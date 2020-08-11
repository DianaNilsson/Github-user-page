<template>
  <header id="main-header">
    <main-header-background />
    <main-header-left-sidebar @sidebar-changed="onSidebarChange" />
    <main-header-top-sidebar :sidebar-collapsed="sidebarCollapsed" />
    <main-header-content />
    <div class="main-header-border-right"></div>
    <div class="main-header-border-bottom"></div>
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
  border-bottom: 6px solid #588c7e;

  display: flex;
  justify-content: center;
  align-items: center;

  overflow: hidden;
}

.main-header-border-right {
  position: absolute;
  right: 0;
  height: 68vh;
  width: 2rem;
  border-left: 1px solid #fff;
}

.main-header-border-bottom {
  position: absolute;
  bottom: 0;
  height: 1.5rem;
  width: 68vw;
  border-top: 1px solid #fff;
}
</style>