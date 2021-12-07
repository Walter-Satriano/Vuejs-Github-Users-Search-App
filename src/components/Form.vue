<template>
  <form @submit.prevent="addUser">
    <input
      type="text"
      v-model="username"
      placeholder="GitHub Username"
      required
    />
    <button type="submit">Add Card</button>
  </form>
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
