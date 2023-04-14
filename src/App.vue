<template>
  <HeaderComponent />
  <MainComponent />
  <BannerComponent />
  <FooterComponent />
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import BannerComponent from './components/BannerComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponent,
      BannerComponent,
      FooterComponent
    }
  }
</script>

<style lang="scss" scoped>

</style>

