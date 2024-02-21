<template>
  <section class="qualities">
    <ul class="qualities__list">
      <li class="qualities__item">
        <div>
          <svg class="qualities__item-img" style="width: 66px">
            <use
              xlink:href="../assets/svg_sprite/sprite.svg#career_ladder"
            ></use>
          </svg>
        </div>
        <div class="qualities__item-desc">
          <h3>Развитие</h3>
          <span
            >Общего центра обслуживания. Современные технологии, проекты,
            рабочие группы</span
          >
        </div>
      </li>
      <li class="qualities__item">
        <div>
          <svg class="qualities__item-img" style="width: 66px">
            <use xlink:href="../assets/svg_sprite/sprite.svg#study"></use>
          </svg>
        </div>
        <div class="qualities__item-desc">
          <h3>Обучение</h3>
          <span
            >Общего центра обслуживания. Современные технологии, проекты,
            рабочие группы</span
          >
        </div>
      </li>
      <li class="qualities__item">
        <div>
          <svg class="qualities__item-img" style="width: 68px">
            <use xlink:href="../assets/svg_sprite/sprite.svg#blocks"></use>
          </svg>
        </div>
        <div class="qualities__item-desc">
          <h3>Ответственность</h3>
          <span
            >Общего центра обслуживания. Современные технологии, проекты,
            рабочие группы</span
          >
        </div>
      </li>
      <li class="qualities__item">
        <div>
          <svg class="qualities__item-img" style="width: 93px">
            <use xlink:href="../assets/svg_sprite/sprite.svg#dinamic"></use>
          </svg>
        </div>
        <div class="qualities__item-desc">
          <h3>Динамика</h3>
          <span
            >Общего центра обслуживания. Современные технологии, проекты,
            рабочие группы</span
          >
        </div>
      </li>
      <li class="qualities__item">
        <div>
          <svg class="qualities__item-img" style="width: 72px">
            <use xlink:href="../assets/svg_sprite/sprite.svg#comfort"></use>
          </svg>
        </div>
        <div class="qualities__item-desc">
          <h3>Комфорт</h3>
          <span
            >Общего центра обслуживания. Современные технологии, проекты,
            рабочие группы</span
          >
        </div>
      </li>
      <li class="qualities__item">
        <div>
          <svg class="qualities__item-img" style="width: 54px">
            <use xlink:href="../assets/svg_sprite/sprite.svg#security"></use>
          </svg>
        </div>
        <div class="qualities__item-desc">
          <h3>Надежность</h3>
          <span
            >Общего центра обслуживания. Современные технологии, проекты,
            рабочие группы</span
          >
        </div>
      </li>
    </ul>
  </section>
  <section class="qualities-table">
    <swiper :slides-per-view="1" :space-between="50">
      <swiper-slide>
        <ul class="qualities__list-table">
          <li class="qualities__item-table">
            <div>
              <svg class="qualities__item-img-table" style="width: 66px">
                <use
                  xlink:href="../assets/svg_sprite/sprite.svg#career_ladder"
                ></use>
              </svg>
            </div>
            <div class="qualities__item-desc-table">
              <h3>Развитие</h3>
              <span
                >Общего центра обслуживания. Современные технологии, проекты,
                рабочие группы</span
              >
            </div>
          </li>
          <li class="qualities__item-table">
            <div>
              <svg class="qualities__item-img-table" style="width: 66px">
                <use xlink:href="../assets/svg_sprite/sprite.svg#study"></use>
              </svg>
            </div>
            <div class="qualities__item-desc-table">
              <h3>Обучение</h3>
              <span
                >Общего центра обслуживания. Современные технологии, проекты,
                рабочие группы</span
              >
            </div>
          </li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <ul class="qualities__list-table">
          <li class="qualities__item-table">
            <div>
              <svg class="qualities__item-img-table" style="width: 68px">
                <use xlink:href="../assets/svg_sprite/sprite.svg#blocks"></use>
              </svg>
            </div>
            <div class="qualities__item-desc-table">
              <h3>Ответственность</h3>
              <span
                >Общего центра обслуживания. Современные технологии, проекты,
                рабочие группы</span
              >
            </div>
          </li>
          <li class="qualities__item-table">
            <div>
              <svg class="qualities__item-img-table" style="width: 93px">
                <use xlink:href="../assets/svg_sprite/sprite.svg#dinamic"></use>
              </svg>
            </div>
            <div class="qualities__item-desc-table">
              <h3>Динамика</h3>
              <span
                >Общего центра обслуживания. Современные технологии, проекты,
                рабочие группы</span
              >
            </div>
          </li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <ul class="qualities__list-table">
          <li class="qualities__item-table">
            <div>
              <svg class="qualities__item-img-table" style="width: 72px">
                <use xlink:href="../assets/svg_sprite/sprite.svg#comfort"></use>
              </svg>
            </div>
            <div class="qualities__item-desc-table">
              <h3>Комфорт</h3>
              <span
                >Общего центра обслуживания. Современные технологии, проекты,
                рабочие группы</span
              >
            </div>
          </li>
          <li class="qualities__item-table">
            <div>
              <svg class="qualities__item-img-table" style="width: 54px">
                <use
                  xlink:href="../assets/svg_sprite/sprite.svg#security"
                ></use>
              </svg>
            </div>
            <div class="qualities__item-desc-table">
              <h3>Надежность</h3>
              <span
                >Общего центра обслуживания. Современные технологии, проекты,
                рабочие группы</span
              >
            </div>
          </li>
        </ul>
      </swiper-slide>
    </swiper>
  </section>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/scss";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
};
</script>
<style lang="scss" scoped>
@import "../assets/scss/_vars.scss";
.qualities {
  &__list {
    list-style-type: none;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    margin: 0;
    padding: 0;
  }
  &__item-img {
    height: 70px;
    fill: $Dark;
    stroke: $Dark;
    margin-bottom: 44px;
  }
  &__item {
    border: 1px solid $Gray2;
    height: 377px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 50px;
    &:hover {
      border: none;
      @include shadow;
      background-color: #fff;
    }
    &:hover .qualities__item-desc span {
      opacity: 1;
    }
    &:hover .qualities__item-img {
      fill: $Orange;
      stroke: $Orange;
    }
  }
  &__item-desc {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    h3 {
      @include f400;
      font-size: 20px;
      line-height: 26px;
      color: $Dark;
      text-align: center;
      width: 100%;
    }

    span {
      @include f400;
      color: $Stroke;
      font-size: 16px;
      margin-top: 10px;
      opacity: 0;
      max-height: 0;
      text-align: center;
      transition: opacity 0.2s;
    }
  }
}

