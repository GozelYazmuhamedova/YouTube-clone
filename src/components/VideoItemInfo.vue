<template>
  <div class="flex  items-start mt-3">
    <img
      :src="`https://picsum.photos/seed/film${index}/68`"
      class="mr-3 w-9 h-9 rounded-full"
    />
    <div class="text-sm">
      <span class=" font-semibold text-gray-800">Video title {{index}} </span>
      <div class=" mt-1 flex items-center">
        <span>Channel name {{index}} </span>
        <BaseIcon name="checkCircle"  class="w-3.5 h-3.5 ml-1" />
      </div>
      <div v-html="summary"></div>
    </div>
    <button
      class="ml-auto -mt-1 p-1 opacity-0 group-hover:opacity-100 text-gray-500 hover:text-gray-700 hover:outline-none"
    >
      <BaseIcon name="dotsVertical" />
    </button>
  </div>
</template>

<script>
import BaseIcon from './BaseIcon.vue'
export default {
  props: ['index'],
  components: { BaseIcon },

  computed: {
    summary() {
        const days = this.index == 1 ? 'day' : 'days'
        return `${this.index}K veiws &middot; ${this.index} ${days} ago`
    }

  }
}
</script>
