<template>
  <section class="projects">
    <h2>Projekt</h2>
    <ul class="choose-projects-list">
      <li :class="{'active':chooseProjects.all}">Alla</li>
      <li :class="{'active':chooseProjects.type}">Projekttyp</li>
      <li :class="{'active':chooseProjects.tools}">Verktyg</li>
    </ul>
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
      chooseProjects: {
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
        }
      ]
    };
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
  margin-bottom: 0.6rem;
  text-align: center;
}
.choose-projects-list {
  display: flex;
  list-style: none;
  margin: 4rem 0;
  border-bottom: 1px solid #b5b2b2;
  overflow: visible;
}

.choose-projects-list li {
  padding: 0.8rem 0.2rem;
  margin: 0 1rem;
  font-size: 16px;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: #b5b2b2;

  cursor: pointer;
}

.active {
  color: #333333 !important;
  border-bottom: 3px solid #c43b3b;
  margin-bottom: -1.5px !important;
}
</style>