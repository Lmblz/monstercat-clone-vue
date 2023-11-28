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
              <a :href="network.linkUrl">
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
          linkUrl: 'https://www.instagram.com/monstercat/',
          pictoUrl: '/IconInstagram.svg'
        },
        TikTok: {
          id: 1,
          name: 'TikTok',
          linkUrl: 'https://www.tiktok.com/@monstercat',
          pictoUrl: '/IconTikTok.svg'
        },
        Twitter: {
          id: 2,
          name: 'Twitter',
          linkUrl: 'https://twitter.com/monstercat',
          pictoUrl: '/IconTwitter.svg'
        },
        Twitch: {
          id: 3,
          name: 'Twitch',
          linkUrl: 'https://www.twitch.tv/monstercat',
          pictoUrl: '/IconTwitch.svg'
        },
        Facebook: {
          id: 4,
          name: 'Facebook',
          linkUrl: 'https://www.facebook.com/monstercat',
          pictoUrl: '/IconFacebook.svg'
        },
        Discord: {
          id: 5,
          name: 'Discord',
          linkUrl: 'https://discord.com/invite/monstercat',
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
        margin-top: 3rem;
        .social-networks__list {
          .list__item {
            margin-bottom: 1rem;
            list-style: none;
          }
        }
      }
    }
  }
}
</style>
