<template>
  <Slide @openMenu="handleOpenMenu" @closeMenu="handleCloseMenu">
    <a id="home" href="#">
      <span>
        <ul class="menu-content">
          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/main.svg" />
            <p class="menu-content__text">Главная</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/bilet.svg" />
            <p class="menu-content__text">Билеты</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/prokat.svg" />
            <p class="menu-content__text">Прокат</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/scholl.svg" />
            <p class="menu-content__text">Школа</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/hobby.svg" />
            <p class="menu-content__text">Развлечения</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/otels.svg" />
            <p class="menu-content__text">Отели</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/restorans.svg" />
            <p class="menu-content__text">Рестораны</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/magazin.svg" />
            <p class="menu-content__text">Магазины</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/kids.svg" />
            <p class="menu-content__text">Детям</p>
          </li>

          <li class="menu-content_element">
            <img class="menu-content__image" src="../image/parking.svg" />
            <p class="menu-content__text">Паркинг</p>
          </li>

          <li class="menu-content_element menu-content_element_info">
            <img class="menu-content__image menu-content__image_info" src="../image/Voscl.svg" />
            <p class="menu-content__text">Инфо</p>
          </li>
        </ul>
      </span>
    </a>
  </Slide>
</template>
<script>
import { Slide } from "vue3-burger-menu";

export default {
  name: "burger-menu",
  components: {
    Slide,
  },
  props: {
    isOpen: Boolean,
  },
  methods: {
    handleOpenMenu() {
      this.$emit("handleOpen", this.isOpen);
    },
    handleCloseMenu() {
      this.$emit("handleClose", !this.isOpen);
    },
  },
};
</script>

<style >
.menu-content_element_info {
  background-color: #75b6f2;
  border-radius: 12px;
  box-shadow: 0px 8.88889px 10.6667px rgba(117, 182, 242, 0.15);
  color: #ffffff;
  width: 136px;
  height: 48px;
  display: flex;
  flex-direction: row;
  padding-left: 12px;
}
.menu-content__image {
  height: 48px;
  width: 48px;
}
.menu-content__text {
  font-size: 18px;
  font-weight: 500;
  line-height: 22px;
}
.menu-content_element {
  display: flex;
  gap: 12px;
  align-items: center;
}
.line-style {
  color: #4f5864;
  height: 5%;
  border-radius: 10px;
  top: 14%;
}
.bm-burger-button {
  height: 56px;
  width: 56px;
  content: url(../image/Burger.svg);
  left: 19px;
  top: 14px;
  z-index: 10;
}

.menu-content__image_info {
  width: 27px;
  height: 27px;
}

.bm-menu,
.bm-overlay {
  background-color: #ffffff;
}

.bm-menu {
  position: absolute;
}

.bm-item-list > * > span {
  color: #4f5864;
}

.cross-style {
  content: url(../image/Burger.svg);
  top: 20px;
  left: 32px;
  height: 56px;
  width: 56px;
}

.menu-content {
  margin-top: 32px;
  margin-left: 40px;
  margin-bottom: 0;
  padding: 0;
  list-style-type: none;
}

@media screen and (max-width: 1280px) {
  .bm-burger-button {
    left: 47px;
    top: 13px;
  }
}

@media screen and (max-width: 768px) {
  .bm-burger-button {
    left: 10px;
    top: 5px;
  }
}
</style>