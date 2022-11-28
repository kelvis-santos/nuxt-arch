<template>
  <div class="container-about">
    <NuxtLink to="/">Página inicial</NuxtLink>
    <block v-for="card, index in cards" :key="index"
      :name="card.name"
      :description="card.description"
      :value="card.value"
      :quantity="card.quantity"
    />
  </div>
</template>
<script>
import Block from '../../components/block/block.vue';
import CardList from '~/json/cards.json'
export default {
  name: 'about',
  data () {
    return {
      cards: CardList
    }
  },  
  components: {
    Block
  }
}
</script>
<style>
  .container-about {
    background-color: #F7F7F7;
  }
</style>