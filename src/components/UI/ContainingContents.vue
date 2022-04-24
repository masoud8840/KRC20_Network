<template>
  <div class="containing-contents__container">
    <div class="containing-contents__item ltr">
      <div class="containing-content__holder">
        <img src="/src/assets/images/Contents_LTR.png" alt="img">
        <p>Markets</p>
      </div>
    </div>
    <div class="containing-contents__item rtl">
      <div class="containing-content__holder">
        <img src="/src/assets/images/Contents_RTL.png" alt="img">
        <p>Defi</p>
      </div>
    </div>
    <div class="containing-contents__item ltr">
      <div class="containing-content__holder">
        <img src="/src/assets/images/Contents_LTR.png" alt="img">
        <p>RSI maker</p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.containing-contents__item {

  .containing-content__holder {
    max-width: 50%;
    position: relative;

    img {
      width: 100%;
    }
  }

  p {
    position: absolute;;
    left: 50%;
    top: 45%;
    transform: translate(-50%, -50%);
    font: 700 15px "Open Sans";
  }
}

.containing-contents__item.rtl {
  display: flex;
  justify-content: flex-end;

  p {
    left: initial;
    right: 37%;
    transform: translate(-50%, -50%);
  }
}

// Media Queries
// LargeMobile Device
@media (min-width: 425px) {
  .containing-content__holder {
    p {
      font-size: 18px;
      top: 50%;
    }
  }
}
</style>