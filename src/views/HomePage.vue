<template>
  <main class="content">
    <header class="content__header">
      <div class="header__background">
        <img :src="album.background" />
      </div>
      <div class="header__content">
        <figure class="content__image">
          <img :src="album.image" />
          <figcaption class="">
            <i
              ><span :style="{ color: album.color }">{{ album.name }}</span> - Released
              {{ album.releaseDate }}</i
            >
          </figcaption>
        </figure>
        <div class="content__infos">
          <h1>{{ album.name }}</h1>
          <p class="font-monument">{{ artist.name }}</p>
          <div class="infos__buttons">
            <my-button
              :background="album.color"
              content="<p class='font-monument'>Listen now</p>"
            ></my-button>
            <my-button
              background="transparent"
              border="white"
              content="<p class='font-monument'>Share</p>"
            ></my-button>
          </div>
        </div>
      </div>
    </header>
    <section class="content__main">
      <div class="main__top">
        <h2>Stream it you way</h2>
        <div class="top__players">
          <my-button
            class="players__item"
            v-for="player in players"
            :key="player.name"
            border="#ffffff"
            background="#00000000"
            :content="`<a href='${player.link}'><img src='/Icon${
              player.name.split(' ')[0]
            }.svg' /></a>`"
          ></my-button>
        </div>
        <div class="top__tracklist">
          <h2>Track list</h2>
          <TrackList :data="tracklistData" />
        </div>
      </div>
      <div class="main__video">
        <h2>Music Video</h2>
        <div class="video__player">
          <iframe
            width="1568"
            height="882"
            src="https://www.youtube.com/embed/7nObtWENgxA"
            title="Conro - Therapy [Monstercat Lyric Video]"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            allowfullscreen
          ></iframe>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import MyButton from '../components/Button.vue'
import TrackList from '../components/TrackList.vue'

export default {
  name: 'HomePage',
  data() {
    return {
      artist: {
        name: 'Conro'
      },
      album: {
        name: 'Level Days',
        image:
          'https://cdx.monstercat.com/resized/8a169d846576fcdad7a0a6e04d371eb05b2a9397/600.webp',
        background:
          'https://cdx.monstercat.com/resized/8a169d846576fcdad7a0a6e04d371eb05b2a9397/1024.webp',
        color: '#50A584',
        releaseDate: 'May 22, 2020',
        tracklist: [
          {
            title: 'The Small Things',
            duration: '3:35'
          },
          {
            title: 'Without Your Love',
            duration: '3:09'
          },
          {
            title: 'Therapy',
            duration: '3:06'
          },
          {
            title: 'Fighters',
            duration: '3:46'
          },
          {
            title: 'Way Up',
            duration: '3:32'
          },
          {
            title: 'Waiting',
            duration: '3:07'
          },
          {
            title: 'Dreaming',
            duration: '2:57'
          },
          {
            title: 'Tattoo',
            duration: '3:29'
          },
          {
            title: 'Out for the Night',
            duration: '3:05'
          },
          {
            title: 'Overdue',
            duration: '2:48'
          },
          {
            title: 'Say It',
            duration: '3:04'
          },
          {
            title: 'Here to Stay',
            duration: '2:44'
          }
        ]
      },
      players: [
        {
          name: 'Monstercat Player',
          link: 'https://player.monstercat.app/release/MCLP017'
        },
        {
          name: 'Bandcamp',
          link: 'https://monstercatmedia.bandcamp.com/album/level-days'
        },
        {
          name: 'Soundcloud',
          link: 'https://soundcloud.com/monstercat/sets/conro-level-days'
        },
        {
          name: 'Apple Music',
          link: 'https://music.apple.com/ca/album/level-days/1508531211'
        },
        {
          name: 'Youtube',
          link: 'https://www.youtube.com/watch?v=7nObtWENgxA&list=PLyBpB3ighZijdaq0QsA77iQVvE39gJ9-U&index=3&ab_channel=MonstercatInstinct'
        },
        {
          name: 'Spotify',
          link: 'https://open.spotify.com/playlist/4vM8ONc8HQ9odCaEZTEv89?si=7DJVqY5dTJm6rfylntpAHg&nd=1&dlsi=69200e8f08ef4db6'
        }
      ]
    }
  },
  components: {
    MyButton,
    TrackList
  },
  computed: {
    tracklistData() {
      let response = {
        tracklist: this.album.tracklist,
        artist: this.artist.name
      }
      return response
    }
  }
}
</script>

<style lang="scss" scoped>
.content {
  position: relative;
  z-index: 1;
  .content__header {
    position: relative;
    //height: 100vh;

    .header__background {
      pointer-events: none;
      max-height: 100vh;
      overflow: hidden;
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      -webkit-mask-image: linear-gradient(180deg, black 50%, transparent 100%);
      mask-image: linear-gradient(180deg, black 50%, transparent 100%);

      img {
        filter: blur(4px) contrast(1.2);
        opacity: 0.3;
        width: 100%;
        transform: translateY(-20%);
      }
    }
    .header__content {
      position: relative;
      z-index: 1;
      padding-top: 12rem;
      max-width: 1200px;
      margin: auto;
      display: flex;
      gap: 5rem;

      .content__image {
        margin: 0 0 0 20px;
        display: flex;
        flex-direction: row-reverse;
        position: relative;

        img {
          width: 480px;
        }

        figcaption {
          position: absolute;
          left: -5px;
          bottom: 0;
          transform-origin: left bottom;
          transform: rotate(-90deg);

          i {
            font-weight: 500;
          }
        }
      }

      .content__infos {
        margin: auto 0;

        h1 {
          margin-bottom: 1rem;
        }

        & > p.font-monument {
          text-transform: uppercase;
          font-size: 28px;
          margin-bottom: 2rem;
        }

        .infos__buttons {
          display: flex;
          gap: 0.625rem;
        }
      }
    }
  }

  .content__main {
    max-width: 1600px;
    margin: 7rem auto 0;

    .main__top {
      .top__players {
        display: flex;

        .players__item {
          margin-top: 1rem;
          display: flex;
          align-items: center;
          justify-content: center;

          &:not(:last-of-type) {
            border-right: 0 !important;

            &:hover {
              border-right: 0 !important;
            }
          }
        }
      }

      .top__tracklist {
        margin-top: 7rem;

        h2 {
          margin-bottom: 1rem;
        }
      }
    }

    .main__video {
      margin-top: 5rem;

      h2 {
        margin-bottom: 1rem;
      }
      .video__player {
        iframe {
          width: 100%;
        }
      }
    }
  }
}
</style>
