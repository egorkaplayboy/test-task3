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
</template>
<script>
export default {};
</script>
<style lang="scss">
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
</style>
