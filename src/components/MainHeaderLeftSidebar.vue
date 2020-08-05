<template>
  <nav
    id="main-header-left-sidebar"
    :class="{'sidebar-expanded': !sidebarCollapsed, 'sidebar-collapsed': sidebarCollapsed}"
  >
    <button class="menu-bar">
      <img src="../assets/icons/bar.png" alt="menu-bar" @click="menuClick" />
    </button>

    <nav class="social-media-links-container">
      <a href="https://github.com/DianaNilsson">
        <img src="../assets/icons/github.png" alt="Github" />
      </a>
      <a href="https://www.linkedin.com/in/diana-nilsson-7987871a2/">
        <img src="../assets/icons/linkedin.png" alt="LinkedIn" />
      </a>
      <a href>
        <img src="../assets/icons/mail.png" alt="Mail" />
      </a>
    </nav>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      sidebarCollapsed: true
    };
  },

  methods: {
    menuClick() {
      if (this.sidebarCollapsed == true) {
        this.sidebarCollapsed = false;
      } else {
        this.sidebarCollapsed = true;
      }
      // custom event
      this.$emit("sidebar-changed", {
        status: this.sidebarCollapsed
      });
    }
  },
  name: "MainHeaderLeftSidebar"
};
</script>

<style scoped>
#main-header-left-sidebar {
  position: absolute;
  top: 0;
  left: 0;
  width: 3.6rem;
  height: 100%;
  background-color: rgba(62, 72, 55, 0.3);
  border-right: 2px solid #ffffff;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-top: 3.6rem;

  z-index: 1;
  transition: width 0.3s;
  white-space: nowrap;
}

/* Menu bar */
.menu-bar {
  position: absolute;
  top: 0;
  left: 0;
  height: 3.6rem;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  border-bottom: 2px solid #ffffff;
}

.menu-bar img {
  height: 2rem;
  transition: height 0.2s;
}

.menu-bar img:hover {
  height: 2.4rem;
}

.menu-bar:hover {
  background-color: rgba(62, 72, 55, 0.3);
}

/* Social media links */
.social-media-links-container {
  display: flex;
}

.sidebar-collapsed .social-media-links-container:hover {
  background-color: rgba(62, 72, 55, 0.3);
}

.sidebar-collapsed .social-media-links-container {
  padding-top: 1.5rem;
  height: 100%;
  flex-direction: column;
  align-items: center;
}

.sidebar-expanded .social-media-links-container {
  justify-content: center;
  margin-bottom: 0.5rem;
}

.social-media-links-container > a {
  margin: 3.2rem 0.6rem 0;
}

/* .tablet .social-media-links-container > a,
.desktop .social-media-links-container > a {
  margin: 4rem 0.8rem 0 !important;
} */

.social-media-links-container img {
  height: 1.6rem;
  transition: height 0.1s;
}

.social-media-links-container img:hover {
  height: 2rem;
}
</style>