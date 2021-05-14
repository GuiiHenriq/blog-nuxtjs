<template>
  <header class="min-w-full bg-white shadow-md py-5">
    <div class="title flex justify-between mx-20">
      <nuxt-link to="/">My Blog</nuxt-link>

      <nav>
        <nuxt-link to="/" class="mr-8 inline-block">Home</nuxt-link>
        <nuxt-link to="/about">About</nuxt-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style>

</style>