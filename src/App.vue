<template>
  <div id="app">
    <main-header></main-header>
  </div>
</template>

<script>
// @ is an alias to /src
import MainHeader from "@/components/header/MainHeader.vue";

export default {
  components: {
    MainHeader
  }
};
</script>

<style>
/* Global CSS rules */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
  color: #1a1a1a;
  text-decoration: none;
  overflow-x: hidden;
  font-family: "Roboto", sans-serif;
}
</style>
