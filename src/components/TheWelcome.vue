<template>
  <section class="welcome">
    <div class="container">
      <div class="welcome__info">
        <h1 class="welcome__title">
          Энергия твоего роста! – <br />заряжаем твою карьеру
        </h1>
        <button @click="showPopup" class="welcome__button" href="#">
          Cтать частью команды
        </button>
      </div>
    </div>
    <img class="welcome__img" src="../assets/img/welcomePeoples.png" alt="#" />
    <ThePopup v-if="isOpen" @close="closePopup" />
  </section>
</template>

<script>
import ThePopup from "./ThePopup.vue";
export default {
  components: {
    ThePopup,
  },
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    showPopup() {
      this.isOpen = true;
    },
    closePopup() {
      this.isOpen = false;
    },
  },
};
</script>
<style lang="scss" scoped>
@import "../assets/scss/_vars.scss";
.welcome {
  background: url(../assets/img/welcomeBlue.png) left no-repeat,
    url(../assets/img/welcomeHome.jpg) right no-repeat;
  position: relative;
  height: 448px;
  margin-bottom: 57px;
  &__info {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  &__title {
    @include f700;
    font-size: 36px;
    color: #ffffff;
    display: flex;
    align-items: center;
  }
  &__button {
    margin-top: 59px;
    width: 254px;
    height: 64px;
    background-color: $Orange;
    padding: 22px 33px;
    color: #fff;
    @include f700;
    border: none;
    outline: none;
    cursor: pointer;
    font-size: 16px;
    transition: all 0.5s;
    z-index: 6;
    &:hover {
      background-color: #e77e1e;
    }
  }
  &__img {
    position: absolute;
    bottom: 0;
    right: 50px;
  }
}

// Media

@media (max-width: 1200px) {
  .welcome {
    margin-bottom: 38px;
    background: url(../assets/img/welcomeBlue.png) -460px no-repeat,
      url(../assets/img/welcomeHome.jpg) right no-repeat;
    &__title {
      font-size: 30px;
      line-height: 35px;
      display: flex;
      align-items: center;
    }
    &__button {
      margin-top: 51px;
    }
    img {
      height: 334px;
      right: -95px;
    }
  }
}
@media (max-width: 320px) {
  .welcome {
    margin-bottom: 38px;
    height: 318px;
    padding-top: 24px;
    background: #003264 url(../images/main/mainPeople.png) bottom;
    background-position: right;
    background-size: 100%;
    background-repeat: no-repeat;

    &__title {
      font-size: 22px;
      line-height: 26px;
      text-align: center;
      z-index: 10;
    }
    &__button {
      display: block;
      margin: 0 auto;
      margin-top: 148px;
      z-index: 8;
    }
  }
}
</style>
