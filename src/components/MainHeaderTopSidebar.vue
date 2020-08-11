<template>
  <aside id="main-header-top-sidebar" :class="{'sidebar-expanded': !sidebarCollapsed}">
    <p>Diana Nilsson | Frontendutvecklare</p>
  </aside>
</template>

<script>
export default {
  name: "MainHeaderTopSidebar",
  props: {
    sidebarCollapsed: {
      type: Boolean
    }
  }
};
</script>

<style scoped>
#main-header-top-sidebar {
  position: absolute;
  top: 0;
  left: 3.6rem;
  width: 100%;
  height: 3.6rem;
  display: flex;
  align-items: center;
  padding: 0 5rem;
  background-color: rgba(51, 51, 51, 0.4);
  border-bottom: 2px solid #ffffff;

  transition: left 0.3s;
  white-space: nowrap;
}

#main-header-top-sidebar > p {
  color: #ffffff;
  font-size: 1.2rem;
  font-weight: 300;
  letter-spacing: 0.125rem;
  text-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25);
}

/* If sidebar expanded */
.sidebar-expanded {
  left: 11rem !important;
}

/* Responsiveness */
@media only screen and (max-width: 450px) and (orientation: portrait),
  only screen and (max-width: 850px) and (max-height: 450px) {
  #main-header-top-sidebar {
    display: none;
  }
}
</style>