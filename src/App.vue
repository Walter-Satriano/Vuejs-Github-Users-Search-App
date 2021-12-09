<template>
  <div id="app">
    <Form :handleGitHubData=handleGitHubData />
    <CardList :cards=cards />
  </div>
</template>

<script>
import Form from './components/Form.vue'
import CardList from './components/CardList.vue'

export default {
  name: 'App',
  data: function() {
    return {
      cards: [],
    }
  },
  components: {
    Form,
    CardList,
  },
  methods: {
    handleGitHubData(data) {
      this.cards.push(data)
    }
  },
  watch: {
    cards() {
      localStorage.setItem("cards", JSON.stringify(this.cards))
    }
  },
  mounted() {
    if(localStorage.getItem("cards")) {
      this.cards = JSON.parse(localStorage.getItem("cards"))
    }
  }
}
</script>

