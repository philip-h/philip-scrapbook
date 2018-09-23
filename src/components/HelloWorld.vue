<template>
  <div class="hello">
    <h1>{{id}}</h1>
    <h1>{{post.title}}</h1>
    <p>{{post.body}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      post: {}
    }
  },

  created() {
    this.$http.get("https://jsonplaceholder.typicode.com/posts/" + this.$props.id).then(function(data) {
      this.post = data.body;
    })
  },

  name: 'HelloWorld',
  props: {
    id: Number
  }
}
</script>

