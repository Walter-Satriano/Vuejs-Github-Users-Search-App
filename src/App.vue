<template>
  <div id="app">
    <Form :handleGitHubData=handleGitHubData />
  </div>
</template>

<script>
import Form from './components/Form.vue'

export default {
  name: "App",
  data: function() {
    return {
      cards: [],
    }
  },
  components: {
    Form,
  },
  methods: {
    handleGitHubData(data) {
      this.cards.push(data)
    }
  }
}
</script>

