<template>
  <header class="flex fixed justify-between z-30 w-full">
    <div class="lg:w-1/4 flex">
      <div class="flex items-center  xl:w-64 xl:bg-white pl-4">
        <button class="mr-3 sm:ml-2 sm:mr-6">
         <BaseIcon  name="menu" />
        </button>
        <LogoMain />
      </div>
    </div>  

    <div
      class=" hidden p-2.5 pl-8 md:pl-12 md:px-8 lg:px-0 sm:flex items-center justify-end lg:w-1/2 flex-1 max-w-screen-md"
    >
      <TheSearch />
      <button class="ml-4">
       <BaseIcon name="microphone" class="w-5 h-5" />
      </button>
    </div>

    <div
      class="flex items-center justify-end lg:w-1/4 sm:space-x-4 p-2 sm:px-4"
    >
      <button class="sm:hidden p-2">
  <BaseIcon name="microphone" class="w-5 h-5" />
      </button>
      <button class="sm:hidden p-2">
         <BaseIcon name="search" class="w-5 h-5" />
      </button>

      <!--dropdown-list-->
      <button class="relative group p-2 focus:outline-none">
       <BaseIcon name="viewGrid" class="w-5 h-5" />
       <TheDropdownApps />
      </button>

      <!--dropdown-list-->
      <button class="relative group p-2 focus:outline-none">
     <BaseIcon name="dotsVertical" class="w-5 h-5" />
        <TheDropdownSettings />
      </button>
     <ButtonSignIn />
    </div>
  </header>
</template>



<script>
import BaseIcon from './BaseIcon.vue'
import LogoMain from './LogoMain.vue'
import TheSearch from './TheSearch.vue'
import ButtonSignIn from './ButtonSignIn.vue'
import TheDropdownApps from './TheDropdownApps.vue'
import TheDropdownSettings from './TheDropdownSettings.vue'

export default {
  components: {
    BaseIcon,
    LogoMain,
    TheSearch,
    ButtonSignIn,
    TheDropdownApps,
    TheDropdownSettings
  }
}
</script>