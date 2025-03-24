<template>
  <div id="app">
    <Header />
    <main>
      <Jumbotron />
      <Skills />
      <About />
      <Portfolio />
      <Certificates />
      <Questions />
      <Contact />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Jumbotron from './components/Jumbotron.vue';
import Skills from './components/Skills.vue';
import About from './components/About.vue';
import Portfolio from './components/Portfolio.vue';
import Certificates from './components/Certificates.vue';
import Questions from './components/Questions.vue';
import Contact from './components/Contact.vue';

export default {
  components: {
    Header,
    Footer,
    Jumbotron,
    Skills,
    About,
    Portfolio,
    Certificates,
    Questions,
    Contact
  }
};
</script>
