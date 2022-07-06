<template>
  <div class="space-y-2.5 text-black text-sm mt-5">
    <div
      v-for="(label, index) in searchPredictions"
      :key="label"
      class="flex items-center"
    >
      <BaseCheckBox
        :id="index"
        :value="label"
        v-bind="$attrs"
        v-model="modelValue"
      >
       {{ label }}
      </BaseCheckBox>
    </div>
  </div>
</template>

<script>
import BaseCheckBox from './BaseCheckBox.vue'

export default {
  components: {
    BaseCheckBox
  },

  props: {
    searchPredictions: Array,
    modelValue: Array
  }
}
</script>
