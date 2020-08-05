<template>
  <header id="main-header">
    <main-header-background />
    <main-header-left-sidebar @sidebar-changed="onSidebarChange" />
    <main-header-top-sidebar :sidebar-collapsed="sidebarCollapsed" />
    <main-header-content />
  </header>
</template>

<script>
import MainHeaderBackground from "@/components/MainHeaderBackground.vue";
import MainHeaderContent from "@/components/MainHeaderContent.vue";
import MainHeaderLeftSidebar from "@/components/MainHeaderLeftSidebar.vue";
import MainHeaderTopSidebar from "@/components/MainHeaderTopSidebar.vue";

export default {
  data() {
    return {
      sidebarCollapsed: true
    };
  },
  components: {
    MainHeaderBackground,
    MainHeaderContent,
    MainHeaderLeftSidebar,
    MainHeaderTopSidebar
  },
  methods: {
    onSidebarChange(sidebar) {
      this.sidebarCollapsed = sidebar.status;
    }
  },
  name: "MainHeader"
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