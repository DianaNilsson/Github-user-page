<template>
  <section class="projects">
    <h2>Projekt</h2>

    <!-- Filter bar -->
    <ul class="filter-projects-bar">
      <li :class="{'active':filterProjects.all}" @click="filterAll">Alla</li>
      <li
        :class="{'active':filterProjects.type}"
        @click="filterType"
      >Projekttyp{{filterProjects.type}}</li>
      <li :class="{'active':filterProjects.tool}" @click="filterTool">Verktyg{{filterProjects.tool}}</li>
    </ul>

    <!-- Select project type list -->
    <transition name="fade">
      <ul class="project-type-list" v-if="chooseProjectType">
        <li
          v-for="projectType in projectTypes"
          :key="projectType"
          @click="selectProjectType($event.target.innerHTML)"
        >{{projectType}}</li>
      </ul>

      <!-- Select project tool list -->
      <ul class="project-tool-list" v-if="chooseProjectTool" :class="{'wide': filterProjects.type}">
        <li
          v-for="projectTool in projectTools"
          :key="projectTool"
          @click="selectProjectTool($event.target.innerHTML)"
        >{{projectTool}}</li>
      </ul>
    </transition>

    <!-- Render projects - all -->
    <section class="projects-container" v-if="filterProjects.all">
      <article v-for="project in projects" :key="project.id">
        <div class="project-links-container">
          <img :src="require(`../assets/projects/${project.img[0]}`)" :alt="`${project.name}`" />
          <a href class="project-link website-link">
            <font-awesome-icon :icon="['fas', 'globe']" />
            <span class="link-name">Webbsida</span>
          </a>
          <a href class="project-link github-link">
            <font-awesome-icon :icon="['fab', 'github']" />
            <span class="link-name">Github repo</span>
          </a>
        </div>
        <h4>{{project.type}}</h4>
        <h3>{{project.name}}</h3>
        <p>
          <span v-for="tool in project.tools" :key="tool">{{tool}} |&nbsp;</span>
        </p>
      </article>
    </section>

    <!-- Render projects - filter on types -->
    <section class="projects-container" v-if="filterProjects.type">
      <article v-for="project in computedType" :key="project.id"></article>
    </section>
  </section>
</template>


<script>
export default {
  name: "Projects",
  components: {},
  computed: {
    computedType() {
      return this.projects.filter(project => project.type == "Skolprojekt");
    }
  },
  data() {
    return {
      filterProjects: {
        all: true,
        type: "",
        tool: ""
      },
      chooseProjectTool: false,
      chooseProjectType: false,
      projects: [
        {
          id: 1,
          img: ["1.1-hamsterwars.jpg", "1.2-hamsterwars.jpg"],
          name: "Hamsterwars",
          type: "Skolprojekt",
          tools: [
            "React",
            "JavaScript",
            "HTML",
            "CSS",
            "Node.js",
            "Express.js",
            "Github",
            "Firestore",
            "Heroku"
          ],
          link: "https://hamsterwars-app.herokuapp.com/",
          github: "https://github.com/DianaNilsson/hamsterwars-app"
        },
        {
          id: 2,
          img: ["1.1-hamsterwars.jpg", "1.2-hamsterwars.jpg"],
          name: "Hamsterwars 2.0",
          type: "Eget arbete",
          tools: ["React", "JavaScript", "HTML"],
          link: "https://hamsterwars-app.herokuapp.com/",
          github: "https://github.com/DianaNilsson/hamsterwars-app"
        },
        {
          id: 3,
          img: ["1.1-hamsterwars.jpg", "1.2-hamsterwars.jpg"],
          name: "Hamsterwars 2.0",
          type: "Eget arbete",
          tools: ["React", "JavaScript", "HTML"],
          link: "https://hamsterwars-app.herokuapp.com/",
          github: "https://github.com/DianaNilsson/hamsterwars-app"
        },
        {
          id: 4,
          img: ["1.1-hamsterwars.jpg", "1.2-hamsterwars.jpg"],
          name: "Hamsterwars 2.0",
          type: "Eget arbete",
          tools: ["React", "JavaScript", "HTML"],
          link: "https://hamsterwars-app.herokuapp.com/",
          github: "https://github.com/DianaNilsson/hamsterwars-app"
        },
        {
          id: 5,
          img: ["1.1-hamsterwars.jpg", "1.2-hamsterwars.jpg"],
          name: "Hamsterwars 2.0",
          type: "Eget arbete",
          tools: ["React", "JavaScript", "HTML"],
          link: "https://hamsterwars-app.herokuapp.com/",
          github: "https://github.com/DianaNilsson/hamsterwars-app"
        }
      ],
      projectTools: [
        "React",
        "JavaScript",
        "HTML",
        "CSS",
        "Node.js",
        "Express.js",
        "Github",
        "Firestore",
        "Heroku"
      ],
      projectTypes: [
        "Skolprojekt",
        "Eget Projekt",
        "Skarpt projekt",
        "Teamwork"
      ]
    };
  },
  methods: {
    filterAll() {
      this.filterProjects.all = true;
      this.filterProjects.type = "";
      this.filterProjects.tool = "";
      this.chooseProjectTool = false;
      this.chooseProjectType = false;
    },
    filterTool() {
      if (this.chooseProjectTool) {
        this.chooseProjectTool = false;
      } else {
        this.chooseProjectType = false;
        this.chooseProjectTool = true;
      }
    },
    filterType() {
      if (this.chooseProjectType) {
        this.chooseProjectType = false;
      } else {
        this.chooseProjectTool = false;
        this.chooseProjectType = true;
      }
    },
    selectProjectTool(tool) {
      this.filterProjects.all = false;
      this.filterProjects.type = "";
      this.filterProjects.tool = ": " + tool;
      this.chooseProjectTool = false;
    },
    selectProjectType(type) {
      this.filterProjects.all = false;
      this.filterProjects.type = ": " + type;
      this.filterProjects.tool = "";
      this.chooseProjectType = false;
    }
  }
};
</script>

