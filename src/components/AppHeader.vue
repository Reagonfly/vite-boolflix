<script>
export default {
    props: ['message']
}
</script>

<template lang="">
    <header class="container-fluid bg-dark">
        <h1 class="flix-style">{{ message }}</h1>
    </header>
</template>

<style lang="scss" scoped>
    @use '../styles/generals.scss' as *;
    @use '../styles/partials/mixins.scss' as *;
    header{
        .flix-style{
            font-size: 61px;
            color: red;
            margin: 2rem 3rem;
            font-weight: 700;
        }

    }
</style>