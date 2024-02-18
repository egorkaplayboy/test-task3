<template>
  <div>
    <div class="container">
      <TheHeader />
    </div>
    <TheWelcome />
    <div class="container">
      <TheQualities />
    </div>
    <TheSlider />
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheWelcome from "./components/TheWelcome.vue";
import TheQualities from "./components/TheQualities.vue";
import TheSlider from "./components/TheSlider.vue";
export default {
  components: {
    TheHeader,
    TheWelcome,
    TheQualities,
    TheSlider,
  },
};
</script>
<style scoped lang="scss"></style>
