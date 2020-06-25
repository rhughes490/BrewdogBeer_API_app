<template lang="html">
<div>
    <h3>Tagline: {{selectedBeer.tagline}}</h3>
    <h3>First brewed: {{selectedBeer.first_brewed}}</h3>
    <h3>Description: {{selectedBeer.description}}</h3>
    <button v-on:click="handleClickButton">Add to favourites</button>
    <beer-favourites :favouriteBeers="favouriteBeers"></beer-favourites>
</div>
</template>

<script>
import BeerFavourites from './BeerFavourites.vue';

export default {
    name: 'beer-details',
    components: {
        'beer-favourites': BeerFavourites
    },
    data() {
        return {
            favouriteBeers: []
        }
    },
    props: ['selectedBeer'],
    methods: {
        handleClickButton: function () {  
            if (!this.favouriteBeers.includes(this.selectedBeer.name)) {
                this.favouriteBeers.push(this.selectedBeer.name)
            }
        }
    }
}
</script>

<style>

</style>