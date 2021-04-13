<template>
  <div class="container">
    <nuxt-link to="/jokes">Back</nuxt-link>
    <div class="detail" v-if="fetchDone">
      <p>Joke ID : {{joke.id}}</p>
      <p class="joke-text">{{joke.joke}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailJoke',

  data () {
    return {
      joke: {},
      fetchDone: false
    }
  },

  head () {
    return {
      title: this.fetchDone ? this.joke.joke : '... - Nuxt Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.joke.joke
        }
      ]
    }
  },

  async created () {
    const data = await fetch(`https://api.icndb.com/jokes/${this.$route.params.id}`).then(response => response.json())
    this.joke = data.value
    this.fetchDone = true
  }
}
</script>

<style scoped>
p {
  margin: 0px;
}

.container {
  padding: 20px 15px;
}

.container a {
  text-decoration: none;
}

.detail {
  margin-top: 15px;
}

.joke-text {
  border: 1px solid #333333;
  padding: 25px 20px;
  margin-top: 10px;
}
</style>