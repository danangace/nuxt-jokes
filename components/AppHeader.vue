<template>
  <div class="app-header">
    <div class="title">
      <h1>Nuxt Jokes</h1>
    </div>
    <div class="nav">
      <p v-for="(data,index) in navbar" :key="index">
        <nuxt-link :to="data.link">{{data.label}}</nuxt-link>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppHeader',

  data () {
    return {
      navbar : [
        { link: '/', label: 'Home' },
        { link: '/jokes', label: 'Jokes' },
        { link: '/about', label: 'About' },
      ]
    }
  }
}
</script>

<style scoped>
p {
  margin-bottom: 0px;
}

.app-header {
  display: grid;
  grid-template-columns: 60% 40%;
  align-items: center;
  padding: 15px;
}

.nav {
  display: flex;
  justify-content: space-between;
}

.nav a {
  text-decoration: none;
  color: #333333;
  font-size: 18px;
  font-weight: bold;
}

.nav a:hover {
  color: #144db6;
}
</style>