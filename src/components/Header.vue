<template>
  <header class="header">
    <div class="header__container">
      <img class="header__logo" src="../image/sIcon.svg" alt="logo" />
      <div class="header__buttons">
        <button class="header__button header__button_life">
          <img
            class="header__img header__img_life"
            src="../image/Live.svg"
            alt="live-button"
          />
        </button>

        <button class="header__button header__button_weather">
          <img
            class="header__img header__img_weather"
            src="../image/IconWeather.svg"
            alt="weather=button"
          />
        </button>

        <button class="header__button header__button_change">
          <div class="header__btn header__btn_summer">Лето</div>
          <div class="header__btn header__btn_winter">Зима</div>
        </button>

        <button class="header__button header__button_search">
          <img class="header__img" src="../image/Search.svg" alt="search" />
        </button>
      </div>
    </div>

    <div class="header__container-profile">
      <button class="header__button header__button_lang">RU</button>
      <button class="header__button header__button_profile">
        <img src="../image/Profile.svg" alt="profile-button" />
      </button>
      <button
        class="header__button header__button_profile header__button_saved"
      >
        <img src="../image/Saved.svg" alt="saved-button" />
      </button>
      <button class="header__button header__button_backet">
        <img src="../image/backet.svg" alt="backet-button" />
        <span class="header__backet-sum">8</span>
      </button>
    </div>
  </header>
</template>

<script>
export default {
  name: "header-container",
};
</script>

<style scoped>
.header__backet-sum {
  background-color: #e53d18;
  border-radius: 50px;
  position: absolute;
  width: 22px;
  height: 22px;
  font-size: 14px;
  font-weight: 500;
  line-height: 23px;
  letter-spacing: 0em;
  color: #ffffff;
  right: 5px;
  top: 4px;
}
.header {
  display: flex;
  justify-content: space-between;
  height: 96px;
  align-items: center;
  position: relative;
}

.header__container {
  display: flex;
}

.header__container-profile {
  display: flex;
  gap: 32px;
}

.header__buttons {
  display: flex;
  gap: 32px;
}
.header__logo {
  height: 45px;
  width: 28px;
  margin-left: 107px;
  margin-right: 46px;
}

.header__btn {
  font-size: 16px;
  line-height: 37px;
  font-style: normal;
  font-weight: 500;
}

.header__button {
  outline: none;
  border: none;
  background-color: #ffffff;
  height: 56px;
  width: 146px;
}

.header__button_search {
  height: 56px;
  width: 56px;
}

.header__button_profile {
  height: 56px;
  width: 56px;
}

.header__button_backet {
  height: 56px;
  width: 56px;
  border-radius: 16px;
  border: 1px solid #dae9f4;
  background-color: #ffffff;
  position: relative;
}
.header__btn_summer {
  height: 40px;
  width: 65px;
  border-radius: 12px;
  background-color: #ffd710;
  color: #ffffff;
}

.header__button_lang {
  font-size: 22px;
  font-weight: 400;
  line-height: 26px;
  border: 1px solid #dae9f4;
  background-color: #ffffff;
  height: 56px;
  width: 56px;
  border-radius: 16px;
  color: #6d7784;
}
.header__btn_winter {
  color: #a0a7af;
}

.header__button_change {
  background-color: #ffffff;
  border: 1px solid #dae9f4;
  width: 146px;
  height: 56px;
  border-radius: 16px;
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 12px;
}

@media screen and (max-width: 1280px) {
  .header__button_weather,
  .header__button_life,
  .header__button_change,
  .header__button_lang {
    display: none;
  }

  .header__container {
    display: grid;
    grid-template-areas: "a b";
    flex-grow: 1;
    margin-left: 120px;
  }

  .header__logo {
    grid-area: b;
    margin: 0;
  }

  .header__button_search {
    grid-area: a;
  }

  .header {
    height: 83px;
  }

  .header__container-profile {
    gap: 20px;
    margin-right: 16px;
  }
}

@media screen and (max-width: 768px) {
  .header {
    height: 64px;
  }

  .header__container-profile {
    gap: 12px;
    margin-right: 12px;
  }

  .header__container {
    margin-left: 68px;
  }
}

@media screen and (max-width: 458px) {
  .header__button_saved {
    display: none;
  }
}
</style>