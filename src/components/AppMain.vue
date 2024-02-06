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
    <main class="container my-5">
        <div class="border rounded-2 border-2 border-black d-flex g-4 row row-cols-2 row-cols-md-3 row-cols-lg-5">
            <div v-for="pokemon in store.pokemons" :key="pokemon.id" class="col">
                <PokemonCard v-bind="pokemon" />
            </div>
        </div>
    </main>
</template>
<style lang="scss" scoped>
ul {
    list-style-type: none;
}
</style>
