<template>
    <HeroComponent />
    <main>
        <div class="container h-100 d-flex justify-content-center align-items-center">
            -- Content goes here --
        </div>
    </main>
</template>

<script>
import HeroComponent from './HeroComponent.vue';
    export default {
        name: 'MainComponent',
        components: {
            HeroComponent
        },
    }
</script>

<style lang="scss" scoped>
    main{
        background-color: #1c1c1c;
        color: white;
        font-size: 2rem;
    }
</style>