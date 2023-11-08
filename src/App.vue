<template>
  <TheHeader />
  <router-view></router-view>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
export default {
  components: {
    TheHeader: TheHeader,
  }
}
</script>

<style lang="scss">
  #app {
    background: $color-grey;

    h1, h2, h3, h4, h5, h6, a, p, span, b, li {
      color: $color-white;
    }
  }
</style>