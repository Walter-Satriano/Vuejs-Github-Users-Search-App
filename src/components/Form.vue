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
export default {
  name: "Form",
  data: function() {
    return {
      username: '',
    }
  },
  methods: {
    addUser: function() {
      alert(this.username)
    }
  }
}
</script>
