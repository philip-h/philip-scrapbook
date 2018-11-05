<template>
  <div class="about">
    <img :src="me" alt="Young Adult with Sunglasses, a bowtie and suspenders">
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
        This online scrapbook (more specifically, the blog page over &#x2192;) is dedicated to 
        critically analysing articles and renderings about things like youth culture and 
        adolescent development.
      </p>
    </section>
  </div>
</template>

<script>
import me from '../assets/me.jpeg'

export default {
  data() {
    return {
      me: me
    }
  },


  name: 'About'
}
</script>

<style scoped>
.about {
  display: flex;
  max-width: 1200px;
  margin: 0 auto;
  padding: 30px;
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


