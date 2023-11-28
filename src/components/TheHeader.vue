<template>
  <header>
    <div class="header__wrapper">
      <div class="header__left-side">
        <img
          src="../assets/LogoMonstercat-NoText.webp"
          alt="Logo Monstercat no text"
          height="50"
          width="50"
        />
      </div>
      <div class="header__right-side">
        <div class="right-side__menu">
          <div class="menu__icon">
            <img src="./icons/IconMenu.svg" alt="Menu" @click="toggleMenu()" />
          </div>
          <TheMenu ref="menu" @closeMenu="toggleMenu" />
        </div>
        <div class="right-side__social-networks">
          <ul class="social-networks__list">
            <li class="list__item" v-for="network in ListSocialNetworks" :key="network.id">
              <a :href="network.pictoUrl">
                <img :src="network.pictoUrl" :alt="network.name" />
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import TheMenu from './TheMenu.vue'

export default {
  name: 'TheHeader',
  components: {
    TheMenu: TheMenu
  },
  data() {
    return {
      ListSocialNetworks: {
        Instagram: {
          id: 0,
          name: 'Instagram',
          linkUrl: '/',
          pictoUrl: '/IconInstagram.svg'
        },
        TikTok: {
          id: 1,
          name: 'TikTok',
          linkUrl: '/',
          pictoUrl: '/IconTikTok.svg'
        },
        Twitter: {
          id: 2,
          name: 'Twitter',
          linkUrl: '/',
          pictoUrl: '/IconTwitter.svg'
        },
        Twitch: {
          id: 3,
          name: 'Twitch',
          linkUrl: '/',
          pictoUrl: '/IconTwitch.svg'
        },
        Facebook: {
          id: 4,
          name: 'Facebook',
          linkUrl: '/',
          pictoUrl: '/IconFacebook.svg'
        },
        Discord: {
          id: 5,
          name: 'Discord',
          linkUrl: '/',
          pictoUrl: '/IconDiscord.svg'
        }
      }
    }
  },
  methods: {
    toggleMenu() {
      let menu = this.$refs.menu
      let menuWrapper = menu.$refs.menuWrapper
      if (!menuWrapper.classList.contains('-active')) {
        menuWrapper.classList.add('-active')
      } else {
        menuWrapper.classList.remove('-active')
      }
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  position: fixed;
  top: 0;
  padding: 1.5rem 2rem;
  width: calc(100% - 4rem);
  z-index: 5;

  .header__wrapper {
    display: flex;
    justify-content: space-between;
    .header__right-side {
      img {
        filter: invert(1);
        transition: all 0.5s;
        cursor: pointer;

        &:hover {
          filter: invert(0.8);
        }
      }

      .right-side__social-networks {
        .social-networks__list {
          .list__item {
            list-style: none;
          }
        }
      }
    }
  }
}
</style>
