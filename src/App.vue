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
      this.pokemons = res.data.docs
    })
    console.log(endpoint)
  }

}
</script>
<template>
  <h1 class="container text-danger">Ciao</h1>
</template>
<style lang="scss">
@use './assets/stylesass/style.scss';
</style>