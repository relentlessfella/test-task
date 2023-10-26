<template>
  <div id="app">
    <NavBar />
    <ImageGallery />
  </div>
</template>

<script>
import ImageGallery from './components/ImageGallery.vue'
import NavBar from './components/NavBar.vue'

export default {
  components: {
    ImageGallery,
    NavBar
  }
}
</script>

<style>
body {
  margin: 0;
}
</style>
