<template>
  <div class = "Post">
    <h1>{{ post.title }}</h1>
    <p>{{ post.description }}</p>
  </div>
</template>

<script>
  export default {
    name: "Post",
    async asyncData({ params, $axios }) {
      const post = await $axios.$get(`https://api.nuxtjs.dev/posts/${params.id}`)
      //console.log(post)
      return { post }
    }
  }
</script>