// Media

@media (min-width: 1201px) {
  .qualities-table {
    display: none;
  }
}
@media (max-width: 1200px) {
  .qualities {
    display: none;
  }
  .qualities__list-table {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .qualities__item-table {
    height: 345px;
    width: 345px;
    padding: 60px 24px;
    border: 1px solid $Gray2;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    &:hover {
      border: none;
      @include shadow;
      background-color: #fff;
    }
    &:hover .qualities__item-desc-table span {
      opacity: 1;
    }
    &:hover .qualities__item-img-table {
      fill: $Orange;
      stroke: $Orange;
    }
  }
  .qualities__item-desc-table {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    h3 {
      @include f400;
      font-size: 20px;
      line-height: 26px;
      color: $Dark;
      text-align: center;
      width: 100%;
    }

    span {
      @include f400;
      color: $Stroke;
      font-size: 16px;
      margin-top: 10px;
      opacity: 0;
      max-height: 0;
      text-align: center;
      transition: opacity 0.2s;
    }
  }
  .qualities__item-img-table {
    height: 70px;
    fill: $Dark;
    stroke: $Dark;
    margin-bottom: 44px;
  }
}
@media (max-width: 320px) {
  .qualities {
    display: none;
  }
  .qualities-table {
    display: none;
  }
}
</style>
