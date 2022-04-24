<template>
  <div class="containing-contents__container">
    <div class="containing-contents__item ltr">
      <img src="/src/assets/images/Contents_LTR.png" alt="img">
      <p>Markets</p>
    </div>
    <div class="containing-contents__item rtl">
      <img src="/src/assets/images/Contents_RTL.png" alt="img">
      <p>Defi</p>
    </div>
    <div class="containing-contents__item ltr">
      <img src="/src/assets/images/Contents_LTR.png" alt="img">
      <p>RSI maker</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.containing-contents__item {
  padding: 20px 0;
  position: relative;

  img {
    width: 50%;
  }

  p {
    position: absolute;;
    left: 15%;
    top: calc(50% - 2px);
    transform: translateY(-50%);
    font: 700 16px "Open Sans";
  }
}

.containing-contents__item.rtl {
  display: flex;
  justify-content: flex-end;

  p {
    left: initial;
    right: 15%;
  }
}

</style>