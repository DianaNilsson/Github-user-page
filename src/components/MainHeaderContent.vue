<template>
  <section id="main-header-content">
    <h1>
      <span>Min</span> Projektsida
    </h1>
    <h3>Välkommen till min projektsida! Här delar jag med mig av projekt och arbeten som jag skapar under min väg mot att bli en duktig frontendutvecklare.</h3>
    <button>Visa projekt</button>
  </section>
</template>

<script>
export default {
  name: "MainHeaderBackground"
};
</script>

<style scoped>
#main-header-content {
  position: relative;
  max-width: 28rem;
  margin: 3rem 3rem 6rem 20rem;
  overflow: visible;
}

#main-header-content h1 {
  margin-bottom: 1.5rem;
  font-size: 3.5rem;
  font-weight: 400;
  color: #fff;
}

#main-header-content h1 span {
  font-size: 3.5rem;
  color: #f3b265;
}

#main-header-content h3 {
  color: #fff;
  font-size: 1.3rem;
  font-weight: 400;
  letter-spacing: 0.2px;
}

#main-header-content button {
  background-color: rgba(62, 72, 55, 0.8);
  padding: 0.4rem 0.8rem;
  border: 2px solid #fff;
  border-radius: 2px;
  font-size: 1.1rem;
  color: #fff;

  position: absolute;
  right: 4rem;
  bottom: -3.6rem;
  cursor: pointer;
  transition: all 0.2s;
}

#main-header-content > button:hover {
  background-color: #f3b265;
  border: 2px solid #f3b265;
}

@media only screen and (max-width: 450px) and (orientation: portrait),
  only screen and (max-width: 800px) and (orientation: landscape) {
  #main-header-content {
    margin: 3rem;
  }
}
</style>