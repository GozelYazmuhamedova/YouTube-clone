<template>
  <aside
    class="hidden xl:block w-64 max-h-screen overflow-auto fixed z-20 top-0 pt-12 bg-white"
  >
  <SidebarContent />
  </aside>
</template>

<script>
import SidebarContent from './SidebarContent.vue'

export default {
  components: {
    SidebarContent
  }
}
</script>
