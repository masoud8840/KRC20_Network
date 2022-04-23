<template>
  <div class="network-introduction__container">
    <section class="network-introduction__description">
      <h3>KRC20 network</h3>
      <p>development of blockchain flexibility infrastructure in smart chains under krc20 network to create a layer of
        user security expansion</p>
    </section>
    <img src="/src/assets/images/Introduce_Network.png" alt="network-intro-img">
  </div>
</template>

<script>
export default {
  name: "NetworkIntroduction"
}
</script>

<style lang="scss" scoped>
.network-introduction__container {
  display: flex;;
  flex-direction: column-reverse;
  justify-content: center;
  align-items: center;
  margin: 25px 0 50px;


  img {
    max-width: 180px;
  }

  .network-introduction__description {
    h3 {
      font: 700 38px "Open Sans";
    }

    P {
      text-transform: uppercase;
      line-height: 1.3;
      font: 400 14px "Open Sans";
    }
  }
}

// Media Queries

// Large Mobile Device
@media (min-width: 375px) {
  .network-introduction__container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }
  .network-introduction__description {
    h3 {
      line-height: 1.1 !important;
      margin-bottom: 10px !important;
    }
  }
  img {
    max-width: 100% !important;
  }
}

// Tablet Device
@media (min-width: 768px) {
  img {
    max-width: 400px !important;
    margin: 0 auto;
  }
  .network-introduction__description {
    h3 {
      font-size: 60px !important;
      margin-bottom: 25px;
      line-height: 1 !important;

    }

    p {
      font-size: 19px !important;
    }
  }
}
</style>