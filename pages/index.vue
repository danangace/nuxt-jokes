<template>
  <div class="container">
    <p style="font-size: 20px;">Welcome to the best Nuxt Jokes on Web!</p>
  </div>
</template>

<script>

import AppHeader from '../components/AppHeader'

export default {
  name: 'App',

  head() {
    return {
      title: 'Nuxt Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Welcome to the best Nuxt Jokes on Web!'
        }
      ]
    }
  },

  components: {
    AppHeader
  }
}
</script>

<style scoped>
.container {
  padding: 20px 15px;
}

p {
  margin: 0px;
}
</style>
