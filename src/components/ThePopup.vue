<template>
  <div class="popup">
    <div class="popup-content">
      <svg class="close-btn" @click="closePopup">
        <use xlink:href="/src/assets/svg_sprite/sprite.svg#close"></use>
      </svg>
      <div class="popup-content__wrapper">
        <h2 class="popup-content__title">Отклик на вакансию</h2>
        <form @submit.prevent class="popup-content__form">
          <div class="popup-content__form-item">
            <form-field
              label="Желаемая вакансия *"
              type="text"
              :text="vacancy"
              @update:text="vacancy = $event"
            />
          </div>
          <div class="popup-content__form-item">
            <form-field
              label="Фамилия, имя и отчество *"
              type="text"
              :text="fio"
              @update:text="fio = $event"
            />
          </div>
          <div class="popup-content__form-item flex">
            <form-field
              label="Мобильный телефон*"
              type="tel"
              :text="phone"
              @update:text="phone = $event"
            />
            <form-field
              label="E-mail"
              type="email"
              :text="email"
              @update:text="email = $event"
            />
          </div>
          <div class="popup-content__form-item">
            <form-field
              label="Образование *"
              type="text"
              :text="education"
              @update:text="education = $event"
            />
          </div>
          <div class="popup-content__form-item">
            <form-field
              label="Адрес места жительства *"
              type="text"
              :text="adress"
              @update:text="adress = $event"
            />
          </div>
          <div class="popup-content__form-item flex">
            <form-field
              label="Дата рождения"
              type="date"
              :text="date"
              @update:text="date = $event"
            />
            <form-field
              label=""
              type="file"
              :text="date"
              @update:text="date = $event"
            />
          </div>
          <div class="popup-content__form-item">
            <form-field
              label="Комментарий"
              type="text"
              :text="comment"
              @update:text="comment = $event"
            />
          </div>
          <div class="popup-content__form-agree">
            <label style="display: flex">
              <input type="checkbox" />
              <p>
                Я принимаю условия
                <a href="#" style="text-decoration: none"
                  >передачи информации</a
                >
              </p>
            </label>
            <button
              class="form-button__button"
              :class="{ 'form-button__button--disabled': hasErrors }"
              @click="submitForm"
              :disabled="hasErrors"
            >
              Отправить
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { useVuelidate } from "@vuelidate/core";
import { required, email } from "@vuelidate/validators";
import FormField from "./ui/FormField.vue";
export default {
  components: {
    FormField,
  },
  data() {
    return {
      v$: useVuelidate(),
      vacancy: "",
      fio: "",
      phone: "",
      email: "",
      education: "",
      adress: "",
      date: "",
      comment: "",
    };
  },
  validations() {
    return {
      vacancy: { required },
      fio: { required },
      phone: { required },
      email: { required, email },
      education: { required },
      adress: { required },
    };
  },
  computed: {
    hasErrors() {
      this.v$.$validate();
      return this.v$.$error;
    },
  },
  methods: {
    closePopup() {
      this.$emit("close");
    },
    submitForm() {
      this.v$.$validate();
      if (!this.v$.$error) {
        // Если обязательные поля заполнены
        alert("success");
      } else {
        alert("fail");
      }
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/_vars.scss";
.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 199;

  &-content {
    background-color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 200;
    width: 1145px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    position: relative;
    &__wrapper {
      max-width: 712px;
      max-height: 90vh;
      overflow-y: auto;
      overflow-x: hidden;
    }
    &__title {
      align-self: start;
      @include f700;
      font-size: 36px;
      margin-bottom: 57px;
      margin-top: 104px;
    }
    &__form {
      display: flex;
      flex-direction: column;
      &-agree {
        display: flex;
        justify-content: space-between;
        align-items: center;
        border: 1px solid $Gray4;
        padding: 38px 34px;
      }
      &-item {
        margin-bottom: 32px;
        &.flex {
          display: flex;
          align-items: center;
          justify-content: space-between;
          width: 100%;
          gap: 5px;
          span {
            color: $Blue;
          }
        }
      }
    }
  }

  & .close-btn {
    cursor: pointer;
    width: 12px;
    height: 12px;
    padding: 29px;
    fill: #fff;
    background-color: $Orange;
    position: absolute;
    right: 0;
    top: 0;
    z-index: 5;
  }
}
.form-button__button {
  padding: 22px 63px;
  font-size: 16px;
  line-height: 17px;
  color: #fff;
  text-align: center;
  border-radius: 0;
  border: none;
  outline: none;
  background: #e9862a;
  cursor: pointer;

  &--disabled {
    background: #c3c8c8;
    padding: 22px 63px;
    font-size: 16px;
    line-height: 17px;
    color: #fff;
    text-align: center;
    border-radius: 0;
    border: none;
    outline: none;
    pointer-events: none;
    &:hover {
      background: #c3c8c8;
    }
  }

  &:hover {
    background: #e77e1e;
  }
}
.popup-content__wrapper::-webkit-scrollbar {
  width: 0; /* убираем скроллбар в вебките браузерах (Chrome, Safari) */
}

.popup-content__wrapper {
  -ms-overflow-style: none; /* убираем скроллбар в Internet Explorer и Edge */
}
.popup-content__form-agree {
  margin-bottom: 65px;
}
</style>
