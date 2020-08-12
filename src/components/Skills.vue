<template>
  <section class="skills">
    <h2>Skills</h2>
    <section class="skills-section">
      <article class="skills-box"></article>
      <article class="education-box">
        <h3>Utbildning</h3>
        <ul class="education-timeline">
          <li>test 1</li>
          <li>test 2</li>
          <li>test 3</li>
        </ul>
      </article>
    </section>
  </section>
</template>

<script>
export default {
  name: "Skills"
};
</script>

<style scoped>
.skills {
  width: 100vw;
  height: 30rem;
  background-color: #629d8d;
  margin-bottom: 6rem;
}

.skills h2 {
  font-size: 2.8rem;
  font-weight: 300;
  color: #fff;
  background-color: #629d8d;
  width: 10rem;
  text-align: center;
  line-height: 4rem;

  position: relative;
  left: 20%;
  top: 2rem;
}

.skills-section {
  width: 80%;
  border-top: 2px solid #fff;
  margin: auto;
  display: flex;
}

.skills-box {
  width: 70%;
}

.education-box {
  width: 30%;
  height: 20rem;
  padding: 2rem;
}

.education-box h3 {
  font-size: 1.4rem;
  font-weight: 300;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: #fff;
  margin-bottom: 1rem;
}

.education-timeline {
  border-left: 2px solid #fff;
  overflow: visible;
  padding: 0 1rem;
  /* list-style: none; */
}

.education-timeline li {
  color: #fff;
  margin-left: -0.3rem;
  /* margin-left: -1.4rem; */
}

/* li:before {
  content: "•";
  padding-right: 1rem;
  font-size: 2rem;
} */
</style>