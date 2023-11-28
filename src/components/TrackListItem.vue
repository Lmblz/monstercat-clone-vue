<template>
  <div class="tracklist__item">
    <div class="item__wrapper">
      <div class="item__index">
        <p>{{ index }}</p>
        <img src="./icons/IconPlay.svg" />
      </div>
      <div class="item__main-infos">
        <p class="title">{{ title }}</p>
        <p class="artist">{{ artist }}</p>
      </div>
      <div class="item__secondary-infos">
        <p>{{ duration }}</p>
        <img src="./icons/IconShare.svg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String
    },
    duration: {
      type: String
    },
    artist: {
      type: String
    },
    index: {
      type: Number
    }
  }
}
</script>

<style lang="scss" scoped>
.tracklist__item {
  .item__wrapper {
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 1.2rem 0;

    .item__index {
      display: flex;
      gap: 30px;
      font-size: 18px;
      align-items: center;

      p {
        width: 30px;
      }

      img {
        width: 30px;
      }
    }
    .item__main-infos {
      font-size: 18px;
      font-weight: 600;
      width: 100%;

      .artist {
        font-size: 14px;
      }
    }

    .item__secondary-infos {
      display: flex;
      align-items: center;
      gap: 30px;
      font-size: 18px;

      img {
        width: 18px;
      }
    }
  }
}
</style>
