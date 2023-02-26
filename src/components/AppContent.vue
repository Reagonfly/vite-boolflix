<script>
import MoovieCard from './MoovieCard.vue';

export default {
    components:{
        MoovieCard
    },
    props:{
        moovies: Array
    }
}
</script>

<template lang="">
    <div class="container">
        <div class="d-flex justify-content-between flex-wrap">
            <MoovieCard v-for="(item, index) in moovies" :key="index" :moovie="item" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use '../styles/generals.scss' as *;
    @use '../styles/partials/mixins.scss' as *;
</style>