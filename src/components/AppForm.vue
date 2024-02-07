<script>
import { store } from '../store'
export default {
    data: () => ({
        store,
        optionValue: ''
    }),
    emits: ['search-terms']
}
</script>
<template>
    <form @click.prevent="$emit('search-terms', optionValue)">
        <select class="form-select" aria-label="Default select example" v-model="optionValue">
            <option selected>Visualizza Pokemon per tipologia</option>
            <option v-for="(pokemonType, i) in  store.pokemonsTypes" :key="i" :value="pokemonType">
                {{ pokemonType }}
            </option>
        </select>
    </form>
</template>
<style lang="scss" scoped></style>