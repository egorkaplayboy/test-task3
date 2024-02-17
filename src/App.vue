<template>
  <div>
    <div class="container">
      <TheHeader />
    </div>
    <TheWelcome />
    <div class="container">
      <TheQualities />
    </div>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheWelcome from "./components/TheWelcome.vue";
import TheQualities from "./components/TheQualities.vue";
export default {
  components: {
    TheHeader,
    TheWelcome,
    TheQualities,
  },
};
</script>
<style scoped lang="scss"></style>
