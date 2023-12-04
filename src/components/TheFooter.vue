<template>
  <footer>
    <div class="footer__wrapper">
      <div class="footer__column">
        <div class="column__row">
          <p class="font-monument">About monstercat</p>
        </div>
        <div class="column__row">
          <p class="font-monument">Contact us</p>
        </div>
        <div class="column__row">
          <p class="font-monument">Careers</p>
        </div>
        <div class="column__row">
          <p class="font-monument">News</p>
        </div>
        <div class="column__row">
          <p class="font-monument">Press</p>
        </div>
      </div>
      <div class="footer__column">
        <div class="column__row">
          <p class="font-monument">Terms of service</p>
        </div>
        <div class="column__row">
          <p class="font-monument">Privacy policy</p>
        </div>
      </div>
      <div class="footer__column -newsletter">
        <div class="column__row">
          <p class="font-monument">Monstercat News</p>
        </div>
        <div class="column__row">
          <p><i>Don't miss a thing, stay up to date with the lastest news from us</i></p>
        </div>
        <div class="column__row -form">
          <input type="email" placeholder="Enter email" />
          <button type="submit">→</button>
        </div>
      </div>
    </div>

    <div class="footer__bottom">
      <div class="bottom__legal">
        <p><i>2011 - 2023 © Monstercat, All Rights Reserved</i></p>
        <div class="legal__networks">
          <ul>
            <li v-for="network in ListSocialNetworks" :key="id">
              <a :href="network.linkUrl"><img :src="network.pictoUrl" /></a>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <div class="footer__details">
      <p class="infos">
        <i
          >We acknowledge with gratitude the traditional, ancestral and unceded land of the Coast
          Salish peoples, including the territories of the Sḵwx̱wú7mesh (Squamish), Stó:lō and
          Səl̓ílwətaʔ/Selilwitulh (Tsleil-Waututh) and xʷməθkʷəy̓əm (Musqueam) Nations, on which
          Monstercat's Vancouver HQ stands.</i
        >
      </p>
      <p class="infos">
        <i
          >We acknowledge the unceded and ancestral territories of the Gabrielino/Tongva peoples on
          which our LA team live and work.</i
        >
      </p>
    </div>
  </footer>
</template>
<script>
export default {
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
  }
}
</script>
<style lang="scss">
footer {
  max-width: 1600px;
  margin: auto;
  z-index: 1;
  position: relative;
  margin-top: 7rem;
  padding-bottom: 5rem;

  .footer__wrapper {
    display: flex;
    gap: 0.625rem;
    border-top: solid 1px white;
    border-bottom: solid 1px white;
    padding: 3rem 0;

    .footer__column {
      flex: 1;

      .column__row {
        line-height: 1.75;

        p,
        a {
          &.font-monument {
            font-weight: 400;
            font-size: 1.125rem;
            text-transform: uppercase;
          }
        }
      }

      &.-newsletter {
        .font-monument {
          color: $color-mid-dark-grey !important;
        }

        i {
          font-size: 1rem;
        }

        .column__row {
          &:not(:last-of-type) {
            margin-bottom: 1rem;
          }

          &.-form {
            display: flex;
            border-bottom: solid 1px $color-grey;
            justify-content: space-between;
            padding-bottom: 0.5rem;

            input {
              color: $color-white;
              background: transparent;
              border: none;
              outline: none;
              font-size: 1.125rem;
              line-height: 1.75;
              padding: 1px 2px;
            }

            button {
              background-color: transparent;
              border: none;
              color: white;
              padding: 1rem 1.5rem;
              cursor: pointer;

              &:hover {
                border: none !important;
                color: black;
              }
            }
          }
        }
      }
    }
  }

  .footer__bottom {
    padding-top: 2.5rem;
    margin-bottom: 4rem;

    .bottom__legal {
      display: flex;
      justify-content: space-between;

      .legal__networks {
        ul {
          display: inline-flex;
          gap: 1rem;

          li {
            list-style: none;

            img {
              filter: invert(1);
            }
          }
        }
      }
    }
  }

  .footer__details {
    width: 60%;
    margin: auto;
    text-align: center;

    p:first-of-type {
      margin-bottom: 1rem;
    }
  }
}
</style>
