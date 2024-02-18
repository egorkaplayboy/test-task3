<template>
  <nav class="nav">
    <div class="nav__logo">
      <svg class="nav__logo-icon">
        <use xlink:href="../assets/logo.svg#logo"></use>
      </svg>
    </div>
    <ul class="nav__list">
      <li
        class="nav__list-item"
        v-for="(link, index) in navLinks"
        :key="link"
        @click="handleNavItemClick(index)"
      >
        {{ link }}
      </li>
    </ul>
    <div class="nav__socials" v-if="isPopupOpen">
      <div class="nav__socials-wrapper">
        <svg class="nav__socials-item">
          <use xlink:href="../assets/svg_sprite/sprite.svg#vk"></use>
        </svg>
        <svg class="nav__socials-item">
          <use xlink:href="../assets/svg_sprite/sprite.svg#ok"></use>
        </svg>
        <svg class="nav__socials-item">
          <use xlink:href="../assets/svg_sprite/sprite.svg#facebook"></use>
        </svg>
        <svg class="nav__socials-item">
          <use xlink:href="../assets/svg_sprite/sprite.svg#insta"></use>
        </svg>
      </div>
    </div>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      navLinks: [
        "О нас",
        "Наши ценности",
        "Вакансии",
        "Начало карьеры",
        "Контакты",
        "Социальные сети",
      ],
      isPopupOpen: false,
    };
  },
  methods: {
    handleNavItemClick(index) {
      // Проверяем, является ли элемент последним
      if (index === this.navLinks.length - 1) {
        this.isPopupOpen = !this.isPopupOpen; // Переключаем состояние попапа
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/_vars.scss";
@mixin horizontal {
  display: flex;
  align-items: center;
}
.nav {
  position: relative;
  @include horizontal;
  justify-content: space-between;
  &__logo-icon {
    width: 115px;
    height: 25px;
    cursor: pointer;
  }
  &__list {
    @include horizontal;
    list-style-type: none;
  }
  &__list-item {
    position: relative;
    font-size: 16px;
    color: $Dark;
    margin: 32px;
    padding-bottom: 27px;
    cursor: pointer;
    @include f400;

    &::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 0;
      height: 2px;
      background-color: $Orange;
      transition: width 0.3s;
    }

    &:hover::after {
      width: 100%;
    }
  }
  &__list-item:last-child:hover::after {
    width: 0;
  }
  &__list-item:last-child {
    font-size: 16px;
    color: $Blue;
    margin: 30px;
    cursor: pointer;
    @include f400;
    display: flex;
    align-items: center;
  }
  &__socials {
    padding: 15px;
    box-shadow: 0px 17px 46px 0px #00000014;
    position: absolute;
    top: 100%;
    right: 0;
    background-color: white;
    z-index: 10;
  }
  &__socials-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  &__socials-item {
    width: 25px;
    height: 20px;
    cursor: pointer;
    padding: 20px;
    fill: $Orange;
    border: 1px solid $Gray;
  }
  &__socials-item:hover {
    fill: $MainBlue;
  }
}
</style>
