<template>
  <div id="app">
    <Header />
    <Form :handleGitHubData=handleGitHubData />
    <CardList :cards=cards v-on:deleteCard="deleteCard"
      class="d-flex flex-wrap justify-content-center justify-content-md-around"
    />
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

<style lang="scss" scoped>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
  @import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.7.2/font/bootstrap-icons.css");
</style>

