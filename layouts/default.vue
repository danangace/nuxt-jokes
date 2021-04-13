<template>
  <div class="layout">
    <div class="layout-page">
      <AppHeader />
      <hr style="margin: 0px;">
      <Nuxt />
    </div>
  </div>
</template>
<script>

import AppHeader from '../components/AppHeader'

export default {
  name: 'DefaultLayout',
  components: {
    AppHeader
  },

  head () {
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
}
</script>
<style>
html {
  background-color: #E0E0E0;
}

.layout {
  display: flex;
  justify-content: center;
}

.layout-page {
  background-color: #FFFFFF;
  width: 768px;
  padding: 10px 20px;
}
</style>
