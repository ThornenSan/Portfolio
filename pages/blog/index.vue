<script setup>
const { data: posts } = await useAsyncData('posts', () =>
  queryContent('/blog').find()
)
</script>

<template>
  <h1 class="text-3xl my-8">Blog Posts</h1>

  I like to write about anything that I am currently working or something new that interests me. If you would like me to
  write about something or be a guest blogger on your blog please reach out to me. 

  <section class="grid md:grid-cols-3 mt-8 gap-10">
    <Post :posts="posts" />
  </section>
</template>
