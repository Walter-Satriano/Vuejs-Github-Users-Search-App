<template>
  <div class="card-container position-relative col-10 col-sm-10 col-md-5 col-lg-4 col-xl-4 mt-5 mx-lg-2">
    <img class="w-75 mb-3" v-bind:src="avatar_url" alt="user-avatar">
    <div>
      <h2 class="name mb-3">{{name}}</h2>
      <p><strong>Location: </strong>{{location}}</p>
      <p><strong>Public Repository: </strong>{{public_repos}}</p>
      <p><strong>Followers: </strong>{{followers}}</p>
      <a class="btn btn-info" :href="html_url" target="blank">SEE GITHUB PROFILE</a>
    </div>
    <div class="position-absolute top-0 end-0 mt-2 me-2" @click="deleteCard(index)"><i class="bi bi-x-lg fs-3"></i></div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
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

<style lang="scss" scoped>
.card-container {
  border-radius: 15px;
  padding: 25px;
  text-align: center;
  max-width: 350px;
  font-family: 'Roboto', sans-serif;
  box-shadow: 12px 12px 5px lightgrey;

  img {
    border-radius: 50%;
    border: 2px solid black;
  }

  .name {
    font-weight: 700;
  }

  p {
    font-size: 18px;
  }
}
</style>