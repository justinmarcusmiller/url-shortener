<template>
  <div id="app">
    <Header />
    <Body />
    <BoostCTA />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Body from './components/Body.vue'
import Footer from './components/Footer.vue'
import BoostCTA from './components/BoostCTA.vue'

export default {
  name: 'App',
  components: {
    Header,
    Body,
    Footer,
    BoostCTA
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  transition: all .1s ease-in-out;
}

#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

button:hover {
  opacity: 0.8;
}
</style>
