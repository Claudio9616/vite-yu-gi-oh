<script>
import { store } from '../store'
export default {
    data: () => ({
        store
    })
}
</script>
<template>
    <select class="form-select" aria-label="Default select example">
        <option selected>Visualizza Pokemon per tipologia</option>
        <option v-for="pokemonType in  store.pokemonsTypes " :value="pokemonType">
            {{ pokemonType }}
        </option>
    </select>
</template>
<style lang="scss" scoped></style>