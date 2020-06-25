<template>
<div id="beerList">
    <ul>
        <list-component v-for="(beer, index) in beers" :key="index" :beer="beer"></list-component>
    </ul>
</div>
</template>

<script>
import ListComponent from './ListComponent.vue';

export default {
    props: ['beers'],
    components: {
        'list-component': ListComponent
    }
}
</script>

<style>

</style>