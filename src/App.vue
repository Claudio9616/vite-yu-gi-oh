<script>
import axios from 'axios';
import { store } from './store';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
export default {
  name: 'yu-gi-oh',
  data: () => ({
    pokemons: []
  }),
  created() {
    axios.get(endpoint).then(res => {
      const pokemons = res.data.docs.map(pokemon => {
        return {
          id: pokemon._id,
          name: pokemon.name,
          type: pokemon.type1,
          image: pokemon.imageUrl
        }
      })
      this.pokemons = pokemons
    })
  }
}
</script>
<template>
  <h1 class="container text-danger">Ciao</h1>
</template>
<style lang="scss">
@use './assets/stylesass/style.scss';
</style>