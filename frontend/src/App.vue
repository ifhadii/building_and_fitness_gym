<template>
    <!-- Font Awesome 7.0.1 CSS -->
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/all.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/brands.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/fontawesome.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/regular.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/solid.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/svg-with-js.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/svg.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/v4-font-face.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/v4-shims.min.css">
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.1/css/v5-font-face.min.css">



    <Navbar />
    <HomePage />
    <SubscriptionsSections />
    <FooterPage />

</template>

<script>

import HomePage from './components/HomePage.vue'
import Navbar from './components/Navbar.vue'
import FooterPage from './components/FooterPage.vue'
import SubscriptionsSections from './components/SubscriptionsSections.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    HomePage,
    FooterPage,
    SubscriptionsSections,
  }
}
</script>

<style>
#app {
  /* background-color: #eee; */
}

</style>