<template>
  <section class="projects">
    <h2>Projekt</h2>
    <ul class="choose-projects-list">
      <li :class="{'active':filterProjects.all}" @click="filterAll">Alla</li>
      <li
        :class="{'active':filterProjects.type}"
        @click="filterType"
      >Projekttyp{{selectedProjectType}}</li>
      <li :class="{'active':filterProjects.tools}">Verktyg</li>
    </ul>

    <!-- Project types list -->
    <ul class="project-type-list" v-if="showProjectTypes">
      <li
        v-for="projectType in projectTypes"
        :key="projectType"
        @click="selectProjectType($event.target.innerHTML)"
      >{{projectType}}</li>
    </ul>

    <!-- project tools list -->
    <ul class="project-type-list" v-if="showProjectTools">
      <li></li>
    </ul>

    <!-- Render projects -->
    <div v-for="project in projects" :key="project.id">
      <h2>{{project.name}}</h2>
    </div>

    <!-- <img :src="test" alt /> -->
    <!-- <img :src="require(`../assets/projects/${projects[0].img[0]}`)" alt="hamsterwars" /> -->
    <project-card />
  </section>
</template>


<script>
import ProjectCard from "./ProjectCard.vue";

export default {
  name: "Projects",
  components: {
    ProjectCard
  },
  data() {
    return {
      filterProjects: {
        all: true,
        type: false,
        tools: false
      },
      test: require("../assets/projects/1.1-hamsterwars.jpg"),
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
          type: "Skolprojekt",
          tools: ["React", "JavaScript", "HTML"],
          link: "https://hamsterwars-app.herokuapp.com/",
          github: "https://github.com/DianaNilsson/hamsterwars-app"
        }
      ],
      selectedProjectType: "",
      showProjectTools: false,
      showProjectTypes: false,
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
      projectTypes: ["Skolprojekt", "Eget Projekt", "Skarpt projekt"]
    };
  },
  methods: {
    chooseProjectType(value) {
      alert(value);
      this.filterProjects.type = true;
      this.filterProjects.all = false;
    },
    filterAll() {
      this.filterProjects.all = true;
      this.filterProjects.type = false;
      this.filterProjects.tools = false;
      this.showProjectTypes = false;
      this.selectedProjectType = "";
    },
    filterType() {
      if (this.showProjectTypes) {
        this.showProjectTypes = false;
      } else {
        this.showProjectTypes = true;
      }
    },
    selectProjectType(type) {
      this.selectedProjectType = ": " + type;
      this.filterProjects.all = false;
      this.filterProjects.type = true;
      this.filterProjects.tools = false;

      this.showProjectTypes = false;
    }
  }
};
</script>

<style scoped>
.projects {
  width: 90vw;
  margin: auto;
  margin-bottom: 10rem;
}
.projects h2 {
  font-size: 2.8rem;
  font-weight: 300;
  color: #c43b3b;
  margin-bottom: 5rem;
  text-align: center;
}
.choose-projects-list {
  display: flex;
  list-style: none;
  border-bottom: 1px solid #b5b2b2;
  overflow: visible;
}

.choose-projects-list li {
  padding-bottom: 0.8rem;
  margin-right: 2rem;
  font-size: 16px;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: #b5b2b2;
  cursor: pointer;
}

.choose-projects-list li:hover {
  color: #333333;
}

.choose-projects-list li:first-of-type {
  width: 3rem;
  text-align: center;
}

.choose-projects-list li:nth-of-type(2) {
  /* width: 8rem; */
  text-align: center;
}

.active {
  color: #333333 !important;
  border-bottom: 3px solid #c43b3b;
  margin-bottom: -1.5px !important;
}

.project-type-list {
  position: relative;
  left: 5rem;
  background-color: rgba(51, 51, 51, 0.8);
  width: 10rem;
  list-style: none;
  padding: 1rem 0;

  display: flex;
  flex-direction: column;
}

.project-type-list li {
  color: #b5b2b2;
  font-weight: 400;
  letter-spacing: 1px;
  padding: 0.5rem 1rem;
  margin: 0.2rem 0;
  cursor: pointer;
}

.project-type-list li:hover {
  color: #fff;
}
</style>