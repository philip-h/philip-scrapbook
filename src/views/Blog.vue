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
          <h1 v-html="posts[curr_index-1].title"></h1>
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
}

span {
  text-indent: 30px;
}

</style>
