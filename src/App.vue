<script setup>
import Header from "./components/Header.vue"
import Hero from "./components/Hero.vue"
import About from "./components/About.vue"
import Skills from "./components/Skills.vue"
import Projects from "./components/Projects.vue"
import Experience from "./components/Experience.vue"
import Contact from "./components/Contact.vue"
import Footer from "./components/Footer.vue"
import '@fontsource/inter/400.css';

</script>

<template>
  <div class="app-container">
    <Header />
    <main>
      <Hero />
      <About />
      <Skills />
      <Projects />
      <Experience />
      <Contact />
    </main>
    <Footer />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  text-decoration: none;
  font-family: "Open Sans", sans-serif;
  font-weight: normal;
}

.app-container {
  min-height: 100vh;
  /* = tailwind min-h-screen */
  display: flex;
  flex-direction: column;
}

.container {
  max-width: 1300px;
  margin: 0 auto;
  width: 100%;
}

main {
  /* width: 100%; */
  margin: 0 auto;
}


.loader-overlay {
  position: fixed;
  inset: 0;
  /* top, right, bottom, left = 0 */
  background-color: rgba(0, 0, 0, 0.4);
  /* qora yarim shaffof */
  backdrop-filter: blur(5px);
  /* orqa fon blur */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  /* hamma narsadan ustida */
}

.loader {
  width: 60px;
  height: 60px;
  border: 6px solid rgba(0, 0, 0, 0.229);
  /* sariq shaffof */
  border-top: 6px solid #000000ff;
  /* sariq qismi */
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
</style>
