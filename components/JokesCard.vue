<template>
  <div class="card">
    <nuxt-link :to="`/jokes/${id}`">
      <p class="joke-text">{{joke}}</p>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'JokesCard',
  props: {
    joke: String,
    id: Number
  }
}
</script>

<style scoped>
p {
  margin: 0px;
}

.card {
  border: 1px solid #333333;
  padding: 5px;
  margin:  10px 0px; 
  cursor: pointer;
}

.card a {
  text-decoration: none;
  color: #333333;
}

.card:hover {
  background-color: #e0e0e0;
}
</style>