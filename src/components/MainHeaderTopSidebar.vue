<template>
  <header id="top-sidebar" :class="{'position-left': !sidebarCollapsed}">
    <p>Diana Nilsson | Frontendutvecklare</p>
  </header>
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
#top-sidebar {
  position: absolute;
  top: 0;
  left: 3.6rem;
  width: 100%;
  height: 3.6rem;
  display: flex;
  align-items: center;
  padding: 0 5rem;
  background-color: rgba(62, 72, 55, 0.3);
  border-bottom: 2px solid #ffffff;

  transition: left 0.3s;
  white-space: nowrap;
}

#top-sidebar:hover {
  background-color: rgba(62, 72, 55, 0.4);
}

#top-sidebar > p {
  color: #ffffff;
  font-size: 1.2rem;
  font-weight: 300;
  letter-spacing: 2px;
  text-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25);
}

/* If sidebar expanded */
.position-left {
  left: 11rem !important;
}
</style>