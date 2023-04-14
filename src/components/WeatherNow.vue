<template>
  <section class="container">
    <p class="container__name">Сейчас</p>

    <div class="container__flex">
      <img
        class="container__image"
        src="../image/Icons.svg"
        alt="weather-image"
      />

      <div class="container__description">
        <p class="container__characteristic">{{ this.data?.length > 0 ? this.data[0].description : 'n/a' }}</p>
        <p class="container__degrees">{{ this.data?.length > 0 ? this.data[0].temp + '°C' : 'n/a' }}</p>

        <div class="container__data">
          <div class="container__data-info">
            <img
              class="container__image-data"
              src="../image/Wind.png"
              alt="wind"
            />
            <p class="container__text">{{ this.data?.length > 0 ? this.data[0].windSpeed + 'м/c' : 'n/a' }}</p>
          </div>

          <div class="container__data-info">
            <img
              class="container__image-data"
              src="../image/Precipitation.png"
              alt="precipitation"
            />
            <p class="container__text">{{ this.data?.length > 0 ? this.data[0].humidity + '%' : 'n/a' }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "weather-now",
  props: {
    data: [],
  }
};
</script>

<style scoped>
.container__flex {
  display: flex;
  flex-direction: row;
  gap: 56px;
  align-items: flex-end;
  margin: 0 0 32px 32px;
}
.container {
  background: #75b6f2;
  border-radius: 20px;
  padding: 0;
  grid-area: a;
  width: 50%;
}

.container__name {
  font-family: Inter;
  font-size: 24px;
  font-weight: 600;
  line-height: 29px;
  color: #ffffff;
  margin: 24px 0 8px 32px;
  padding: 0;
  text-align: left;
}

.container__text {
  font-size: 18px;
  font-weight: 400;
  line-height: 22px;
  text-align: left;
  margin: 0;
  padding: 0;
}

.container__description {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.container__image-data {
  height: 23px;
  width: 23px;
}

.container__data {
  display: flex;
  flex-direction: row;
  gap: 36px;
  margin-top: 17px;
  color: #ffffff;
}

.container__data-info {
  display: flex;
  flex-direction: row;
  gap: 12px;
}

.container__degrees {
  font-family: Inter;
  font-size: 64px;
  font-weight: 700;
  line-height: 77px;
  color: #ffffff;
  margin: 0 32px 0 0;
  padding: 0;
  text-align: left;
  padding-bottom: 16px;
  padding-top: 8px;
  border-bottom: 1px solid #ffffff;
}

.container__characteristic {
  font-family: Inter;
  font-size: 18px;
  font-weight: 600;
  line-height: 22px;
  color: #ffffff;
  margin: 0;
  text-align: left;
  padding: 0;
}

.container__image {
  height: 147px;
  width: 147px;
}

@media screen and (max-width: 1280px) {
  .container__name {
    font-size: 18px;
    font-weight: 600;
    line-height: 22px;
    margin: 16px 0 0 20px;
  }

  .container__image {
    width: 128px;
    height: 128px;
  }

  .container__flex {
    margin: 0 0 16px 24px;
    gap: 48px;
  }

  .container__characteristic {
    font-size: 16px;
    font-weight: 600;
    line-height: 19px;
  }

  .container__degrees {
    font-size: 56px;
    font-weight: 700;
    line-height: 68px;
    padding: 4px 0 4px;
  }

  .container__data-info {
    gap: 8px;
  }

  .container__text {
    font-size: 16px;
    font-weight: 400;
    line-height: 19px;
  }

  .container__image-data {
    height: 20px;
    width: 20px;
  }

  .container {
    height: 190px;
  }
}
@media screen and (max-width: 901px) {
  .container__data {
    gap: 10px;
  }
}

@media screen and (max-width: 869px) {
  .container__data {
    display: none;
  }
}

@media screen and (max-width: 768px) {
  .container {
    height: 165px;
    display: flex;
    flex-direction: column-reverse;
    justify-content: start;
    position: relative;
  }

  .container__image {
    height: 112px;
    width: 112px;
  }

  .container__flex {
    margin: 14px 0 0 28px;
    gap: 42px;
    align-items: flex-start;
  }

  .container__name {
    margin: 0;
    position: absolute;
    bottom: 13px;
    left: 181px;
    font-size: 14px;
    font-weight: 300;
    line-height: 17px;
  }

  .container__degrees {
    font-size: 48px;
    font-weight: 700;
    line-height: 58px;
    padding: 0 0 4px 0;
    margin: 0;
    max-width: 114px;
  }

  .container__description {
    flex-direction: column-reverse;
  }

  .container__characteristic {
    margin-top: 6px;
    font-size: 21px;
    font-weight: 600;
    line-height: 25px;
  }
}

@media screen and (max-width: 677px) {
  .container {
    height: 168px;
    width: 100%;
  }

  .container__image {
    height: 123px;
    width: 120px;
  }

  .container__flex {
    margin: 20px 0 0 28px;
    gap: 33px;
  }

  .container__name {
    bottom: 15px;
    left: 181px;
  }

  .container__degrees {
    width: 90%;
  }
}


</style>
