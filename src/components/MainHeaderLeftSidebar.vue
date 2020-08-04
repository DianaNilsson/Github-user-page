<template>
  <nav
    id="main-header-left-sidebar"
    :class="{'sidebar-expanded': !sidebarCollapsed, 'sidebar-collapsed': sidebarCollapsed}"
  >
    <button class="menu-bar">
      <img src="../assets/icons/bar.png" alt="menu-bar" @click="menuClick" />
    </button>
  </nav>
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

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-top: 3.5rem;

  z-index: 1;
  transition: width 0.3s;
  white-space: nowrap;
}

/* Menu bar */
.menu-bar {
  position: absolute;
  top: 0;
  left: 0;
  height: 3.5rem;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  border-bottom: 2px solid #ffffff;
}

.menu-bar img {
  height: 2rem;
  transition: height 0.1s;
}

.menu-bar img:hover {
  height: 2.2rem;
}
</style>