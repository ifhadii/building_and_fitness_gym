<template>

    <Navbar />
    <About />
    <FooterPage />

</template>

<script>

import About from './components/About.vue'
import Navbar from './components/Navbar.vue'
import FooterPage from './components/FooterPage.vue'

export default {
  name: 'App',
  components: {
    About,
    Navbar,
    FooterPage,
  }
}
</script>

<style>
#app {
}
</style>