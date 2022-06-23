<template>
  <TheMobileSidebarOverlay>
    <aside class="hidden w-64 max-h-screen overflow-auto bg-white">
      <section class="flex items-center p-4 border-b sticky top-0 bg-white">
        <button class="mr-4 ml-2">
          <BaseIcon name="menu" />
        </button>
        <LogoMain />
      </section>
      <SidebarContent />
    </aside>
  </TheMobileSidebarOverlay>
</template>

<script>
import SidebarContent from './SidebarContent.vue'
import LogoMain from './LogoMain.vue'
import BaseIcon from './BaseIcon.vue'
import TheMobileSidebarOverlay from './TheMobileSidebarOverlay.vue'

export default {
  components: {
    SidebarContent,
    LogoMain,
    BaseIcon,
    TheMobileSidebarOverlay
  }
}
</script>
