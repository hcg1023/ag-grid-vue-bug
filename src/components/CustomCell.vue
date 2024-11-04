<template>
  <div>
    {{injectionValue}}
  </div>
</template>

<script setup lang="ts">
import {inject} from "vue";

const injectionValue = inject('customProvide')
</script>

<style scoped>

</style>
