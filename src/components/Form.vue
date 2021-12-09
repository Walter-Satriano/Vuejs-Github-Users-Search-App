<template>
  <div class="searchbar">
    <form @submit.prevent="addUser">
      <input
        type="text"
        v-model="username"
        placeholder="GitHub Username"
        required
      />
      <button type="submit">Add Card</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Form',
  data: function() {
    return {
      username: '',
    }
  },
  props: {
    handleGitHubData: Function,
  },
  methods: {
    addUser: function() {
      axios.get(`https://api.github.com/users/${this.username}`).then(resp => {
        this.handleGitHubData(resp.data)
        this.username = ''
      })
    },
  }
}
</script>

<style scoped>
  .searchbar {
    text-align: center;
  }

  .searchbar button {
    margin-left: 15px;
  }

  .searchbar button, input {
    margin-left: 15px;
    font-size: 25px;
    padding: 10px 15px;
    border-radius: 15px;
  }
</style>
