<template>
  <section class="menu__wrapper" ref="menuWrapper">
    <div class="menu__header">
      <router-link to="/">
        <img src="../assets/LogoMonstercat.svg" class="header__logo" />
      </router-link>
      <img src="../components/icons/IconCross.svg" class="header__close" @click="toggleMenu()" />
    </div>
    <div class="menu__content">
      <ul class="content__list">
        <slot v-for="item in menuItems" :key="item.id">
          <MenuItem :title="item.title" :children="item.children" />
        </slot>
      </ul>
    </div>
  </section>
</template>

<script>
import MenuItem from './MenuItem.vue'

export default {
  data() {
    return {
      menuItems: [
        {
          id: 0,
          title: 'music',
          children: [
            {
              title: 'our-music'
            },
            {
              title: 'instinct'
            },
            {
              title: 'uncaged'
            },
            {
              title: 'silk'
            }
          ]
        },
        {
          id: 1,
          title: 'artists'
        },
        {
          id: 2,
          title: 'about',
          children: [
            {
              title: 'about monstercat'
            },
            {
              title: 'diversity & inclusion'
            },
            {
              title: 'code of ethics'
            },
            {
              title: 'environmental'
            },
            {
              title: 'contact us'
            }
          ]
        },
        {
          id: 3,
          title: 'news'
        },
        {
          id: 4,
          title: 'events',
          children: [
            {
              title: 'monstercat events experience'
            },
            {
              title: 'upcomming events'
            }
          ]
        },
        {
          id: 5,
          title: 'programming',
          children: [
            {
              title: 'monstercatTv'
            },
            {
              title: 'call of the wild'
            },
            {
              title: 'silk showcase'
            },
            {
              title: 'upcomming shows'
            }
          ]
        },
        {
          id: 6,
          title: 'gold'
        },
        {
          id: 7,
          title: 'partners'
        },
        {
          id: 8,
          title: 'press'
        },
        {
          id: 9,
          title: 'player'
        },
        {
          id: 10,
          title: 'shop'
        },
        {
          id: 11,
          title: 'lost civilization'
        }
      ]
    }
  },
  components: {
    MenuItem
  },
  methods: {
    toggleMenu() {
      this.$emit('closeMenu')
    }
  },
  emits: ['closeMenu']
}
</script>

<style lang="scss">
.menu__wrapper {
  background: $color-black;
  width: 420px;
  position: fixed;
  top: 0;
  right: 0;
  transform: translateX(100%);
  z-index: 1;
  height: 100%;
  transition: transform ease-in-out 0.5s;

  &.-active {
    transform: translateX(0%);
  }

  .menu__header {
    display: flex;
    padding: 2rem;
    justify-content: space-between;

    img {
      cursor: pointer;

      &.header__logo {
        width: 180px;
      }

      &.header__close {
        filter: invert(1);
        width: 30px;
      }
    }
  }

  .menu__content {
    padding: 2rem;

    .content__list {
      .list__item {
        list-style: none;
      }
    }
  }
}
</style>
