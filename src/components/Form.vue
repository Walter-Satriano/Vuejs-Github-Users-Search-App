<template>
  <div class="searchbar my-5">
    <form @submit.prevent="addUser">
      <input
        type="text"
        v-model="username"
        placeholder="Insert GitHub Username"
        required
      />
      <button type="submit" class="mt-3 mt-sm-0 ms-3 text-white">Add Card</button>
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

<style lang="scss" scoped>
  .searchbar {
    text-align: center;
    font-family: 'Roboto', sans-serif;

    button, input {
      padding: 10px;
      border-radius: 10px;
      border-color: darkblue;
      font-size: 25px;
    }

    button {
      background-color: darkblue;

      &:hover {
        background-color: blue;
      }
    }
  }
</style>
