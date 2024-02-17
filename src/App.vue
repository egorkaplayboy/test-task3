<template>
  <div>
    <div class="container">
      <TheHeader />
    </div>
    <TheWelcome />
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheWelcome from "./components/TheWelcome.vue";
export default {
  components: {
    TheHeader,
    TheWelcome,
  },
};
</script>
<style scoped lang="scss"></style>
