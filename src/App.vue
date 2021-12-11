<template>
  <div id="app">
    <Header />
    <Form :handleGitHubData=handleGitHubData />
    <CardList :cards=cards v-on:deleteCard="deleteCard" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
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
    Header,
    Form,
    CardList,
  },
  methods: {
    handleGitHubData(data) {
      this.cards.push(data)
    },
    deleteCard(index) {
      this.cards = this.cards
        .slice(0, index)
        .concat(this.cards.slice(index + 1, this.cards.length))
        console.log(index);
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

