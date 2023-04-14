<template>
  <HeaderComponent />
  <MainComponent />
  <BannerComponent />
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import BannerComponent from './components/BannerComponent.vue';
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponent,
      BannerComponent
    }
  }
</script>

<style lang="scss" scoped>

</style>

