<script>
import AppForm from './AppForm.vue';
export default {
    components: { AppForm },
    emits: ['search-terms']
}
</script>
<template>
    <div class="container">
        <h1 class="text-center text-danger border-2 border-bottom border-danger">LIST POKEMON A.P.I</h1>
        <AppForm @search-terms="$emit('search-terms', $event)" />
    </div>
</template>
<style lang="scss" scoped></style>