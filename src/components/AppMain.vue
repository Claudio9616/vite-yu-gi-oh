<script>
import { store } from '../store';
import PokemonCard from './PokemonCard.vue';
export default {
    name: 'AppMain',
    data: () => ({ store }),
    components: { PokemonCard }
}
</script>
<template>
    <div v-for="pokemon in store.pokemons">
        <PokemonCard v-bind="pokemon" />
    </div>
</template>
<style lang="scss" scoped></style>