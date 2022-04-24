<template>
  <div class="live-price__container">
    <img src="/src/assets/images/LivePrice.png" alt="live_price_bg"/>
    <div class="live-price__info" v-if="true">
      <h3 class="symbol">{{ showSymbol }}</h3>
      <p class="price">{{ showPrice }}</p>
      <span class="change24H" :class="change24HPriceStyleSetter">{{ show24HChange }}%</span>
    </div>
    <loading-spinner
        :active="isLoading"
        color="#fafafa"
        background-color="#000"
        :opacity="0.2"
        blur="1.5"
        :width="96"
        :height="96"
    ></loading-spinner>
  </div>
</template>

<script setup>
import {computed, ref} from "vue";
import LoadingSpinner from "vue-loading-overlay"

const isLoading = ref(true)
const props = defineProps(["symbol", "price", "change24H"]);

const change24HPriceStyleSetter = computed(() => {
  if (props.change24H > 0) return "positive-change";
  else return "negative-change";
});

const showPrice = computed(() => {
  if (!isNaN(props.price)) {
    isLoading.value = false
    return props.price
  }
})

const showSymbol = computed(() => {
  if (props.symbol === "Loading...") {
    return "Loading..."
  } else {
    return props.symbol.toString().toUpperCase()
  }
})

const show24HChange = computed(() => {
  return parseFloat(props.change24H).toFixed(2)
})
</script>

<style lang="scss">
.live-price__container {
  position: relative;
  margin: 20px;

  img {
    max-width: 140px;
    pointer-events: none;
  }

  .live-price__info {
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;

    h3 {
      font: 700 32px "Open Sans";
    }

    p {
      font: 300 19px "Open Sans";
    }

    span {
      font: 500 17px "Open Sans";
    }

    .positive-change {
      color: var(--positivePriceChange);
    }

    .negative-change {
      color: var(--negativePriceChange);
    }
  }

  .vld-overlay {
    position: absolute;;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
}

// Media Queries
// Medium Mobile Device
@media (min-width: 375px) {
  .live-price__container {
    img {
      max-width: 165px;
    }

    .live-price__info {
      p {
        margin: 10px 0 5px;
      }
    }
  }


}

// Large Mobile Device
@media (min-width: 425px) {
  .live-price__container {
    img {
      max-width: 190px;
    }
  }
}

// Tablet Device
@media (min-width: 768px) {
  .live-price__container {
    img {
      max-width: 220px;
    }
  }
}
</style>
