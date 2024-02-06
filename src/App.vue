<script>
import AppMain from './components/AppMain.vue';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import { store } from './store';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/'
export default {
  name: 'yu-gi-oh',
  data: () => ({ store }),
  components: { AppMain, AppHeader },
  methods: {
    fetchPokemons(endpoint) {
      (axios.get(endpoint).then(res => {
        const pokemons = res.data.docs.map(pokemon => {
          return {
            id: pokemon._id,
            name: pokemon.name,
            type: pokemon.type1,
            image: pokemon.imageUrl
          }
        })
        store.pokemons = pokemons
      }))
    },
    fetchPokemonsTypes() {
      console.log('devo cercare')
    }
  },
  created() {
    this.fetchPokemons(endpoint)
  }
}
</script>
<template>
  <AppHeader @search-terms="fetchPokemonsTypes" />
  <AppMain />
</template>
<style lang="scss">
@use './assets/stylesass/style.scss';
</style>
<!-- per usare lo store, scarica axios e lo importi, poi crei un store.js e lo importi su App.vue, crei la costante dell'endpoint,
alla crezione della pagina segui la riga 11, in data ti destrutturi lo store o lo riassegni modifacato da te con il map come 
a riga 17. Poi importi lo store (modificato) dove ti serve in questo caso sull'appmain, lo importi, lo destrutturi nel data dell'appmain, ci 
fai un v-for, usi il v-bind col nome che hai scelto nel v-for e fai un props nel figlio, in questo caso dell'Appmain, e usi le 
chiavi che ti servono e le chiami, come più ti pare e piace-->