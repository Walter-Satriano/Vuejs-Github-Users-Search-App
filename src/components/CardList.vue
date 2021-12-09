<template>
  <div class="card-list">
    <Card v-for="(card, index) in cards" :key="index"
      :avatar_url=card.avatar_url
      :name=card.name
      :blog=card.blog
      :location=card.location
      :public_repos=card.public_repos
      :html_url=card.html_url
      :followers=card.followers
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
  }
}
</script>

<style scoped>
 .card-list {
   display: flex;
 }
</style>