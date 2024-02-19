<template>
  <section class="slider">
    <div class="slider__wrapper">
      <div class="slider__item" :key="sliderData[currentSlide].id">
        <button @click="prevSlide" class="slider__button">
          <svg class="slider__item-svg prev">
            <use xlink:href="../assets/svg_sprite/sprite.svg#arrow_slide"></use>
          </svg>
        </button>
        <div class="slider__item-desc">
          <h3>{{ sliderData[currentSlide].name }}</h3>
          <p>{{ sliderData[currentSlide].grade }}</p>
          <span>{{ sliderData[currentSlide].desc }}</span>
        </div>
        <div class="slider__item-img">
          <img
            :src="`/src/assets/img/${sliderData[currentSlide].imgUrl}`"
            alt="employee"
            loading="lazy"
          />
        </div>
        <button @click="nextSlide" class="slider__button">
          <svg class="slider__item-svg">
            <use xlink:href="../assets/svg_sprite/sprite.svg#arrow_slide"></use>
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      sliderData: [
        {
          id: 1,
          name: "Евдокимова Майя",
          grade: "Генеральный директор",
          desc: "Цель нашей работы обеспечить высочайший сервис нашим клиентам. Дать возможность бизнесу сосредоточиться на своих ключевых задачах, передав функции управления персоналом, казначейства, финансового учёта и отчётности нам.",
          imgUrl: "director.png",
        },
        {
          id: 2,
          name: "2",
          grade: "Генеральный директор",
          desc: "Цель нашей работы обеспечить высочайший сервис нашим клиентам. Дать возможность бизнесу сосредоточиться на своих ключевых задачах, передав функции управления персоналом, казначейства, финансового учёта и отчётности нам.",
          imgUrl: "director.png",
        },
        {
          id: 3,
          name: "3",
          grade: "Генеральный директор",
          desc: "Цель нашей работы обеспечить высочайший сервис нашим клиентам. Дать возможность бизнесу сосредоточиться на своих ключевых задачах, передав функции управления персоналом, казначейства, финансового учёта и отчётности нам.",
          imgUrl: "director.png",
        },
      ],
      currentSlide: 0,
    };
  },
  methods: {
    /**
     * Переключает на предыдущий слайд в слайдере.
     * Если текущий слайд - первый, переключает на последний слайд.
     */
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      } else {
        // Если текущий слайд первый, переключаем на последний слайд
        this.currentSlide = this.sliderData.length - 1;
      }
    },

    /**
     * Переключает на следующий слайд в слайдере.
     * Если текущий слайд - последний, переключает на первый слайд.
     */
    nextSlide() {
      if (this.currentSlide < this.sliderData.length - 1) {
        this.currentSlide++;
      } else {
        // Если текущий слайд последний, переключаем на первый слайд
        this.currentSlide = 0;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/_vars.scss";
.slider {
  max-width: 1480px;
  height: 446px;
  width: 100%;
  overflow: hidden;
  margin: 70px auto;
  &__wrapper {
    display: flex;
  }
  &__button {
    outline: none;
    border: 1px solid $Gray;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 94px;
    margin: 0 50px;
    background-color: transparent;
    transition: 0.2s ease;
    &:hover {
      border: none;
      background-color: #fff;
    }
  }
  &__item {
    width: 100%;
    background-color: $WhiteBg;
    display: flex;
    align-items: center;
    justify-content: space-around;
    padding: 0 40px;
    transition: transform 0.5s;
  }
  &__item-svg {
    width: 10px;
    height: 8px;
    padding: 0 23px;
    &.prev {
      transform: rotate(180deg);
    }
  }
  &__item-desc {
    h3 {
      font-size: 36px;
      @include f400;
      color: $Dark;
    }
    p {
      margin-top: 20px;
      margin-bottom: 40px;
      @include f400;
      font-size: 16px;
      color: $Gray3;
    }
    span {
      @include f400;
      font-size: 18px;
      color: $Dark;
    }
  }
}
</style>
