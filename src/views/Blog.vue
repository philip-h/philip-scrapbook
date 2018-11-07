<template>
  <div class="blog">
    <md-divider class="md-full"></md-divider>
    <md-app>
       <!--<md-app-toolbar class="md-transparent" md-elevation="0">-->
         <!--<md-button class="md-icon-button" @click="menuVisible = !menuVisible">-->
          <!--<md-icon>menu</md-icon>-->
         <!--</md-button>-->
        <!--<span class="md-title">My Title</span>-->
      <!--</md-app-toolbar> -->

      <md-app-drawer md-permanent="full" v-if="menuVisible" class="md-scrollbar">
        <md-toolbar class="md-transparent" md-elevation="0">
          Entries
        </md-toolbar>

        <md-list class="md-double-line">
          <md-list-item v-for="post in posts" :key="post.id" @click="curr_index = post.id">

            <md-avatar>
              <img :src="require('../assets/'+post.img)" :alt="post.alt"/>
            </md-avatar>

            <div class="md-list-item-text" :class="{ active : post.id === curr_index }">
              <span v-html="post.title"></span>
              <span v-html="post.body.slice(0,45) + '...'"></span>
            </div>
       
          </md-list-item>
        </md-list>

      </md-app-drawer>
      
      <md-app-content>
        <md-button class="md-icon-button md-primary" @click="menuVisible = !menuVisible">
          <md-icon v-if="menuVisible">chevron_left</md-icon>
          <md-icon v-else>chevron_right</md-icon>
        </md-button>


        <div class="post-content">
          <h1 v-html="'Critical Analysis '+ curr_index + ': ' + posts[curr_index-1].title"></h1>
          <!-- Conditional Renders Based on Post Type -->
          <!--post with an image-->
          <figure class="container" v-if="posts[curr_index-1].renderImg">
            <img :src="require('../assets/'+posts[curr_index-1].renderImg)" :alt="posts[curr_index-1].renderImgAlt">
            <figcaption style="text-align: center" v-html="posts[curr_index-1].renderImgAlt"></figcaption>
          </figure>
          <!--post with a video-->
          <a v-if="posts[curr_index-1].renderVideo" :href="posts[curr_index-1].renderVideo" target="_blank">
            <md-button class="md-primary md-raised">watch the video</md-button>
          </a>
          <!--post with a poem-->
          <div class="container" v-if="posts[curr_index-1].renderPoem">
            <blockquote v-html="posts[curr_index-1].renderPoem"></blockquote>
          </div>

          <span v-html="posts[curr_index-1].body"></span>
        </div>
               
      </md-app-content>
       
      
    </md-app>
    
  </div>
</template>

<script>
import posts from '../assets/posts.json'

export default {
  data() {
    return {
      curr_index: 0,
      posts,
      menuVisible: true
    }
  },

  created() {
   this.curr_index = this.posts[0].id;
  },

  name: 'Blog'
}
</script>

<style scoped>
.active {
  font-weight: bold;
}
.md-app {
  max-height: calc(100vh - 105px);
}

h1 {
  line-height: normal;
  text-align: center;
}

.post-content {
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
}

span {
  text-indent: 30px;
}

.container {
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  border-radius: 4px;
  overflow: hidden;
  display: inline-block;
}

.img-container > img {
  height: 250px;
}

</style>
