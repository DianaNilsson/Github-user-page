<template>
  <div id="app">
    <main-header></main-header>
    <about-me></about-me>
  </div>
</template>

<script>
// @ is an alias to /src
import MainHeader from "@/components/MainHeader.vue";
import AboutMe from "@/components/AboutMe.vue";

export default {
  components: {
    MainHeader,
    AboutMe
  }
};
</script>

<style>
@import "./assets/css-reset.css";
@import "./assets/css-responsive.css";
</style>
