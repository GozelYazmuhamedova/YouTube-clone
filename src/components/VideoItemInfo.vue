<template>
  <div class="flex  items-start mt-3">
    <img
      :src="`https://picsum.photos/seed/film${index}/68`"
      class="mr-3 w-9 h-9 rounded-full"
    />
    <div class="text-sm">
      <span class=" font-semibold text-gray-800">Video title {{ index }} </span>
      <div class=" mt-1 flex">
        <BaseTooltip :text="channelName" top>
          <span>{{ channelName }} </span>
        </BaseTooltip>
        <BaseTooltip text="Verified" top>
          <BaseIcon name="checkCircle" class="w-3.5 h-3.5 ml-1" />
        </BaseTooltip>
      </div>
      <div v-html="summary"></div>
    </div>
    <VideoItemDropdown />
  </div>
</template>

<script>
import BaseIcon from './BaseIcon.vue'
import VideoItemDropdown from './VideoItemDropdown.vue'
import BaseTooltip from './BaseTooltip.vue'
export default {
  props: ['index'],

  data () {
    return {
      channelName: `Channel name ${this.index}`
    }
  },

  components: { BaseIcon, VideoItemDropdown, BaseTooltip },

  computed: {
    summary () {
      const days = this.index == 1 ? 'day' : 'days'
      return `${this.index}K veiws &middot; ${this.index} ${days} ago`
    }
  }
}
</script>
