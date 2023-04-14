<template>
  <section class="all-day">
    <h2 class="all-day__title">Погода в течении дня</h2>
    <button @click="prevSlide" class="all-day__button all-day__button_right">
      <img src="../image/leftButton.svg" alt="button-img"/>
    </button>
    <ul class="elements">
      <Element
        v-for="(card, index) in data?.slice(currentIndex, 10)"
        :key="card[index]"
        :card="card"
      ></Element>
    </ul>
    <button @click="nextSlide" class="all-day__button all-day__button_left">
      <img src="../image/rigthButton.svg" alt="button-img"/>
    </button>
  </section>
</template>

<script>
import Element from "./WeatherElement.vue";
export default {
  name: "weather-all",
  components: { Element },
  data() {
    return {
      currentIndex: 0,
    };
  },
  props: {
    data: []
  },
  methods: {
    prevSlide() {
      if (this.currentIndex) {
        this.currentIndex--;
        console.log(this.currentIndex);
      }
    },
    nextSlide() {
      if (this.currentIndex > 3) {
        this.currentIndex=0
      } else {
        this.currentIndex++;
      }
    },
  },
};
</script>

<style >
.all-day__button_right {
  top: 143px;
  left: 32px;
}

.all-day__button_left {
  top: 143px;
  right: 32px;
}

.all-day__button {
  outline: none;
  border: none;
  background-color: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.05);
  border-radius: 50px;
  width: 40px;
  height: 40px;
  position: absolute;
  padding: 12px 16px 12px;
}

.elements {
  display: flex;
  flex-direction: row;
  gap: 24px;
  padding: 0;
  margin: 39px 103px 24px 103px;
  overflow: hidden;
}
.all-day {
  grid-area: b;
  padding: 0;
  width: 50%;
  border: 1px solid #f3f5f7;
  border-radius: 20px;
  position: relative;
}
.all-day__title {
  font-family: Inter;
  font-size: 24px;
  font-weight: 600;
  line-height: 29px;
  text-align: left;
  color: #212225;
  padding: 0 0 24px;
  margin: 24px 32px 0 32px;
  border-bottom: 1px solid #e1e7ee;
}

@media screen and (max-width: 1280px) {
  .all-day {
    height: 190px;
  }

  .all-day__title {
    margin: 16px 20px 0 20px;
    padding-bottom: 16px;
    font-size: 18px;
    font-weight: 600;
    line-height: 22px;
  }

  .elements {
    margin: 24px 0 24px 40px;
    gap: 34px;
  }
  .all-day__button_right {
    top: 101px;
    left: 2px;
  }
  .all-day__button_left {
    top: 101px;
    right: 2px;
  }
}

@media screen and (max-width: 768px) {
  .all-day {
    height: 165px;
  }
  .all-day__title {
    margin: 16px 19px 0 16px;
    padding-bottom: 12px;
    font-size: 14px;
    font-weight: 500;
    line-height: 17px;
    color: #4f5864;
  }

  .elements {
    margin: 16px 36px 16px 20px;
    gap: 32px;
  }
  .all-day__button {
    top: 81px;
    width: 36px;
    height: 29px;
    padding: 4px 11px 7px;
  }
}

@media screen and (max-width: 677px) {
  .all-day {
    width: 100%;
    height: 159px;
  }

  .elements {
    margin: 12px 0 14px 12px;
    gap: 26px;
  }
}
</style>