<template>
  <div class="background">
    <BurgerMenu
      :isOpen="isOpen"
      @handleOpen="handleOpen"
      @handleClose="handleClose"
    ></BurgerMenu>
    <div :class="[isOpen ? 'page' : '']">
      <Header
        :isOpen="isOpen"
        @handleOpen="handleOpen"
        @handleClose="handleClose"
      ></Header>
      <Weather :data="data" :weatherInfoByDays="weatherInfoByDays"></Weather>
      <Footer></Footer>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Weather from "./components/Weather.vue";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import BurgerMenu from "./components/Burger-Menu.vue";
import token from './config/config'

export default {
  data() {
    return {
      isOpen: false,
      data: null,
      weatherInfoByDays: [],
    };
  },
  components: {
    Weather,
    Header,
    Footer,
    BurgerMenu,
  },
  methods: {
    handleOpen() {
      this.isOpen = true;
    },
    handleClose() {
      this.isOpen = false;
    },
  },
  mounted() {
    axios
      .get(
        `https://api.openweathermap.org/data/2.5/forecast?lat=43.12&lon=77.08&appid=${token}&units=metric&lang=ru`
      )
      .then((response) => {
        this.data = response.data.list.map((w) => ({
          dt: new Date(Date.parse(w.dt_txt)),
          temp: Math.floor(w.main.temp),
          minTemp: Math.floor(w.main.temp_min),
          maxTemp: Math.floor(w.main.temp_max),
          windSpeed: w.wind.speed,   // Скорость ветра
          humidity: w.main.humidity, // Влажность
          iconUrl: `http://openweathermap.org/img/w/${w.weather[0].icon}.png`,
          description: w.weather[0].description.charAt(0).toUpperCase() + w.weather[0].description.slice(1),
        }));

        // Группируем температуры по дню месяца без учета времени
        const tempsByDay = this.data.reduce((acc, item) => {
          (acc[item.dt.getDate()] = acc[item.dt.getDate()] || []).push(
            item.temp
          );
          return acc;
        }, {});

        const days = Object.keys(tempsByDay);
        const month = [
          "Январь",
          "Февраль",
          "Март",
          "Апрель",
          "Май",
          "Июнь",
          "Июль",
          "Август",
          "Сентябрь",
          "Октябрь",
          "Ноябрь",
          "Декабрь",
        ];

        const weekday = [
          "Понедельник",
          "Вторник",
          "Среда",
          "Четверг",
          "Пятница",
          "Суббота",
          "Воскресенье",
        ];

        for (let i = 0; i < days.length; i++) {
          const day = days[i];
          const currentMinTemp = Math.min(...tempsByDay[day]);
          const currentMaxTemp = Math.max(...tempsByDay[day]);

          var currentDayWeather = this.data.filter((w) => w.dt.getDate() == day)[0];
          const currentDt = currentDayWeather?.dt;
          const currentIcon = currentDayWeather?.iconUrl;
          const humidity = currentDayWeather?.humidity;

          this.weatherInfoByDays.push({
            currentIcon: currentIcon,
            currentDt: currentDt.getDate(),
            humidity: humidity,
            currentMinTemp: currentMinTemp,
            currentMaxTemp: currentMaxTemp,
            currentDtMounth: month[currentDt.getMonth()],
            currentDtWeekday: weekday[currentDt.getDay()],
          });
        }
      })
      .catch((err) => console.log(err));
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #ffffff;
}

.background {
  max-width: 1920px;
  min-width: 320px;
  margin: auto;
  min-height: 100vh;
  position: relative;
}

.page {
  margin-left: auto;
  width: 81%;
}

body {
  margin: 0;
}

a:hover {
  opacity: 0.5;
}

@media screen and (max-width: 1280px) {
  .page {
    width: 100%;
  }
}
</style>
