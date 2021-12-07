<template>
  <form @submit.prevent="addUser">
    <input
      type="text"
      v-model="username"
      placeholder="Github Username"
      required
    />
    <button type="submit">Add Card</button>
  </form>
</template>

<script>

import axios from 'axios'

export default {
  name: "Form",
  data: function() {
    return {
      username: '',
    }
  },
  methods: {
    addUser: function() {
      alert(axios.get(`https://api.github.com/users/${this.username}`))
    }
  }
}
</script>
