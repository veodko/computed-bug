<script setup>
import { ref } from 'vue'
import SelectWrapper from './SelectWrapper.vue'

const value = ref()
</script>

<template>
Selected value: {{ value }}<br><br>
<SelectWrapper v-model="value" :items="['item 1', 'item 2', 'item 3']"/>
</template>