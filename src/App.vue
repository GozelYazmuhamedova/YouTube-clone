<template>

  <TheHeader />
  <TheShortSidebar />
  <TheSidebar />
  <TheMobileSidebar />
  <TheCategories />
  <TheVideos />

</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheShortSidebar from './components/TheShortSidebar.vue'
import TheSidebar from './components/TheSidebar.vue'
import TheMobileSidebar from './components/TheMobileSidebar.vue'
import TheCategories from './components/TheCategories.vue'
import TheVideos from './components/TheVideos.vue'

export default {
  components: {
    TheHeader,
    TheShortSidebar,
    TheSidebar,
    TheMobileSidebar,
    TheCategories,
    TheVideos

  }
}
</script>
