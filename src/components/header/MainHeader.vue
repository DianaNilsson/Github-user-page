<template>
  <header id="main-header">
    <header-background />
    <header-content />
  </header>
</template>

<script>
import HeaderBackground from "@/components/header/HeaderBackground.vue";
import HeaderContent from "@/components/header/HeaderContent.vue";

export default {
  components: {
    HeaderBackground,
    HeaderContent
  }
};
</script>

<style scoped>
#main-header {
  position: relative;
  height: 100vh;
  width: 100vw;
  border-bottom: 6px solid #f3b265;

  display: flex;
  justify-content: center;
  align-items: center;
}
</style>