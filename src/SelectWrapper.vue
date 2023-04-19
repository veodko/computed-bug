<script setup>
import { computed, ref, watch } from 'vue'
const props = defineProps({
  items: Array,
  modelValue: String,
})

const emit = defineEmits(['update:modelValue'])

const mappedValues = computed(() => {
  return props.items.map(i => {
    console.log('Mapping value', i)
    
    return i + '-mapped'
  })
})

/*const mappedValues = ref([])
watch(
  () => props.items,
  (newItems) => {
    mappedValues.value = newItems.map((i) => {
      console.log('Mapping via watch', i)
      return i + '-mapped'
    })
  },
  { immediate: true }
)*/
</script>

<template>
  <select @change="emit('update:modelValue', $event.target.value)">
    <option
      v-for="val in mappedValues"
      :key="val"
      :value="val"
    >
      {{ val }}
    </option>
  </select>
</template>
