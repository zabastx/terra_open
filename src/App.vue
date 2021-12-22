<template>
  <main class="app">
    <Intro />
    <Info />
    <Course />
    <Results />
    <HeadHunter />
    <Audience />
    <TerraForm />
    <Projects />
    <About />
    <Reviews />
    <Partners />
    <TerraForm />
  </main>
</template>

<script>
export default {
  name: 'App',
  components: {
    Intro: () => import('./blocks/Intro.vue'),
    Info: () => import('./blocks/Info.vue'),
    Course: () => import('./blocks/Course.vue'),
    Results: () => import('./blocks/Results.vue'),
    HeadHunter: () => import('./blocks/HeadHunter.vue'),
    Audience: () => import('./blocks/Audience.vue'),
    TerraForm: () => import('./blocks/TerraForm.vue'),
    Projects: () => import('./blocks/Projects.vue'),
    About: () => import('./blocks/About.vue'),
    Reviews: () => import('./blocks/Reviews.vue'),
    Partners: () => import('./blocks/Partners.vue')
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&family=Play:wght@400;700&display=swap');

html {
  min-height: 100vh;
  height: 1px;
  font-size: 18px;
  font-family: 'Play', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  box-sizing: border-box;
  margin: 0;
  scrollbar-width: thin;
  scrollbar-color: #3f5168 #f0f1f3;
  scroll-behavior: smooth;
  &::-webkit-scrollbar {
    width: 5px;
    background-color: #f0f1f3;
  }
  &::-webkit-scrollbar-thumb {
    background-color: #3f5168;
    border-radius: 2.5px;
  }
}

body {
  margin: 0;
}

h1 {
  font-weight: 700;
}

.app {
  margin: auto;
  display: flex;
  flex-direction: column;
  overflow-x: hidden;
  > * {
    flex-grow: 1;
    > * {
      max-width: 1200px;
      padding: 150px 0;
      margin: auto;
    }
  }
}

@media (max-width: 1240px) {
	.app {
    > * {
      > * {
        padding: 100px 0;
      }
    }
  }
}

@media (max-width: 550px) {
  .app {
    > * {
      flex-shrink: 1;
    }
  }
}
</style>
