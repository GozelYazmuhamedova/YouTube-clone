<template>
  <a class="mb-7 group">
    <VideoitemThumbnail :index="index" />
    <VideoItemInfo :index="index" />
  </a>
</template>

<script>
import VideoitemThumbnail from './VideoItemThumbnail.vue'
import VideoItemInfo from './VideoItemInfo.vue'

export default {
  components: {
    VideoitemThumbnail,
    VideoItemInfo
  },
  props: ['index']
}
</script>
