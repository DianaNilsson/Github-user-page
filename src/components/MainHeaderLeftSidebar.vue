<template>
  <nav id="main-header-left-sidebar"></nav>
</template>

<script>
export default {
  name: "MainHeaderLeftSidebar"
};
</script>

<style scoped>
#main-header-left-sidebar {
  position: absolute;
  top: 0;
  left: 0;
  width: 3.5rem;
  height: 100%;
  background-color: rgba(62, 72, 55, 0.3);
  border-right: 2px solid #ffffff;

  /* display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-top: 3.5rem; */

  /* z-index: 1; */
  transition: width 0.3s;
  /* white-space: nowrap; */
}
</style>