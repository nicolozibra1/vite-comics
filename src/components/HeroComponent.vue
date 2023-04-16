<template>
    <div class="box-hero">
        <img src="../assets/img/jumbotron.jpg" alt="jumbotron">
    </div>
</template>

<script>
    export default {
        name: 'HeroComponent'
    }
</script>

<style lang="scss" scoped>
    .box-hero{
        width: 100%;
        height: 400px;
        overflow: hidden;

        img{
            width: 100%;
            min-height: 400px;
        }
    }
</style>