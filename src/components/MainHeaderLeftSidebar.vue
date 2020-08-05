<template>
  <nav
    id="main-header-left-sidebar"
    :class="{'sidebar-expanded': !sidebarCollapsed, 'sidebar-collapsed': sidebarCollapsed}"
  >
    <button class="menu-bar" @click="menuClick">
      <img src="../assets/icons/bar.png" alt="menu-bar" />
    </button>

    <transition name="fade">
      <nav class="page-nav flex" v-if="!sidebarCollapsed">
        <a href>
          <img src="../assets/icons/user.png" alt="Om mig" />Om mig
        </a>
        <a href>
          <img src="../assets/icons/skills.png" alt="Skills" />Skills
        </a>
        <a href>
          <img src="../assets/icons/project.png" alt="Projekt" />Projekt
        </a>
        <a href>
          <img src="../assets/icons/mail.png" alt="Kontakt" />Kontakt
        </a>
      </nav>
    </transition>

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

.sidebar-expanded {
  width: 11rem !important;
}

/* Menu bar */
.menu-bar {
  position: absolute;
  top: 0;
  left: 0;
  height: 3.6rem;
  width: 100%;
  display: flex;
  align-items: center;
  border-bottom: 2px solid #ffffff;
}

.menu-bar img {
  height: 2rem;
  margin-left: 0.8rem;
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
  height: 1.5rem;
  transition: height 0.1s;
}

.social-media-links-container img:hover {
  height: 2rem;
}

/* Page navigation */
.page-nav {
  display: flex;
  padding-top: 1.5rem;
  flex-direction: column;
  margin-top: 1rem;
}

.page-nav > a {
  display: flex;
  align-items: flex-end;
  padding: 0.5rem;
  padding-left: 1rem;
  margin-top: 1rem;
  color: #fff;
  font-size: 1rem;
  font-weight: 300;
}

.tablet .page-nav > a,
.desktop .page-nav > a {
  margin-top: 2rem !important;
}

.page-nav > a:hover {
  background-color: rgba(62, 72, 55, 0.4);
}

.page-nav img {
  height: 1.4rem;
  margin-right: 0.7rem;
}

/* Vue transitions for page navigation */
.fade-enter-active {
  transition: opacity 1s;
}
.fade-enter {
  opacity: 0;
}
</style>