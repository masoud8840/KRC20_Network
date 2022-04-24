<template>
  <footer class="footer__container">
    <div class="footer__title">
      <img src="/src/assets/images/Network_Icon.png" alt="network-icon">
      <h2>KRC20 NTB</h2>
    </div>
    <div class="footer__content">
      <div class="column">
        <a href="#api">API</a>
        <a href="#fee">Fee</a>
        <a href="#pool">Pool</a>
      </div>
      <div class="column">
        <a href="#dev">Developer</a>
        <a href="#blockchainExplorer">Blockchain Explorer</a>
        <a href="#swap">Swap</a>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer__container {
  margin: 25px 0 0;
  padding: 30px;
  background-color: transparent;
  background-image: linear-gradient(to top, #1d0b34, rgba(0, 0, 0, 0.2)), url("/src/assets/images/Footer_Background_3.png"), url("/src/assets/images/Footer_Background_2.png"),
  url("/src/assets/images/Footer_Background_1.png");
  background-size: cover;
  background-position: top;

  .footer__title {
    display: flex;
    align-items: center;
    justify-content: center;

    img {
      max-width: 100px;
    }

    h2 {
      font: 700 42px "Open Sans";
      margin-left: 25px;
    }
  }

  .footer__content {
    display: flex;
    margin-top: 40px;
    padding: 0 10px;

    .column {
      display: flex;
      flex-direction: column;
      padding: 0 5px;

      a {
        margin: 4px;
        text-decoration: none;
        font: 400 18px "Open Sans";
      }
    }
  }
}

</style>