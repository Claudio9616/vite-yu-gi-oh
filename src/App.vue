<script>
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import { store } from './store';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
export default {
  name: 'yu-gi-oh',
  data: () => ({ store }),
  components: { AppMain },
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
      store.pokemons = pokemons
    })
  }
}
</script>
<template>
  <h1 class="container text-center text-danger border-2 border-bottom border-danger">LIST POKEMON A.P.I</h1>
  <AppMain />
</template>
<style lang="scss">
@use './assets/stylesass/style.scss';
</style>