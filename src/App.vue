<template>
  <div class="container" v-if="!isDesktop">
    <the-header></the-header>
    <header>
      <live-price :symbol="BTC.symbol" :price="BTC.price" :change24-h="BTC.change24H"
      ></live-price>
      <live-price :symbol="ETH.symbol" :price="ETH.price" :change24-h="ETH.change24H"
      ></live-price>
    </header>
    <network-introduction></network-introduction>
    <trade-type v-for="(tradeType) in tradesType" :type="tradeType"></trade-type>
    <containing-contents></containing-contents>
    <the-footer></the-footer>
  </div>
  <the-desktop v-else></the-desktop>
</template>

<script setup>
import LivePrice from "./components/UI/LivePrice.vue";
import TradeType from "./components/UI/TradeType.vue";
import ContainingContents from "./components/UI/ContainingContents.vue"
import TheHeader from "./components/layout/TheHeader.vue"
import TheFooter from "./components/layout/TheFooter.vue";
import TheDesktop from "./components/TheDesktop.vue"
import {onMounted, ref} from "vue";
import axios from "axios";
import NetworkIntroduction from "./components/UI/NetworkIntroduction.vue";


const isDesktop = ref(false)
onMounted(() => {
  isDesktop.value = !(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
      navigator.userAgent));
});


const tradesType = ["futures", "spot"];

const BTC = ref({symbol: 'Loading...', price: 'N/A', change24H: "0"})
const ETH = ref({symbol: 'Loading...', price: 'N/A', change24H: "0"})

// get price from api
const config = {
  method: 'get',
  url: 'https://api.coincap.io/v2/assets?limit=2',
  headers: {}
};
const updateCurrencies = () => {
  axios(config)
      .then((res) => res.data).then((data) => {
    BTC.value.symbol = 'btc';
    BTC.value.change24H = data.data[0].changePercent24Hr

    ETH.value.symbol = 'eth';
    ETH.value.change24H = data.data[1].changePercent24Hr

  }).catch((err) => {
    console.log(err)
  })
}

// show price using websocket
const btcPriceLive = new WebSocket('wss://ws.coincap.io/prices?assets=bitcoin')
btcPriceLive.onmessage = function (msg) {
  const btcPrice = JSON.parse(msg.data);
  BTC.value.price = btcPrice.bitcoin;
}
const ethPriceLive = new WebSocket('wss://ws.coincap.io/prices?assets=ethereum')
ethPriceLive.onmessage = function (msg) {
  const ethPrice = JSON.parse(msg.data);
  ETH.value.price = ethPrice.ethereum
}
setInterval(updateCurrencies, 1000)
</script>

<style lang="scss" scoped>
header {
  display: flex;
  justify-content: center;
}
</style>

<style lang="scss">
.container {
  max-width: 1200px;
  margin: 0 auto;
}

#app {
  background-color: var(--mainColor);
}

:root {
  --mainColor: #1d0b34;
  --textColor: #fafafa;

  --positivePriceChange: #4dffa9;
  --negativePriceChange: #ff4040;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: var(--textColor);
  scroll-behavior: smooth;
}
</style>
