<template>
  <div class="card-container">
    <img v-bind:src="avatar_url" alt="user-avatar">
    <div>
      <div class="name">{{name}}</div>
      <div>Location: {{location}}</div>
      <div>Blog: {{blog}}</div>
      <div>GitHub Url: {{html_url}}</div>
      <div>Public Repository: {{public_repos}}</div>
      <div>Followers: {{followers}}</div>
    </div>
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
    followers: Number
  }
}
</script>

<style scoped>
.card-container {
  margin: 20px;
}
.card-container img {
  width: 70px;
}
.card-container .name {
   font-weight: bold;
}
</style>