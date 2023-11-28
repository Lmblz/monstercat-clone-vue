<template>
  <div class="tracklist__wrapper">
    <TrackListItem
      v-for="(track, index) in data.tracklist"
      :key="track.title"
      :title="track.title"
      :duration="track.duration"
      :index="index + 1"
      :artist="data.artist"
    />
  </div>
</template>

<script>
import TrackListItem from './TrackListItem.vue'
export default {
  props: {
    data: {
      type: Object,
      required: true,
      default: {}
    }
  },
  components: {
    TrackListItem
  }
}
</script>
