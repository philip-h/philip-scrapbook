<template>
  <div class="home">
    <img src="http://placekitten.com/200/750" alt="Cat">
    <section>
      Welcome to this blog about youth. I don't know what to put here right now, but I know
      I'll think of something. To the left is all about me and to the right is what I have to 
      say. Relax, stay a while and look around.
    </section>
    
  </div>
</template>

<script>
export default {
  name: 'home',
}
</script>

<style scoped>
.home {
  display: flex;
  max-width: 1200px;
  margin: 0 auto;

}

.home > img {
  flex-shrink: 0;
  align-self: center;
}

.home > section {
  padding: 50px;
  align-self: center;
}
</style>

