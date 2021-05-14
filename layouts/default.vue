<template>
  <div>
    <Header />
    <Nuxt />
  </div>
</template>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: sans-serif;
  }

  body {
    @apply bg-gray-100
  }

  a {
    text-decoration: none;
  }

  p {
    margin-bottom: 15px;
  }

  p:last-of-type {
    margin-bottom: 0;
  }
</style>
