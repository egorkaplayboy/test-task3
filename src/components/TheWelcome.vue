<template>
  <section class="welcome">
    <div class="container">
      <div class="welcome__inner">
        <div class="welcome__info">
          <div class="welcome__info-title">
            Энергия твоего роста! – заряжаем твою карьеру
          </div>
          <div class="welcome__info-button button">
            <button @click="showPopup">Cтать частью команды</button>
          </div>
        </div>
        <div class="welcome_image">
          <img
            src="../assets/img/welcomePeoples.png"
            alt="peoples"
            loading="lazy"
          />
        </div>
      </div>
    </div>
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
  background-image: url(../assets/img/welcomeBg.webp);
  background-position: left;
  background-size: cover;
  overflow: hidden;
  margin-bottom: 76px;
  &__inner {
    display: flex;
    height: 448px;
    align-items: center;
    align-content: space-between;
    position: relative;
  }
  &__info {
    width: 500px;
  }

  &__info-title {
    @include f700;
    font-size: 36px;
    line-height: 42px;
    color: #fff;
    margin-bottom: 56px;
  }

  &__info-button {
    button {
      width: 254px;
      height: 64px;
      background-color: $Orange;
      border: none;
      outline: none;
      cursor: pointer;
      @include f700;
      color: #fff;
      font-size: 16px;
      transition: 0.15s ease;
    }
    button:hover {
      opacity: 0.85;
    }
  }

  &_image {
    align-self: flex-end;
    position: absolute;
    right: -90px;
    bottom: 0px;
    width: 678px;
    height: 430px;

    img {
      width: 100%;
    }
  }
}
</style>
