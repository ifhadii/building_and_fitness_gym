<template>
  <div class="about">
    <h1>{{ msg }}</h1>
    <p>This is the about page for our gym application.</p>
  </div>
</template>

<script>
export default {
  name: 'AboutPage',
  props: {
    msg: String
  }
}
</script>

<style scoped>
.about {
  padding: 20px;
}
</style>