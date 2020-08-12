<template>
  <section class="about-me">
    <section class="about-me-section">
      <img src="../assets/portrait.jpg" alt="portrait" class="about-me-portrait" />
      <article class="about-me-presentation">
        <hgroup>
          <h2>Om mig</h2>
          <h3>Frontendutvecklare med designtänk</h3>
        </hgroup>
        <p>Hej där! Jag är en frontendutvecklare som gillar att planera och skapa nya projekt. Jag gillar att planering, detaljarbete och problemlösningen som jag behöver klara av längs vägen. Med programmeringen ser jag tusen möjligheter och jag kan knappt vänta på att få fortsätta utvecklas genom att utöva nya projekt.</p>
        <p class="signature">/Diana Nilsson</p>
      </article>
    </section>

    <about-me-fact />
  </section>
</template>

<script>
import AboutMeFact from "./AboutMeFact.vue";

export default {
  name: "AboutMe",
  components: {
    AboutMeFact
  }
};
</script>

<style scoped>
.about-me {
  padding: 9rem;
  margin-bottom: 10rem;
}
.about-me-section {
  display: flex;
  /* border-right: 1px solid #588c7e;
  padding-right: 3rem; */
  margin-bottom: 8rem;
}

.about-me-portrait {
  min-width: 16rem;
  max-height: 16rem;
  border: 1px solid #fff;
  border-radius: 100%;
  margin: 3rem 2rem 2rem 2rem;
}

.about-me-presentation {
  margin: 2rem;
}

.about-me-presentation h2 {
  font-size: 2.8rem;
  font-weight: 300;
  color: #c43b3b;
  margin-bottom: 0.6rem;
}

.about-me-presentation h3 {
  font-size: 1.4rem;
  font-weight: 300;
  letter-spacing: 3px;
  margin-bottom: 1.6rem;
}

.signature {
  font-size: 1.6rem;
  text-align: right;
  font-family: "Marck Script", cursive;
  color: #b5b2b2;
  margin: 2rem 6rem 0 0;
}
</style>