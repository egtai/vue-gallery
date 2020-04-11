<template>
  <div id="app">
    <my-gallery></my-gallery>
  </div>
</template>

<script>
import MyGallery from './components/MyGallery.vue'

export default {
  name: 'App',
  components: {
     MyGallery
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
