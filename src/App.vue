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
  font-family: 'Montserrat', Helvetica, Arial, sans-serif;
  font-size: 1.2em;
  line-height: 23px;
  color: rgba(0, 0, 0, 0.8);
}

</style>
