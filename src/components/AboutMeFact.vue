<template>
  <section class="about-me-fact">
    <article class="fact-box">
      <h3>Fakta</h3>
      <ul>
        <li>Ålder: 29 år</li>
        <li>Bor: Göteborg</li>
        <li>Egenskaper: noggrann, omtänksam &amp; driven</li>
      </ul>
    </article>
    <section class="about-me-flex-container">
      <article class="interests-box">
        <h3>Och lite skryt-fakta</h3>
        <ul>
          <li>Cyklat från Umeå till Istanbul och sedan vidare Afrika</li>
          <li>Vandrat hela Kungsleden + Kebne på 20 dagar</li>
          <li>Flera JSM och USM medaljer i friidrott</li>
          <li>240hp i Idrottsmedicin</li>
        </ul>
      </article>
      <article class="funny-fact-box">
        <h3>Intressen</h3>
        <div class="interest-icons-container">
          <figure>
            <img src="../assets/icons/running.png" alt="running" />
            <figcaption>Löpning</figcaption>
          </figure>
          <figure>
            <img src="../assets/icons/hiking.png" alt="running" />
            <figcaption>Äventyr</figcaption>
          </figure>
          <figure>
            <img src="../assets/icons/climbing.png" alt="running" />
            <figcaption>Klättring</figcaption>
          </figure>
          <figure>
            <img src="../assets/icons/creating.png" alt="running" />
            <figcaption>Skapande</figcaption>
          </figure>
          <figure>
            <img src="../assets/icons/running.png" alt="running" />
            <figcaption>Löpning</figcaption>
          </figure>
        </div>
      </article>
    </section>
  </section>
</template>

<script>
export default {
  name: "AboutMeFact"
};
</script>

<style scoped>
.about-me-fact {
  position: relative;
  overflow: visible;
}

.about-me-flex-container {
  display: flex;
  justify-content: flex-end;
}

.about-me-fact h3 {
  font-size: 1.4rem;
  font-weight: 300;
  text-transform: uppercase;
  color: #fff;
  margin-bottom: 1rem;
}

.fact-box {
  width: 30%;
  height: 16rem;
  background-color: rgba(88, 140, 126, 0.85);
  background-color: rgba(196, 59, 59, 0.8);
  border: 2px solid #fff;
  padding: 2rem;

  position: absolute;
  top: -4rem;
  z-index: 1;
}

.interests-box {
  width: 60%;
  height: 17rem;
  /* background-color: #e3c9a4; */
  background-color: #cecbcb;
  border: 2px solid #fff;
  padding: 2rem;
  padding-left: 14rem;
  overflow-y: hidden;
}

.interests-box li,
.interests-box h3 {
  color: #333333;
}

.interest-icons-container {
  display: flex;
  flex-wrap: wrap;
}

.interest-icons-container figure {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0.6rem;
}

.interest-icons-container figcaption {
  color: #fff;
  font-size: 12px;
}

.interest-icons-container img {
  width: 2.5rem;
}

.funny-fact-box {
  width: 30%;
  height: 17rem;
  background-color: #72a799;
  border: 2px solid #fff;
  padding: 2rem;
  overflow-y: hidden;
}

ul {
  padding: 0 1rem;
}

li {
  font-size: 14px;
  line-height: 1.4;
  font-weight: 300;
  color: #fff;
  margin-bottom: 0.6rem;
  overflow-x: visible;
}
</style>