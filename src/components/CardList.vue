<template>
  <div class="card-list-container">
    <Card v-for="(card, index) in cards" :key="index" v-on:deleteCard="deleteCard"
      :avatar_url=card.avatar_url
      :name=card.name
      :location=card.location
      :public_repos=card.public_repos
      :html_url=card.html_url
      :followers=card.followers
      :index="index"
    />
  </div>
</template>

<script>
import Card from './Card.vue'

export default {
  name: 'CardList',
  props: {
    cards: Array,
  },
  components: {
    Card,
  },
  methods: {
    deleteCard(index) {
      this.$emit('deleteCard', index)
    }
  }
}
</script>

<style lang="scss" scoped>
  .card-list-container {
    margin-bottom: 8rem;
  }
</style>