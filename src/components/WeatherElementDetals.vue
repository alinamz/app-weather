<template>
  <li class="element">
    <p class="element__day">{{ item.currentDtWeekday }}</p>
    <p class="element__week">
      {{ item.currentDt + " " + item.currentDtMounth }}
    </p>
    <div>
      <div
        v-bind:style="{ backgroundImage: 'url(' + item.currentIcon + ')' }"
        class="element__img"
      ></div>
      <p class="element__humidity">{{ item.humidity }}</p>
    </div>

    <div class="element__info element__info_first">
      <p class="element__text-info">мин.</p>
      <p class="element__min">{{ item.currentMinTemp }}°C</p>
    </div>

    <div class="element__info">
      <p class="element__text-info">макс.</p>
      <p class="element__min">{{ item.currentMaxTemp }}°C</p>
    </div>
  </li>
</template>

<script>
export default {
  name: "element-detals", 
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.element {
  align-items: flex-start;
  gap: 0;
}
.element__week {
  margin: 0;
  padding: 0;
  font-size: 14px;
  font-weight: 400;
  line-height: 17px;
  color: #6d7784;
}
.element__min {
  margin: 0;
  padding: 0;
}

.element__text-info {
  margin: 0;
  padding: 0;
  font-size: 14px;
  font-weight: 400;
  line-height: 17px;
  color: #a0a7af;
}
.element__info {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 2px;
}

.element__info_first {
  margin-bottom: 8px;
  margin-top: 27px;
}
.element__day {
  font-size: 18px;
  font-weight: 500;
  line-height: 22px;
  color: #4f5864;
  margin: 0 0 4px;
}

.element__humidity {
  display: none;
  font-size: 14px;
  font-weight: 400;
  line-height: 17px;
  color: #75b6f2;
  font-size: 12px;
  font-weight: 600;
  margin: 0;
  padding: 0;
  line-height: 15px;
}

.element__min {
  font-size: 18px;
  font-weight: 500;
  line-height: 22px;
  color: #4f5864;
}

.element__img {
  height: 48px;
  width: 48px;
  margin-top: 27px;
  background-size: cover;
  background-position: center;
}

@media screen and (max-width: 1280px) {
  .element__day {
    font-size: 16px;
    font-weight: 500;
    line-height: 19px;
  }

  .element__img {
    height: 22px;
    width: 22px;
    margin-top: 18px;
  }

  .element__humidit {
    display: block;
  }

  .element__min {
    font-weight: 500;
    size: 16px;
    line-height: 19px;
  }
  .element__week {
    display: none;
  }
  .element__info_first {
    margin-bottom: 8px;
    margin-top: 8px;
  }
}

@media screen and (max-width: 768px) {
  .element__day {
    font-size: 16px;
    font-weight: 500;
    line-height: 19px;
  }

  .element__img {
    margin-top: 16px;
  }

  .element__text-info {
    font-size: 16px;
    font-weight: 400;
    line-height: 19px;
  }

  .element__min {
    font-size: 18px;
    font-weight: 500;
    line-height: 22px;
  }
}

@media screen and (max-width: 677px) {
  .element {
    flex-direction: row;
    align-items: center;
    border-bottom: 1px solid #e1e7ee;
    height: 55px;
    width: 90%;
    justify-content: space-between;
  }

  .element:last-child {
    border: none;
  }

  .element__day {
    margin: 0 16px 0 0;
    width: 67px;
    text-align: left;
  }

  .element__img {
    margin: 0;
  }

  .element__info {
    margin: 0 0 0 20px;
  }
}
</style>