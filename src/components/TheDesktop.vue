<template>
  <div class="desktop__container">
    <div class="container">
      <div>
        <h1>CoperCoin <br>Only On <br>Mobile</h1>
        <p>PLEASE LOG IN WITH MOBILE</p>
      </div>
      <img class="mobile" src="/src/assets/images/desktop/MobileDevice.png" alt="mobile-version">
      <img src="/src/assets/images/desktop/Grass.png" alt="grass-img" class="grass">
    </div>
  </div>
</template>


<style lang="scss" scoped>
.desktop__container {
  background-image: linear-gradient(to top, rgba(29, 11, 52, 0.98), rgba(0, 0, 0, 0.4)), url("/src/assets/images/Footer_Background_3.png"), url("/src/assets/images/Footer_Background_2.png"),
  url("/src/assets/images/Footer_Background_1.png");
  background-size: cover;
  background-position: top;
  height: 100vh;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  flex-direction: column;

  .container {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    column-gap: 75px;
    align-items: center;
    position: relative;
    h1 {
      font: 700 120px "Open Sans";
    }

    p {
      font: 500 32px "Open Sans";
    }
    img.mobile {
      max-width: 100%;
    }
    img.grass {
      max-width: 300px;
      position: absolute;;
      bottom: 0;
      left: 50%;
      transform:translateX(-50%);
    }
  }

}

</style>