<template>

    <Navbar />
    <HomePage />
    <FooterPage />

</template>

<script>

import HomePage from './components/HomePage.vue'
import Navbar from './components/Navbar.vue'
import FooterPage from './components/FooterPage.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    HomePage,
    FooterPage,
  }
}
</script>

<style>
#app {
  background-color: #eee;
}

</style>