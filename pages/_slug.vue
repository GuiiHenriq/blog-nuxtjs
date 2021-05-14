<template>
  <article class="article max-w-screen-lg m-auto">
    <img :src="require(`@/assets/resources/${article.img}`)" alt="" class="w-full h-80 object-cover">
    <h2 class="text-3xl font-semibold text-center text-green-500 my-10">{{article.title}}</h2>
    <nuxt-content :document="article" />
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const article = await $content('blog', params.slug).fetch();

    return { article }
  }
}
</script>

<style>
.nuxt-content h2 {
  @apply text-2xl font-semibold text-green-500
}
</style>