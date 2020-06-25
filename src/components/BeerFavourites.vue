<template>
<div>
    <ul v-if="favouriteBeers.length > 0">
        <li v-for="favouriteBeer in favouriteBeers" :key="favouriteBeer">{{favouriteBeer}}</li>
    </ul>
</div>
</template>

<script>
export default {
    props: ['favouriteBeers']
}
</script>

<style>

</style>

// 
// 