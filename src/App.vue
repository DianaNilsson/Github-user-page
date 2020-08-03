<template>
  <div id="app">
    <main-header></main-header>
  </div>
</template>

<script>
// @ is an alias to /src
import MainHeader from "@/components/MainHeader.vue";

export default {
  components: {
    MainHeader
  }
};
</script>

<style>
@import "./assets/css-reset.css";
@import "./assets/css-responsive.css";
</style>
