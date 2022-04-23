<template>
  <div class="live-price__container">
    <img src="/src/assets/images/LivePrice.png" alt="live_price_bg"/>
    <div class="live-price__info">
      <h3 class="symbol">{{ showSymbol }}</h3>
      <p class="price">{{ showPrice }}</p>
      <span class="change24H" :class="change24HPriceStyleSetter">{{ show24HChange }}%</span>
    </div>
  </div>
</template>

<script setup>
import {computed} from "vue";

const props = defineProps(["symbol", "price", "change24H"]);

const change24HPriceStyleSetter = computed(() => {
  if (props.change24H > 0) return "positive-change";
  else return "negative-change";
});

const showPrice = computed (() => {
  if (isNaN(props.price)) {
    return "loading..."

  } else {
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
    max-width: 230px;
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
      color: var(--textColor);
    }

    p {
      font: 300 19px "Open Sans";
      color: var(--textColor);
      margin: 10px 0 5px;
    }

    span {
      font: 500 17px "Open Sans";
      color: var(--textColor);
    }

    .positive-change {
      color: var(--positivePriceChange);
    }

    .negative-change {
      color: var(--negativePriceChange);
    }
  }
}
</style>
