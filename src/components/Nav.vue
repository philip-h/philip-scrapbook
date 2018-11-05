
<template>
  <nav>
    <md-tabs md-sync-route md-alignment="fixed">
      <md-tab id="tab-home" md-label="Home" md-icon="home" to="/"></md-tab>
      <md-tab id="tab-blog" md-label="Blog" md-icon="subject" to="/blog"></md-tab>
    </md-tabs>
  </nav>
</template>

<script>
export default {
  name: "Nav"
};
</script>


<style scoped>
nav {
  background: white;
  margin-bottom: 30px;
}

</style>




