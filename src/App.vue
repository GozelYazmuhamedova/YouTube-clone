<template>
  <div class="fixed w-full z-30">
    <TheHeader @toggle-sidebar="toggleSidebar" />
  <TheCategories :is-sidebar-open="isSidebarOpen" />
  </div>
  <TheCompactSidebar v-if="isCompactSidebarOpen" />
  <TheSidebar v-if="isSidebarOpen" />
  <TheMobileSidebar
    :is-open="isMobileSidebarOpen"
    @close="closeMobileSidebar"
  />
  <TheVideos :is-sidebar-open="isSidebarOpen" />
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheCompactSidebar from './components/TheCompactSidebar.vue'
import TheSidebar from './components/TheSidebar.vue'
import TheMobileSidebar from './components/TheMobileSidebar.vue'
import TheCategories from './components/TheCategories.vue'
import TheVideos from './components/TheVideos.vue'

export default {
  components: {
    TheHeader,
    TheCompactSidebar,
    TheSidebar,
    TheMobileSidebar,
    TheCategories,
    TheVideos
  },

  data () {
    return {
      isCompactSidebarActive: false,
      isCompactSidebarOpen: false,
      isMobileSidebarOpen: false,
      isSidebarOpen: false
    }
  },

  mounted () {
    this.onResize()

    window.addEventListener('resize', this.onResize)
  },

  methods: {
    onResize () {
      if (window.innerWidth < 768) {
        this.isCompactSidebarOpen = false
        this.isSidebarOpen = false
      } else if (window.innerWidth < 1280) {
        this.isCompactSidebarOpen = true
        this.isSidebarOpen = false
      } else {
        this.isCompactSidebarOpen = this.isCompactSidebarActive
        this.isSidebarOpen = !this.isCompactSidebarActive
        this.isMobileSidebarOpen = false
      }
    },

    toggleSidebar () {
      if (window.innerWidth >= 1280) {
        this.isCompactSidebarActive = !this.isCompactSidebarActive

        this.onResize()
      } else {
        this.openMobileSidebar()
      }
    },

    openMobileSidebar () {
      this.isMobileSidebarOpen = true
    },

    closeMobileSidebar () {
      this.isMobileSidebarOpen = false
    }
  }
}
</script>
