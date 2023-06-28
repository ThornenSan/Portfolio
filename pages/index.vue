<script setup>
const { data: posts } = await useAsyncData('latest-posts', () =>
  queryContent('/blog')
    .sort({ data: 1 })
    .limit(3)
    .find()
)
</script>

<template>
  <section>
    <h1 class="text-5xl font-bold mt-20">👋🏻 Hello, I'm Thornen!</h1>
    <p class="text-base text-gray-900 p-2 italic">A Software Developer</p>
  </section>
  <section class="flex flex-col md:flex-row">
    <div class="md:w-3/4">
      <h2 class="text-3xl font-bold mt-8">My Story</h2>
      <p class="text-lg py-2">
        I am a Software Engineer from Cambodia. I have been writing software for over 3+ years now.
      </p>
      <p class="text-lg py-2">
      From a young age, I have been fascinated by the way technology. I have a positive attitude and approach every challenge with optimism and determination. I enjoy collaborating with others to achieve common goals. I am also adaptable and thrive in fast-paced environments where I can use my problem- solving skills to overcome obstacles.
      </p>
      <p class="text-lg py-2">
        I enjoy reading blog about latest technologies, play sports and lifting weights.
      </p>
    </div>
    <img src="~/assets/images/Thornen.png" class="w-1/2 md:max-w-sm p-8 mx-auto" />
  </section>

  <section>
    <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
    <div class="grid md:grid-cols-3 pt-8 gap-10">
      <Post :posts="posts" />
    </div>
  </section>
</template>
