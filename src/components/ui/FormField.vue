<template>
  <div class="form-field">
    <input
      v-if="type !== 'tel' && type !== 'file'"
      :value="text"
      @input="handleInput"
      :type="type"
      @focus="isFocused = true"
      @blur="isFocused = false"
    />
    <input
      v-else-if="type === 'tel'"
      :value="text"
      @input="handleInput"
      type="tel"
      v-maska
      data-maska="+7 (###) ###-##-##"
      @focus="isFocused = true"
      @blur="isFocused = false"
    />
    <label
      v-else-if="type === 'file'"
      class="file-upload"
      style="color: #187cd3"
    >
      <span>Загрузить резюме</span>
      <input type="file" @change="handleFileUpload" />
    </label>
    <label class="placeholder" :class="{ active: isFocused || text }">{{
      label
    }}</label>
  </div>
</template>

<script>
import { vMaska } from "maska";
export default {
  props: {
    label: String,
    text: [String, Number],
    type: {
      type: String,
      default: "text",
    },
  },
  directives: { maska: vMaska },
  data() {
    return {
      isFocused: false,
    };
  },
  methods: {
    handleInput(event) {
      this.$emit("update:text", event.target.value);
    },
    handleFileUpload(event) {
      const file = event.target.files[0];
    },
  },
};
</script>

<style scoped lang="scss">
@import "../../assets/scss/_vars.scss";
.form-field {
  position: relative;
  margin-bottom: 32px;
  width: 100%;
}

input {
  width: 100%;
  padding: 10px;
  border: 1px solid $Gray4;
  background-color: $Gray4;
  @include f400;
  font-size: 16px;
  height: 70px;
  outline: none;
}

.placeholder {
  position: absolute;
  left: 10px;
  top: 50%;
  transform: translateY(-50%);
  color: $Gray3;
  @include f400;
  font-size: 16px;
  transition: 0.3s;
  pointer-events: none;
}

.placeholder.active,
input:focus + .placeholder {
  top: 10px;
  font-size: 12px;
}
input[type="date"]:in-range::-webkit-datetime-edit-year-field,
input[type="date"]:in-range::-webkit-datetime-edit-month-field,
input[type="date"]:in-range::-webkit-datetime-edit-day-field,
input[type="date"]:in-range::-webkit-datetime-edit-text {
  color: transparent;
}
.file-upload {
  margin-left: 34px;
  position: relative;
  color: #187cd3;
  display: block;
  margin-top: 10px;
  display: flex;
  justify-content: center;
  padding-bottom: 25px;
  border-bottom: 1px solid #242627;
  input {
    display: none;
  }
  span {
    cursor: pointer;
  }
}
</style>
