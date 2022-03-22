<template>
   <transition name="fade" tag="div" class="wrapper" mode="out-in">
      <div class="wrapper" id="app">
         <LandingPage />
         <Description />
         <Experience />
         <Skills />
         <Projects />
         <Footer />
      </div>
   </transition>
</template>

<script>
   export default {
      name: "App",
      components: {
         LandingPage: () => import('./components/LandingPage'),
         Description: () => import('./components/Description'),
         Experience: () => import('./components/Experience'),
         Skills: () => import('./components/Skills'),
         Projects: () => import('./components/Projects'),
         Footer: () => import('./components/Footer'),
      },
   };
</script>

<style scoped lang="scss">
   @import "@/styles/constants.scss";

   #app {
      font-family: Montserrat-Regular, serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      color: #2c3e50;
   }

   .wrapper {
      height: 100%;
   }
</style>
