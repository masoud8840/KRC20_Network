<template>
  <div class="header__container ">
    <nav class="header__navigation">
      <a href="./index.html">
        <img src="/src/assets/images/Navigation_Icon.png" alt="logo">
      </a>
      <ul>
        <li><a href="#api">API</a></li>
        <li><a href="#"><span class="material-symbols-outlined">language</span></a></li>
        <li><a class="btn__secondary btn__login" href="#login">Login</a></li>
        <li><a class="btn__secondary btn__register" href="#register">Register</a></li>
      </ul>
    </nav>
    <div class="header__content">
      <h1>CoperCoin</h1>
      <p>development of copper industry in smart chain network utilizing blockchain infrastructure</p>
    </div>
    <img src="/src/assets/images/Header_Description.png" alt="description-img">
  </div>
</template>


<style lang="scss" scoped>
.header__container {
  background-image: linear-gradient(to top, rgba(29, 11, 52, 0.98) 0%, rgba(0, 0, 0, 0.4) 10%), url("/src/assets/images/Footer_Background_3.png"), url("/src/assets/images/Footer_Background_2.png"),
  url("/src/assets/images/Footer_Background_1.png");
  background-size: cover;
  background-position: top;
  padding-bottom: 50px;

  .header__navigation {
    height: 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;

    ul {
      display: flex;
      align-items: center;

      li {
        a {
          text-decoration: none;
          font: 400 20px "Open Sans";
        }

        list-style: none;
        margin: 0 5px;

        .material-symbols-outlined {
          font-variation-settings: 'FILL' 0,
          'wght' 200,
          'GRAD' 200,
          'opsz' 48
        }

        a.btn__secondary {
          border: 1px solid var(--textColor);
          border-radius: 25px;
          padding: 7px 20px;
          font: 400 13px "Open Sans";
        }
      }
    }


    img {
      width: 75px;
    }
  }

  .header__content {
    padding: 25px 5px;

    h1 {
      font: 700 52px "Open Sans";
      margin-bottom: 10px;
    }

    p {
      font: 400 16px "Open Sans";
      text-transform: uppercase;
      max-width: 93%;
    }

  }

  img {
    width: 100%;
  }
}

// Media Queries
// LargeMobile Device
@media (min-width: 375px) {
  .header__content {
    h1 {
      font-size: 68px !important;
    }
  }
}

@media (min-width: 425px) {
  .header__content {
    h1 {
      font-size: 72px !important;
    }

    p {
      font-size: 18px !important;
    }
  }
}
</style>