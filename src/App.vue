<template>
  <div id="app">
    <Nav/>
    <router-view/>
  </div>
</template>

<script>
import Nav from '@/components/Nav.vue'

export default {
  name: 'App',
  components: {
    Nav
  }
}
</script>

<style>
body {
  background: white;
}

#app {
  font-family: 'Roboto', Helvetica, Arial, sans-serif;
  font-size: 1.5em;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: rgba(0, 0, 0, 0.7);
}

</style>
