<template>
  <div class="card-container">
    <img v-bind:src="avatar_url" alt="user-avatar">
    <div>
      <h2 class="name">{{name}}</h2>
      <p>Location: {{location}}</p>
      <p>Blog: {{blog}}</p>
      <p>GitHub URL:<br>{{html_url}}</p>
      <p>Public Repository: {{public_repos}}</p>
      <p>Followers: {{followers}}</p>
    </div>
    <button @click="deleteCard(index)">DELETE CARD</button>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    blog: String,
    name: String,
    avatar_url: String,
    location: String,
    public_repos: Number,
    html_url: String,
    followers: Number,
    index: Number
  },
  methods: {
    deleteCard(index) {
      this.$emit('deleteCard', index)
    }
  }
}
</script>

<style scoped>
.card-container {
  border: 2px solid black;
  border-radius: 20px;
  margin: 20px;
  padding: 25px;
  text-align: center;
}
.card-container img {
  width: 200px;
  border-radius: 50%;
}
.card-container .name {
   font-weight: bold;
}
</style>