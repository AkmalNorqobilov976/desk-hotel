<template>
  <div id="app">
    <Navbar />
    <Header />
    <Recommendation/>
    <Benifit/>
    <Footer/>
  </div>
</template>

<script>
import Benifit from './components/Benifit.vue';
import Header from "./components/Header.vue";
import Navbar from './components/Navbar.vue';
import Recommendation from './components/Recommendation.vue';
import Footer from './components/Footer.vue';
export default {
  components: { 
    Header, 
    Navbar, 
    Recommendation, 
    Benifit,
    Footer 
  },
  name: "App",
};
</script>

<style lang="scss" scoped>
#app {
  width: 1440px;
  margin: auto;
  position: relative;
  overflow: hidden;
}
</style>