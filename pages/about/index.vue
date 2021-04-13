<template>
  <div class="container">
    <p class="about-title">About Nuxt Jokes</p>
    <p style="margin-top: 10px;">This web contains joke from Chuck Norris Jokes API</p>
  </div>
</template>

<script>
export default {
  name: 'About',
  head() {
    return {
      title: 'About - Nuxt Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Welcome to the best Nuxt Jokes on Web!'
        }
      ]
    }
  },
}
</script>

<style scoped>
.container {
  padding: 20px 15px;
}

p {
  margin: 0px;
}

.about-title {
  font-size: 20px;
  font-weight: bold;
}
</style>