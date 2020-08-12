<template>
  <div id="app">
    <main-header></main-header>
    <about-me></about-me>
    <skills></skills>
  </div>
</template>

<script>
// @ is an alias to /src
import MainHeader from "@/components/MainHeader.vue";
import AboutMe from "@/components/AboutMe.vue";
import Skills from "@/components/Skills.vue";

export default {
  components: {
    MainHeader,
    AboutMe,
    Skills
  }
};
</script>

<style>
@import "./assets/css-reset.css";
@import "./assets/css-responsive.css";
</style>
