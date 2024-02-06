<script>
import { store } from '../store'
export default {
    data: () => ({
        store
    }),
    emits: ['search-terms']
}
</script>
<!-- chiedere come si risolve sto schifo -->
<template>
    <form @click.prevent="$emit('search-terms')">
        <select class="form-select" aria-label="Default select example">
            <option selected>Visualizza Pokemon per tipologia</option>
            <option v-for="pokemonType in  store.pokemonsTypes " :value="pokemonType">
                {{ pokemonType }}
            </option>
        </select>
    </form>
</template>
<style lang="scss" scoped></style>