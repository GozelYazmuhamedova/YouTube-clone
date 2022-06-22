<template>
  <div class="relative">
    <img :src="`https://picsum.photos/seed/video${index}/720/404`" alt="" />
    <span
      class=" opacity-0 group-hover:opacity-100 bg-opacity-60 absolute top-0 right-0 bg-black text-white rounded-sm m-2 p-1"
    >
    <BaseIcon name="clock" class="w-5 h-5" />
    </span>
    <span
      class="opacity-0 group-hover:opacity-100 bg-opacity-60 absolute top-8 right-0 bg-black text-white rounded-sm m-2 p-1"
    >
     <BaseIcon name="menuAlt3" class="w-5 h-5" />
    </span>
    <span
      class="opacity-100 group-hover:opacity-0 duration-500 absolute bottom-0 right-0 bg-black text-white rounded-sm m-1 p-1 text-sm font-semibold"
    >
      56:45
    </span>
  </div>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
export default {
    props: ["index"],
    components: { BaseIcon }
}
</script>
