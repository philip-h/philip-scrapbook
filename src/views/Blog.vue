<template>
  <div class="blog">
    <md-divider class="md-full"></md-divider>
    <md-app>
      <!-- <md-app-toolbar>
        <span class="md-title">My Title</span>
      </md-app-toolbar> -->

      <md-app-drawer md-permanent="full" class="md-scrollbar">
        <md-toolbar class="md-transparent" md-elevation="0">
          Entries
        </md-toolbar>

        <md-list class="md-double-line">
          <md-list-item v-for="post in posts" :key="post.id" @click="curr_index = post.id">

            <md-avatar>
              <img src="http://placekitten.com/40/40" alt="Cat">
            </md-avatar>

            <div class="md-list-item-text" :class="{ active : post.id === curr_index }">
              <span>{{post.title}}</span>
              <span>{{post.body.slice(0,10)}}</span>
            </div>
       
          </md-list-item>
        </md-list>

      </md-app-drawer>
      
      <md-app-content>
        <div class="post-content">
          <h1>{{ posts[curr_index-1].title }}</h1>
          <p>{{ posts[curr_index-1]. body}}</p>
        </div>
       
      </md-app-content>
       
      
    </md-app>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      curr_index: 0,
      posts: []
    }
  },

  created() {
    // this.$http.get("https://jsonplaceholder.typicode.com/posts/").then(function(data) {
    //   this.posts = data.body.slice(0,50);
    //   this.curr_index = data.body[0].id;
    // })
    this.posts = 
    [
      {
        "userId": 1,
        "id": 1,
        "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
        "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
      },
      {
        "userId": 1,
        "id": 2,
        "title": "qui est esse",
        "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
      },
      {
        "userId": 1,
        "id": 3,
        "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
        "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
      },
      {
        "userId": 1,
        "id": 4,
        "title": "eum et est occaecati",
        "body": "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit"
      },
      {
        "userId": 1,
        "id": 5,
        "title": "nesciunt quas odio",
        "body": "repudiandae veniam quaerat sunt sed\nalias aut fugiat sit autem sed est\nvoluptatem omnis possimus esse voluptatibus quis\nest aut tenetur dolor neque"
      },
      {
        "userId": 1,
        "id": 6,
        "title": "dolorem eum magni eos aperiam quia",
        "body": "ut aspernatur corporis harum nihil quis provident sequi\nmollitia nobis aliquid molestiae\nperspiciatis et ea nemo ab reprehenderit accusantium quas\nvoluptate dolores velit et doloremque molestiae"
      },
      {
        "userId": 1,
        "id": 7,
        "title": "magnam facilis autem",
        "body": "dolore placeat quibusdam ea quo vitae\nmagni quis enim qui quis quo nemo aut saepe\nquidem repellat excepturi ut quia\nsunt ut sequi eos ea sed quas"
      },
      {
        "userId": 1,
        "id": 8,
        "title": "dolorem dolore est ipsam",
        "body": "dignissimos aperiam dolorem qui eum\nfacilis quibusdam animi sint suscipit qui sint possimus cum\nquaerat magni maiores excepturi\nipsam ut commodi dolor voluptatum modi aut vitae"
      },
      {
        "userId": 1,
        "id": 9,
        "title": "nesciunt iure omnis dolorem tempora et accusantium",
        "body": "consectetur animi nesciunt iure dolore\nenim quia ad\nveniam autem ut quam aut nobis\net est aut quod aut provident voluptas autem voluptas"
      },
      {
        "userId": 1,
        "id": 10,
        "title": "optio molestias id quia eum",
        "body": "quo et expedita modi cum officia vel magni\ndoloribus qui repudiandae\nvero nisi sit\nquos veniam quod sed accusamus veritatis error"
      }
    ]
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

</style>


