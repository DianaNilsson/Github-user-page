<template>
  <header id="main-header">
    <header-background />
  </header>
</template>

<script>
import HeaderBackground from "@/components/header/HeaderBackground.vue";
export default {
  components: {
    HeaderBackground
  }
};
</script>

<style scoped>
#main-header {
  position: relative;
  height: 100vh;
  width: 100vw;
  border-bottom: 6px solid #f59a55;
}
</style>