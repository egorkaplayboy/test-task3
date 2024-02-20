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
  <nav class="nav-tablet">
    <div class="nav__logo">
      <svg class="nav__logo-icon">
        <use xlink:href="../assets/logo.svg#logo"></use>
      </svg>
    </div>
    <div class="nav__burger-btn" @click="handleBurgerBtnClick" ref="burgerBtn">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="nav__overlay" v-if="isSidebarOpen">
      <div class="nav__sidebar" ref="sidebar" :class="{ open: isSidebarOpen }">
        <ul class="nav__list-tablet">
          <li
            class="nav__list-item-tablet"
            v-for="(link, index) in navLinksTablet"
            :key="link"
            @click="handleNavItemClick(index)"
          >
            {{ link }}
          </li>
        </ul>
        <div class="nav__socials-tablet">
          <div class="nav__socials-wrapper-tablet">
            <svg class="nav__socials-item-tablet">
              <use xlink:href="../assets/svg_sprite/sprite.svg#vk"></use>
            </svg>
            <svg class="nav__socials-item-tablet">
              <use xlink:href="../assets/svg_sprite/sprite.svg#ok"></use>
            </svg>
            <svg class="nav__socials-item-tablet">
              <use xlink:href="../assets/svg_sprite/sprite.svg#facebook"></use>
            </svg>
            <svg class="nav__socials-item-tablet">
              <use xlink:href="../assets/svg_sprite/sprite.svg#insta"></use>
            </svg>
          </div>
        </div>
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
      navLinksTablet: [
        "О нас",
        "Наши ценности",
        "Вакансии",
        "Начало карьеры",
        "Контакты",
      ],
      //Состояние popup
      isPopupOpen: false,
      // Cостояние для отображения шторки
      isSidebarOpen: false,
    };
  },
  mounted() {
    document.addEventListener("click", this.handleClickOutside);
  },
  beforeDestroy() {
    document.removeEventListener("click", this.handleClickOutside);
  },
  methods: {
    handleNavItemClick(index) {
      // Проверяем, является ли элемент последним
      if (index === this.navLinks.length - 1) {
        this.isPopupOpen = !this.isPopupOpen; // Переключаем состояние попапа
      }
    },
    handleBurgerBtnClick() {
      // Изменяем состояние для отображения шторки
      this.isSidebarOpen = !this.isSidebarOpen;
    },
    handleClickOutside(event) {
      const sidebar = this.$refs.sidebar; // Получаем ссылку на элемент sidebar
      if (
        !sidebar.contains(event.target) &&
        !this.$refs.burgerBtn.contains(event.target)
      ) {
        this.isSidebarOpen = false; // Закрываем шторку, если клик был вне sidebar и кнопки "бургер"
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
  padding: 34px 40px;
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

// Tablet

.nav-tablet {
  @include horizontal;
  justify-content: space-between;
  padding: 34px 40px;
}
.nav__burger-btn {
  display: block;
  z-index: 15;
  span {
    width: 28px;
    height: 2px;
    background-color: $Blue;
    display: block;

    & + span {
      margin-top: 6px;
    }
  }
}
.nav__overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 19;
}
.nav__sidebar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 472px;
  background-color: #003264;
  z-index: 20;
  transition: transform 0.3s;
  transform: translateY(-100%);
}

.nav__sidebar.open {
  transform: translateY(0);
}
.nav__list-tablet {
  display: flex;
  flex-direction: column;
  align-self: start;
  list-style-type: none;
  padding-top: 68px;
  padding-left: 40px;
}
.nav__list-item-tablet {
  @include f400;
  font-size: 16px;
  color: #fff;
  margin-bottom: 40px;
}
.nav__list-item-tablet:hover {
  color: $Blue;
}
.nav__socials-wrapper-tablet {
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav__socials-item-tablet {
  width: 48px;
  height: 36px;
  margin: 8px;
  padding: 10px 15px;
  border: 1px solid #ffffff14;
  margin-bottom: 53px;
  fill: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
}
.nav__socials-item-tablet:hover {
  border: 1px solid $Gray;
}
// Media
@media (min-width: 1001px) {
  .nav {
    display: flex;
  }
  .nav-tablet {
    display: none;
  }
}
@media (max-width: 1000px) {
  .nav {
    display: none;
  }
  .nav-tablet {
    display: flex;
  }
}
</style>
