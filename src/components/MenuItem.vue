<template>
  <li
    class="list__item"
    :class="{ '-has-children': children }"
    @click="openDropDown(title)"
    :ref="title"
    :style="`--height-children: ${children ? children.length * 43 + 'px' : 0 + 'px'}`"
  >
    <div class="item__wrapper">
      <p class="item__title">{{ title }}</p>
      <div class="item__icon" v-if="children">
        <img src="./icons/IconChevron.svg" />
      </div>
    </div>
    <div class="item__children -dropdown" v-if="children">
      <ul class="children__list">
        <li class="list__item" v-for="item in children" :key="title">
          <p class="item__title">
            {{ item.title }}
          </p>
        </li>
      </ul>
    </div>
  </li>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    children: {
      type: Array,
      required: false
    }
  },
  methods: {
    openDropDown(el) {
      if (this.children) {
        let elementToOpen = this.$refs[el]

        !elementToOpen.classList.contains('-active')
          ? elementToOpen.classList.add('-active')
          : elementToOpen.classList.remove('-active')
      } else {
        console.log('on ouvre pas')
      }
    }
  },
  mounted() {
    if (this.children) {
      console.log(this.children.length)
    }
  }
}
</script>

<style lang="scss" scoped>
.list__item {
  margin-bottom: 1.5rem;

  .item__wrapper {
    height: 1.25rem;

    .item__title {
      font-family: 'MonumentExtended';
      text-transform: uppercase;
      cursor: pointer;
      transition: all 0.5s;

      &:hover {
        opacity: 0.8;
      }
    }
  }

  &.-has-children {
    .item__wrapper {
      display: flex;

      .item__icon {
        position: relative;

        img {
          position: absolute;
          filter: invert(1);
          top: 50%;
          transform: translateY(-58%);
        }
      }
    }

    &:not(.-active) {
      .item__children {
        height: 0px;
      }
    }

    &.-active {
      .item__children {
        padding-top: 1rem;
        height: calc(var(--height-children) - 0.5rem);
      }
    }

    .item__children {
      overflow: hidden;
      transition: all 0.5s;

      .children__list {
        padding-left: 1rem;

        .list__item {
          height: 1.25rem;
          .item__title {
            color: $color-mid-grey !important;
          }

          &:last-of-type {
            margin-bottom: 0;
          }
        }
      }
    }
  }
}
</style>
