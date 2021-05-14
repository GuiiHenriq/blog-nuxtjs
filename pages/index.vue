<template>
  <div class="home-page">
    <h2 class="text-3xl font-semibold text-center text-green-500 my-10">Posts Recentes</h2>

    <section class="articles flex justify-center">
      <ul>
        <li class="article max-w-3xl bg-white shadow-lg rounded-md p-4 mb-5" v-for="article in articles" :key="article">
          <nuxt-link :to="{name: 'slug',  params: {slug: article.slug}}" class="flex items-center flex-col lg:flex-row">
            <img :src="require(`@/assets/resources/${article.img}`)" alt="" class="max-w-xs mb-2 lg:mb-0">

            <div class="detail w-auto lg:w-80 flex items-center flex-col">
              <h3>{{article.title}}</h3>
              <p>{{article.description}}</p>
            </div>
          </nuxt-link>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "Home",
  async asyncData({ $content, params }) {
    const articles = await $content('blog', params.slug)
      .only(['title', 'description', 'slug', 'img'])
      .sortBy('createdAt', 'asc')
      .fetch();

    return { articles }
  }
}
</script>

<style>
</style>
