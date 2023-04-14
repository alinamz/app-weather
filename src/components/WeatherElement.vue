<template>
  <li class="element">
    <p class="element__time">{{ card.dt.getHours() }}:00</p>
    <img src="../image/vue.svg" class="element__image" alt="weather" />
    <p class="element__degrees">{{ card.temp }}°C</p>
  </li>
</template>

<script>
export default {
  name: "weather-element",
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style >
.element__degrees {
  margin: 0;
  font-size: 24px;
  font-weight: 500;
  line-height: 29px;
}
.element {
  display: flex;
  flex-direction: column;
  gap: 8px;
  align-items: start;
}

.element__image {
  height: 32px;
  width: 32px;
  margin: 0;
}

.element__time {
  margin: 0;
  color: #6d7784;
  font-size: 16px;
  font-weight: 500;
  line-height: 19px;
}

@media screen and (max-width: 1280px) {
  .element__time {
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
  }

  .element__image {
    height: 26px;
    width: 26px;
  }

  .element__degrees {
    font-size: 18px;
    font-weight: 500;
    line-height: 22px;
  }
}

@media screen and (max-width: 768px) {
  .element__time {
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
  }

  .element__image {
    height: 24px;
    width: 24px;
  }

  .element__degrees {
    font-size: 18px;
    font-weight: 500;
    line-height: 22px;
  }
}

@media screen and (max-width: 677px) {
  .element {
    gap: 10px;
  }
}
</style>