<template>
  <div class="trade-type__container" :id="`${props.type}`">
    <h3>{{ props.type }} Trading</h3>
    <p>Carry out your futures trades in complete data security according to our smart contracts</p>
    <a :href="`#${props.type}`" class="trade-type__link" @mouseenter="hoverLinkHandler" @mouseleave="hoverLinkHandler">
      Go To Trade
      <img src="/src/assets/images/GoToTradeBtn.png" alt="link-img">
    </a>
  </div>
</template>

<script setup>

const props = defineProps(['type'])

</script>

<style lang="scss" scoped>
.trade-type__container {
  background: transparent url("/src/assets/images/TradeTypeBackground.png") 0 50%/contain no-repeat;
  height: 310px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: 0 5px;
  margin: 25px 0;

  h3 {
    font: 700 32px "Open Sans";
    text-transform: capitalize;
  }

  p {
    max-width: 250px;
    line-height: 1.6;
    font: 400 16px "Open Sans";
    margin: 20px 0;
  }

  .trade-type__link {
    width: 100%;
    max-width: 240px;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    text-decoration: none;
    font: 700 16px "open Sans";

    img {
      max-width: 50px;
    }
  }
}

// Media Queries
// MediumMobile Device
@media (min-width: 375px) {
  .trade-type__container {
    height: 350px;
  }
}
// Tablet
@media (min-width: 425px) {
  .trade-type__container {
    height: 500px;
    h3 {
      font-size: 44px !important;
    }
    p {
      font-size: 18px;
    }
  }
}
</style>