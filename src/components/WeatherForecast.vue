<template>
  <section class="weekly">
    <h2 class="weekly__title">Прогноз на {{ weatherInfoByDays.length }} дней</h2>
    <ul class="weekly__elements">
      <WeatherElementDetals
        v-for="(item, index) in weatherInfoByDays"
        :key="item[index]"
        :item="item"
      />
    </ul>
  </section>
</template>

<script>
import WeatherElementDetals from "./WeatherElementDetals.vue"; 
export default {
  name: "weather-forecast",
  props: {
    data: [],
    weatherInfoByDays: []
  },
  components: {
    WeatherElementDetals,
  },
};
</script>

<style scoped>
.weekly__elements {
  display: flex;
  flex-direction: row;
  gap: 32px;
  padding: 0;
  width: 100%;
  margin: 0 32px 37px 32px;
  justify-content: space-between;
  overflow: auto;
  width: 95%;
}

.weekly__title {
  font-size: 24px;
  font-weight: 600;
  line-height: 29px;
  text-align: left;
  margin: 0 0 40px 32px;
  padding: 24px 0 0;
  color: #212225;
}

.weekly {
  padding: 0;
  margin-top: 48px;
  background-color: #f4f8fd;
  border-radius: 20px;
  height: 328px;
  margin-bottom: 96px;
}

@media screen and (max-width: 1280px) {
  .weekly {
    margin-top: 24px;
    height: 228px;
  }

  .weekly__title {
    padding: 16px 0 16px 0;
    border-bottom: 1px solid #e1e7ee;
    margin: 0 20px 0 20px;
    font-size: 18px;
    font-weight: 600;
    line-height: 22px;
  }

  .weekly__elements {
    margin: 24px 24px 24px 20px;
    gap: 24px;
  }
}

@media screen and (max-width: 768px) {
  .weekly {
    margin-top: 24px;
    margin-bottom: 48px;
  }
  .weekly__title {
    padding: 16px 0 12px 0;
    margin: 0 16px 0 16px;
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
    color: #4f5864;
  }

  .weekly__elements {
    margin: 24px 0 24px 16px;
    gap: 32px;
  }
}

@media screen and (max-width: 677px) {
  .weekly__elements {
    flex-direction: column;
    gap: 0;
  }

  .weekly {
    height: 100%;
  }
}
</style>