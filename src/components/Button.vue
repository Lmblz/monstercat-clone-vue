<template>
  <button :style="getStyle" v-html="content"></button>
</template>

<script>
export default {
  props: {
    content: {
      type: String,
      required: true
    },
    background: {
      type: String
    },
    color: {
      type: String
    },
    border: {
      type: String
    }
  },
  computed: {
    getStyle() {
      let response = []
      if (this.$props) {
        if (this.$props.background) {
          response.push({ 'background-color': this.$props.background })
        }
        if (this.$props.color) {
          response.push({ color: this.$props.color })
        }
        if (this.$props.border) {
          response.push({ 'border-color': this.$props.border })
        } else if (this.$props.background) {
          response.push({ 'border-color': this.$props.background })
        }
      }
      return response
    }
  }
}
</script>

<style lang="scss">
button {
  font-size: 14px;
  padding: 1.6rem 1.8rem;
  height: 25px;
  border: solid 1px;
  line-height: 0;
  text-transform: uppercase;
  font-weight: 400;
  letter-spacing: 0.1em;

  &,
  & * {
    transition: all 0.5s;
  }

  &:hover {
    border: solid 1px white !important;
    background: white !important;

    p {
      color: black !important;
    }

    svg,
    img {
      filter: invert(1);
    }
  }
}
</style>
