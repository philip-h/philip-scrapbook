<template>
  <div class="about">
    <img src="http://placekitten.com/300/300" alt="Cat">
    <section>
      <p>
        Hi and welcome to my online scrapbook! My name is Philip Habib and yes, that is me! I am a
        York University student studying hard to become a CS and math teacher. I have been working
        and volunteering with "youth" for six years now and that is one of the main reasons as to 
        why I entered teacher's college. 
      </p>
      <p>
        Some interesting facts about me? Sure. 
        <ul>
          <li>I have been playing guitar for as long as I have been working with youth</li>
          <li>I have been able to solve a rubik's cube since I was in elementary school</li>
          <li>My favourite sport is ultimate frisbee</li>
          <li>My favourite past time is learning more about my faith</li>
        </ul>
      </p>
      <p>
        This about me page will be updated for real when I can come up with something clever
        and intelligent to say. Until then, here is the rough outline of the blog site.
      </p>
    </section>
  </div>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style scoped>
.about {
  display: flex;
  max-width: 1200px;
  margin: 0 auto;
}

.about > section {
  padding: 50px;
  align-self: center;
}

.about > img {
  flex-shrink: 0;
  align-self: center;
}
</style>


