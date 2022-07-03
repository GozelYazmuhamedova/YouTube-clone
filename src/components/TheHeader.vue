<template>
  <header :class="classes">
    <div
      :class="[
        'lg:w-1/4',
        'flex',
        isMobileSearchShown ? 'opacity-0' : 'opacity-100'
      ]"
    >
      <div class="flex items-center  xl:w-64 xl:bg-white pl-4">
        <button @click="$emit('toggleSidebar')" class="mr-3 sm:ml-2 sm:mr-4">
          <BaseIcon name="menu" />
        </button>
        <LogoMain />
      </div>
    </div>
    <TheSearchWrapper
      v-show="isSearchShown"
      :is-small-screen="isSmallScreen"
      @close="closeMobileSearch"
    />

    <div
      :class="[
        'flex',
        'items-center',
        'justify-end',
        'lg:w-1/4',
        'sm:space-x-4',
        'p-2',
        'sm:px-4',
        isMobileSearchShown ? 'opacity-0' : 'opacity-100'
      ]"
    >
      <BaseTooltip text="Search with your voice">
        <button class="sm:hidden p-2">
          <BaseIcon name="microphone" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <BaseTooltip text="Search">
        <button @click.stop="isMobileSearchActive = true" class="sm:hidden p-2">
          <BaseIcon name="search" class="w-5 h-5" />
        </button>
      </BaseTooltip>
      <!--dropdown-list-->
      <TheDropdownApps />

      <!--dropdown-list-->
      <TheDropdownSettings />
      <ButtonSignIn />
    </div>
  </header>
</template>

<script>
import BaseIcon from './BaseIcon.vue'
import LogoMain from './LogoMain.vue'
import BaseTooltip from './BaseTooltip.vue'
import ButtonSignIn from './ButtonSignIn.vue'
import TheDropdownApps from './TheDropdownApps.vue'
import TheDropdownSettings from './TheDropdownSettings.vue'
import TheSearchWrapper from './TheSearchWrapper.vue'

export default {
  components: {
    BaseIcon,
    LogoMain,
    BaseTooltip,
    ButtonSignIn,
    TheDropdownApps,
    TheDropdownSettings,
    TheSearchWrapper
  },

  emits: {
    toggleSidebar: null
  },

  data () {
    return {
      searchQuery: '',
      isSmallScreen: false,
      isMobileSearchActive: false,
      classes: [
        'flex',
        'justify-between',
        'w-full',
        'bg-white',
        'bg-opacity-95'
      ]
    }
  },

  computed: {
    isSearchShown () {
      return this.isMobileSearchShown || !this.isSmallScreen
    },

    isMobileSearchShown () {
      return this.isSmallScreen && this.isMobileSearchActive
    }
  },

  mounted () {
    this.onResize()

    window.addEventListener('resize', this.onResize)
  },

  methods: {
    onResize () {
      if (window.innerWidth < 640) {
        this.isSmallScreen = true
        return
      }
      this.closeMobileSearch()
      this.isSmallScreen = false
    },

    closeMobileSearch () {
      this.isMobileSearchActive = false
    }
  }
}
</script>
