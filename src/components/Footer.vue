<template>
  <footer class="footer">
    <button class="footer__logo-button footer__logo-button_shymbulak">
      <img
        class="footer__logo footer__logo_shymbulak"
        src="../image/footerIcon.svg"
        alt="Shymbulak"
      />
    </button>

    <div class="footer__logos">
      <button class="footer__logo-button footer__logo-button_google">
        <img
          class="footer__logo footer__logo_google"
          src="../image/Google.svg"
          alt="google-play"
        />
      </button>
      <button class="footer__logo-button footer__logo-button_app">
        <img
          class="footer__logo footer__logo_app"
          src="../image/App.svg"
          alt="app-store"
        />
      </button>
    </div>

    <div class="footer__container">
      <div class="footer__info">
        <h2 class="footer__title">Курорт</h2>
        <div class="footer__links">
          <a class="footer__link">Отели</a>
          <a class="footer__link">Рестораны</a>
          <a class="footer__link">Развлечения</a>
          <a class="footer__link">Магазин</a>
          <a class="footer__link">Детям</a>
        </div>
      </div>

      <div class="footer__info">
        <h2 class="footer__title">Катания</h2>
        <div class="footer__links">
          <a class="footer__link">Билеты</a>
          <a class="footer__link">Прокат</a>
          <a class="footer__link">Школа</a>
          <a class="footer__link">Паркинг</a>
        </div>
      </div>

      <div class="footer__info">
        <h2 class="footer__title">Инфо</h2>
        <div class="footer__links">
          <a class="footer__link">Погода</a>
          <a class="footer__link">Правила</a>
          <a class="footer__link">Новости</a>
          <a class="footer__link">Как добраться</a>
          <a class="footer__link">Тех. поддержка</a>
        </div>
      </div>

      <div class="footer__info">
        <h2 class="footer__title">Контакты</h2>
        <div class="footer__links footer__links_contacts">
          <div class="footer__icons">
            <a><img class="footer__icon" src="../image/facebook.svg" alt="icon-facebook"/></a>
            <a><img class="footer__icon" src="../image/youtube.svg" alt="icon-youtube"/></a>
            <a><img class="footer__icon" src="../image/instagram.svg" alt="icon-instagram"/></a>
            <a><img class="footer__icon" src="../image/vk.svg" alt="icon-vk"/></a>
          </div>
          <p class="footer__text">info@shymbulak.com</p>
          <p class="footer__text">+7 727 331 77 77</p>
        </div>
      </div>
    </div>

    <div class="footer__author">
      <p class="footer__author-text">© 2023 Alina Development</p>
      <p class="footer__author-text">Created by Alina</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "footer-container",
};
</script>

<style scoped>
.footer {
  background-color: #212225;
  display: grid;
  grid-template-areas:
    "a b b"
    "c b b";
  padding: 0 162px 0;
}

.footer__title {
  font-size: 21px;
  font-weight: 500;
  line-height: 25px;
  color: #ffffff;
  margin: 94px 0 0 0;
}

.footer__author {
  padding-top: 24px;
  border-top: 1px solid #4f5864;
  margin-top: 54px;
  padding-bottom: 24px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 200%;
}

.footer__author-text {
  font-size: 16px;
  font-weight: 400;
  line-height: 19px;
  padding: 0;
  margin: 0;
  color: #4f5864;
}

.footer__icon {
  width: 32px;
  height: 32px;
}

.footer__links {
  display: flex;
  flex-direction: column;
  gap: 16px;
  align-items: flex-start;
}

.footer__logo-button_shymbulak {
  margin-top: 59px;
  grid-area: a;
  height: 84px;
  width: 158px;
}

.footer__link {
  color: #a0a7af;
  font-size: 18px;
  font-weight: 400;
  line-height: 22px;
  letter-spacing: 0em;
}

.footer__text {
  margin: 0;
  padding: 0;
  color: #a0a7af;
  font-size: 18px;
  font-weight: 400;
  line-height: 22px;
  letter-spacing: 0em;
}
.footer__logo-button_app {
  margin-bottom: 55px;
}

.footer__container {
  grid-area: b;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(161px, 1fr));
}

.footer__logo-button {
  outline: none;
  border: none;
  background-color: #212225;
}

.footer__logo_shymbulak {
  height: 84px;
  width: 158px;
}

.footer__logo_google {
  height: 48px;
  width: 158px;
}

.footer__logo_app {
  height: 46px;
  width: 137px;
}
.footer__info {
  display: flex;
  flex-direction: column;
  gap: 24px;
  margin: 0;
  align-items: flex-start;
}

.footer__logos {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  grid-area: c;
}

.footer__icons {
  gap: 16px;
  display: flex;
}

.footer__logo-button_google {
  margin-top: 62px;
  margin-bottom: 17px;
}

@media screen and (max-width: 1280px) {
  .footer {
    display: grid;
    grid-template-areas: "a" "b" "c";
    padding: 0 47px 0;
  }

  .footer__author {
    width: 100%;
  }

  .footer__logo-button_shymbulak {
    margin: 32px 0 40px 0;
  }

  .footer__title {
    margin: 0;
  }

  .footer__link {
    font-size: 16px;
    font-weight: 400;
    line-height: 19px;
  }
  .footer__info {
    gap: 24px;
  }
  .footer__logos {
    margin-top: 57px;
    display: flex;
    flex-direction: row;
    gap: 41px;
  }

  .footer__logo-button_google {
    margin: 0;
  }
}

@media screen and (max-width: 768px) {
  .footer__container {
    margin-left: 16px;
  }
}

@media screen and (max-width: 677px) {
  .footer__logo-button_shymbulak {
    margin: 16px 0 12px 16px;
  }

  .footer__title {
    font-size: 18px;
    font-weight: 500;
    line-height: 22px;
    margin-top: 20px;
  }

  .footer__info {
    gap: 20px;
  }

  .footer__container {
    display: flex;
    flex-direction: column;
  }

  .footer__links {
    display: flex;
    flex-direction: column;
    gap: 16px;
    flex-wrap: wrap;
    align-items: flex-start;
    height: 90px;
    padding-bottom: 20px;
    border-bottom: 1px solid #2c2c2c;
    width: 80%;
  }

  .footer__author {
    flex-direction: column;
    gap: 20px;
  }

  .footer__links_contacts {
    display: flex;
    flex-direction: column;
    height: 100%;
  }
  .footer__logos {
    margin: 0;
    flex-direction: column;
    gap: 10px;
    margin-top: 30px;
    align-items: center;
  }
}
</style>