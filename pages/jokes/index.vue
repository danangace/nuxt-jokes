<template>
  <div class="container">
    <Loading v-if="jokes.loading" />
    <div v-else>
      <button @click.prevent="fetchJokes">Get More</button>
      <jokes-card v-for="data in jokes.data" :key="data.id" :joke="data.joke" :id="data.id"></jokes-card>
    </div>
  </div>
</template>

<script>

import JokesCard from '../../components/JokesCard'
import Loading from '../../components/Loading'

export default {
  name: 'Jokes',

  head () {
    return {
      title: 'Jokes',
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
    JokesCard,
    Loading
  },

  data () {
    return {
      jokes: {
        data: [],
        loading: false
      }
    }
  },

  methods : {
    async fetchJokes () {
      this.$set(this.jokes, 'loading', true)
      const data = await fetch('https://api.icndb.com/jokes/random/10?escape=javascript').then(response => response.json())
      this.jokes.data = data.value
      this.$set(this.jokes, 'loading', false)
    }
  },

  created () {
    this.fetchJokes()
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