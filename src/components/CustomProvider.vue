<template>
  <div style="margin-bottom: 12px;">
    <div style="margin-bottom: 12px;">The provide value is {{value}}</div>
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
import {provide, toRefs} from 'vue'

const props = defineProps<{
  value: string
}>()
const {value} = toRefs(props)

provide('customProvide', value)
</script>

<style scoped>

</style>