<style scoped>
.projects {
  width: 90vw;
  margin: auto;
  margin-bottom: 30rem;
  position: relative;
}
.projects h2 {
  font-size: 2.8rem;
  font-weight: 300;
  color: #c43b3b;
  margin-bottom: 5rem;
  text-align: center;
}
.filter-projects-bar {
  display: flex;
  list-style: none;
  border-bottom: 1px solid #b5b2b2;
  overflow: visible;
}

.filter-projects-bar li {
  padding-bottom: 0.8rem;
  margin-right: 2rem;
  font-size: 16px;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: #b5b2b2;
  cursor: pointer;
}

.filter-projects-bar li:first-of-type {
  width: 3rem;
  text-align: center;
}

.filter-projects-bar li:nth-of-type(2) {
  width: 8rem;
  text-align: center;
}

.active:nth-child(2) {
  width: 18.5rem !important;
}

.active {
  color: #333333 !important;
  border-bottom: 3px solid #c43b3b;
  margin-bottom: -1.5px !important;
}

.project-type-list,
.project-tool-list {
  position: absolute;
  z-index: 2;
  background-color: rgba(51, 51, 51, 0.8);
  width: 10rem;
  list-style: none;
  padding: 1rem 0;
  display: flex;
  flex-direction: column;
}

.project-type-list {
  left: 5rem;
}
.project-tool-list {
  left: 15rem;
}
.wide {
  left: 25.5rem !important;
}

.project-type-list li,
.project-tool-list li {
  color: #b5b2b2;
  font-weight: 400;
  letter-spacing: 1px;
  padding: 0.5rem 1rem;
  margin: 0.2rem 0;
  cursor: pointer;
}

.project-type-list li:hover,
.project-tool-list li:hover {
  color: #fff;
}

.projects-container {
  display: flex;
  flex-wrap: wrap;
}

.projects-container article {
  width: 33.33%;
  margin-top: 3rem;
}

.projects-container article:nth-of-type(3n + 1) {
  padding-right: 1.6rem;
}
.projects-container article:nth-of-type(3n + 2) {
  padding: 0 0.8rem;
}
.projects-container article:nth-of-type(3n + 3) {
  padding-left: 1.6rem;
}

.project-links-container {
  position: relative;
  margin-bottom: 0.8rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.projects-container img {
  width: 100%;
  height: 13rem;
  object-fit: cover;
  border: 0.5px solid #fff;
  border-radius: 2px;
  box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25);
}

.projects-container img:hover {
  opacity: 0.8;
}

.project-links-container:hover .project-link,
.project-link:hover {
  background-color: #fff !important;
}

.projects-container .link-name {
  display: none;
}

.project-links-container:hover .link-name {
  display: inline;
}

.projects-container h4 {
  font-size: 0.8rem;
  font-weight: 300;
  text-transform: uppercase;
  letter-spacing: 1px;
  padding-bottom: 0.6rem;
}

.projects-container h3 {
  font-size: 1.1rem;
  font-weight: 400;
  letter-spacing: 0.5px;
  padding-bottom: 0.4rem;
}

.projects-container span {
  font-size: 14px;
  font-weight: 300;
  letter-spacing: 0.5px;
}

.projects-container .project-link {
  position: absolute;
  z-index: 1;
  background-color: rgba(255, 255, 255, 0.6);
  border: 0.1px solid rgba(255, 255, 255, 0);
  border-radius: 50px;
  display: flex;
  align-items: center;
}

.website-link {
  left: 5%;
  top: 10%;
}

.github-link {
  left: 5%;
  top: 30%;
}

.projects-container svg {
  font-size: 2rem;
  padding: 0.4rem;
}

.projects-container path {
  fill: #404040;
}

/* Transitions */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>