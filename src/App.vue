<template>
  <div id="app">
    <main-header></main-header>
    <about-me></about-me>
    <skills></skills>
    <projects></projects>
  </div>
</template>

<script>
// @ is an alias to /src
import MainHeader from "@/components/MainHeader.vue";
import AboutMe from "@/components/AboutMe.vue";
import Skills from "@/components/Skills.vue";
import Projects from "@/components/Projects.vue";

export default {
  components: {
    MainHeader,
    AboutMe,
    Skills,
    Projects
  }
};
</script>

<style>
@import "./assets/css-reset.css";
@import "./assets/css-responsive.css";
</style>
