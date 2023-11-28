<template>
  <TheHeader />
  <router-view></router-view>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
export default {
  components: {
    TheHeader: TheHeader
  }
}
</script>

<style lang="scss">
#app {
  background-color: $color-background-page;
  background-image: url('https://cdn.monstercat.com/background-tile.webp');

  &:after {
    content: '';
    position: fixed;
    width: 300%;
    height: 300%;
    top: -100%;
    left: -100%;
    z-index: 0;
    opacity: 0.5;
    background-image: url('https://cdn.monstercat.com/background-tile.webp');
    background-repeat: repeat;
    background-attachment: scroll;
    animation: grain 8s steps(10) infinite;
  }

  @keyframes grain {
    0%,
    100% {
      -webkit-transform: translate(0, 0);
      -moz-transform: translate(0, 0);
      -o-transform: translate(0, 0);
      transform: translate(0, 0);
    }

    10% {
      -webkit-transform: translate(-5%, -10%);
      -moz-transform: translate(-5%, -10%);
      -o-transform: translate(-5%, -10%);
      transform: translate(-5%, -10%);
    }
    20% {
      -webkit-transform: translate(-15%, 5%);
      -moz-transform: translate(-15%, 5%);
      -o-transform: translate(-15%, 5%);
      transform: translate(-15%, 5%);
    }
    30% {
      -webkit-transform: translate(7%, -25%);
      -moz-transform: translate(7%, -25%);
      -o-transform: translate(7%, -25%);
      transform: translate(7%, -25%);
    }
    40% {
      -webkit-transform: translate(-5%, 25%);
      -moz-transform: translate(-5%, 25%);
      -o-transform: translate(-5%, 25%);
      transform: translate(-5%, 25%);
    }
    50% {
      -webkit-transform: translate(-15%, 10%);
      -moz-transform: translate(-15%, 10%);
      -o-transform: translate(-15%, 10%);
      transform: translate(-15%, 10%);
    }
    60% {
      -webkit-transform: translate(15%, 0%);
      -moz-transform: translate(15%, 0%);
      -o-transform: translate(15%, 0%);
      transform: translate(15%, 0%);
    }
    70% {
      -webkit-transform: translate(0%, 15%);
      -moz-transform: translate(0%, 15%);
      -o-transform: translate(0%, 15%);
      transform: translate(0%, 15%);
    }
    80% {
      -webkit-transform: translate(3%, 35%);
      -moz-transform: translate(3%, 35%);
      -o-transform: translate(3%, 35%);
      transform: translate(3%, 35%);
    }
    90% {
      -webkit-transform: translate(-10%, 10%);
      -moz-transform: translate(-10%, 10%);
      -o-transform: translate(-10%, 10%);
      transform: translate(-10%, 10%);
    }
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6,
  a,
  p,
  span,
  b,
  li,
  figcaption,
  strong {
    color: $color-white;
  }
}
</style>
