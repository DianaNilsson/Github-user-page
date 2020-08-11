<template>
  <section class="about-me">
    <section class="about-me-section">
      <img src="../assets/portrait.jpg" alt="portrait" class="about-me-portrait" />
      <article class="about-me-presentation">
        <hgroup>
          <h2>Om mig</h2>
          <h3>Frontendutvecklare med designtänk</h3>
        </hgroup>
        <p>Hej där! Jag är en frontendutvecklare som älskar att skapa nya projekt. Jag gillar att planera, detaljarbete och problemlösningen som jag behöver klara av längs vägen. Med programmeringen ser jag tusen möjligheter och jag kan knapptvänta på att få fortsätta utvecklas och få testa nya projekt. Jag är en frontendutvecklare som älskar att skapa nya projekt.</p>
        <p class="signature">/Diana Nilsson</p>
      </article>
    </section>
  </section>
</template>

<script>
export default {
  name: "AboutMe"
};
</script>

<style scoped>
.about-me {
  padding: 8rem;
  margin-bottom: 10rem;
}
.about-me-section {
  display: flex;
  border-right: 1px solid #588c7e;
  padding-right: 2rem;
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

/* .about-me-section {
  display: flex;
  margin-bottom: 10rem;
  margin-top: 8rem;
  margin-left: 5rem;
}

.presentation-container {
  overflow: visible !important;
  width: 40%;
  padding: 5rem 0 6rem 6rem;
}

.presentation-container hgroup {
  background-color: #f3b265;
  border: 2px solid #fff;
  width: 140%;
  position: relative;
  padding: 0.6rem 2rem;
  margin-bottom: 2rem;
  margin-top: -2rem;
}

.presentation-container h2 {
  font-size: 2.4rem;
  font-weight: 400;
  color: #fff;
  margin-bottom: 0.6rem;
}

.presentation-container h3 {
  color: #fff;
  font-size: 1.2rem;
  font-weight: 300;
  letter-spacing: 3px;
}

.presentation-container p {
  width: 120%;
  position: relative;
  line-height: 1.7;
}

.img-container {
  width: 28rem;
  height: 28rem;
  background-color: #eaeaea;
  display: flex;
  align-items: center;
  justify-content: center;
}

.img-container img {
  width: 18rem;
  border: 2px solid #fff;
} */
</style>