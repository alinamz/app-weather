<template>
  <main class="main">
    <h1 class="main__title">Погода</h1>
    <div class="main__display">
      <WeaterNow :data="data"></WeaterNow>
      <WeatherAllDay :data="data"></WeatherAllDay>
    </div>
    <Forecast :weatherInfoByDays="weatherInfoByDays" :data="data" />
  </main>
</template>

<script>
import WeaterNow from "./WeatherNow.vue";
import WeatherAllDay from "./WeatherAllDay.vue"; 
import Forecast from "./WeatherForecast.vue";
export default {
  name: "weather-main",
  props: {
    data: [],
    weatherInfoByDays: []
  },
  components: {
    WeaterNow,
    WeatherAllDay,
    Forecast,
  },
};
</script>

<style scoped>
.main__display {
  display: flex;
  flex-direction: row;
  gap: 24px;
  max-height: 256px;
}
.main {
  margin: auto;
  width: calc(100% - 324px);
  gap: 24px;
}

.main__title {
  font-size: 40px;
  font-weight: 600;
  line-height: 48px;
  text-align: left;
  color: #212225;
}

@media screen and (max-width: 1280px) {
  .main {
    width: calc(100% - 94px);
  }

  .main__title {
    font-size: 32px;
    font-weight: 600;
    line-height: 39px;
    margin-top: 25px;
    margin-bottom: 48px;
  }
  .main__display {
    gap: 12px;
  }
}

@media screen and (max-width: 768px) {
  .main__title {
    margin: 16px 0 24px 0;
    font-size: 24px;
    font-weight: 600;
    line-height: 29px;
  }
  .main {
    width: calc(100% - 64px);
  }
  .main__display {
    gap: 12px;
  }
}

@media screen and (max-width: 360px) {
  .main__title {
    font-size: 24px;
    font-weight: 600;
    line-height: 29px;
    margin: 16px 0 24px 0;
  }
}

@media screen and (max-width: 677px) {
  .main__display {
    flex-direction: column;
    gap: 24px;
    max-height: 100%;
  }

  .main {
    width: calc(100% - 32px);
  }

}
</style>