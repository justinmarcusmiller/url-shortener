<template>
  <main id="body">
    <div id="cta">
      <div id="cta-text">
        <h1>More than just shorter links</h1>
        <p>
          Build your brand's recognition and get detailed insights on how your
          links are performing
        </p>
        <button id="cta-btn">Get Started</button>
      </div>
      <div id="cta-img"></div>
    </div>
    <LinkGenerator />
    <div id="heading">
      <h2>Advanded Statistics</h2>
      <p>
        Track how your links are performing across the web with our advanced
        statistics dashboard.
      </p>
    </div>
    <div id="stats-articles">
      <article id="brand" class="stat-article">
        <h3>Brand Recognition</h3>
        <p>
          Boots your brand recognition with each click. Generic links don't mean
          a thing. Branded links help instil confidence in your content.
        </p>
      </article>
      <article id="records" class="stat-article">
        <h3>Detailed Records</h3>
        <p>
          Gain insights into who is clicking your links. Knowing when and where
          people engage with your content helps inform better decisions.
        </p>
      </article>
      <article id="custom" class="stat-article">
        <h3>Fully Customizable</h3>
        <p>
          Improve brand awareness and content discoverability through
          customizable links, supercharging audience engagement.
        </p>
      </article>
    </div>
  </main>
</template>

<script>
import LinkGenerator from "./LinkGenerator.vue";

export default {
  components: {
    LinkGenerator,
  },
  data() {
    return {};
  },
};
</script>

<style>
#body {
  max-width: 1440px;
  margin: 25px auto;
  padding: 0 25px;
}
#cta {
  display: flex;
  justify-content: space-between;
  max-width: 100vw;
  align-items: center;
}

#cta-img {
  height: 45vw;
  width: 45vw;
  margin: auto;
  background-image: url("../assets/illustration-working.svg");
  background-position: left;
  background-size: cover;
  background-repeat: no-repeat;
}

#cta-text {
  max-width: 45vw;
}

#cta-btn {
  background-color: hsl(180, 66%, 49%);
  border: none;
  color: white;
  font-weight: 700;
  border-radius: 10px;
  font-size: 16px;
  padding: 10px 20px;
  margin-top: 15px;
}

</style>
