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
      <h2>Advanced Statistics</h2>
      <p>
        Track how your links are performing across the web with our advanced
        statistics dashboard.
      </p>
    </div>
    <div id="stats-articles">
      <article id="brand" class="stat-article">
        <img id="brand-icon" class="article-icon" />
        <h3>Brand Recognition</h3>
        <p>
          Boots your brand recognition with each click. Generic links don't mean
          a thing. Branded links help instil confidence in your content.
        </p>
      </article>
      <article id="records" class="stat-article">
        <img id="records-icon" class="article-icon" />
        <h3>Detailed Records</h3>
        <p>
          Gain insights into who is clicking your links. Knowing when and where
          people engage with your content helps inform better decisions.
        </p>
      </article>
      <article id="custom" class="stat-article">
        <img id="custom-icon" class="article-icon" />
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
  color: hsl(260, 8%, 14%);
}
#cta {
  display: flex;
  justify-content: space-between;
  max-width: 100vw;
  align-items: center;
  height: 700px;
}

#cta-img {
  height: 45vw;
  width: 45vw;
  max-width: 600px;
  max-height: 600px;
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

#heading {
  text-align: center;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
#heading h2 {
  font-size: 32px;
}

#heading p {
  font-weight: 700;
  color: hsl(257, 7%, 63%);
}

#stats-articles {
  display: flex;
  justify-content: space-between;
  padding: 100px 0;
}

.stat-article {
  width: 25%;
}

.stat-article h3 {
  margin-bottom: 15px;
  margin-top: 5px;
}

#brand {
  transform: translateY(-50px);
}

#custom {
  transform: translateY(50px);
}

.article-icon {
  background-color: hsl(257, 27%, 26%);
  background-repeat:no-repeat;
  background-position: center;
  padding: 35px;
  border-radius: 100%;
}

#brand-icon {
  background-image: url('../assets/icon-brand-recognition.svg');
}

#records-icon {
  background-image: url('../assets/icon-detailed-records.svg');
}

#custom-icon {
  background-image: url('../assets/icon-fully-customizable.svg');
}

@media only screen and (max-width: 600px) {
  #cta {
    height: unset;
    flex-direction: column-reverse;
    margin-bottom: 50px;
  }
  #cta-text {
    max-width: unset;
    text-align: center;
    margin: 25px 0;
  }
  #cta-text h1 {
    line-height: 42px;
    font-size: 42px;
    margin: 15px 0;
  }
  #cta-text p {
    margin-bottom: 10px;
  }
  #cta-img {
    max-width: unset;
    max-height: unset;
    width: 75vw;
    height: 75vw;
  }
  #cta-btn {
    border-radius: 100px;
    padding: 15px 30px;
  }
  #stats-articles {
    flex-direction: column;
  }
  .stat-article {
    width: 100%;
    text-align: center;
  }
}
</style>
