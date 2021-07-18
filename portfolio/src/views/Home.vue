<template>
  <div class="home">
    <Banner />
    <About />
    <TechStack />
    <Projects />
    <Contact />
    <Footer />
  </div>
</template>

<script>
import Banner from "../components/Banner.vue";
import About from "../components/About.vue";
import TechStack from "../components/TechStack.vue";
import Projects from "../components/Projects.vue";
import Contact from "../components/Contact.vue";
import Footer from "../components/Footer.vue";
export default {
  name: "Home",
  components: {
    Banner,
    About,
    TechStack,
    Projects,
    Contact,
    Footer,
  },
};
</script>
