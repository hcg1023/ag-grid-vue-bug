<script setup lang="ts">
import CustomProvider from "./components/CustomProvider.vue";
import CustomCell from "./components/CustomCell.vue";
import {ref} from "vue";
import { AgGridVue } from 'ag-grid-vue3'
import {ColDef} from 'ag-grid-community'
import 'ag-grid-community/styles/ag-grid.css'
import 'ag-grid-community/styles/ag-theme-quartz.css'

const value = ref('3')
const onClick = () => {
  value.value = String(Number(value.value) + 1)
}

const rowData = [
  {
    name: 'provideValue'
  }
]
const columns: ColDef[] = [
  {
    field: 'provideValue',
    cellRenderer: CustomCell,
    width: 400
  },
]
</script>

<template>
<div>
  <CustomProvider value="1">
    <ag-grid-vue class="ag-theme-quartz" style="height: 200px; width: 400px;" :rowData="rowData"
                 :columnDefs="columns"></ag-grid-vue>
  </CustomProvider>

  <CustomProvider value="2">
    <ag-grid-vue class="ag-theme-quartz" style="height: 200px; width: 400px;" :rowData="rowData"
                 :columnDefs="columns"></ag-grid-vue>
  </CustomProvider>

  <CustomProvider :value="value">
    <ag-grid-vue class="ag-theme-quartz" style="height: 200px; width: 400px;" :rowData="rowData"
                 :columnDefs="columns"></ag-grid-vue>
    <button style="margin-top: 12px;" @click="onClick">click change value</button>
  </CustomProvider>
</div>
</template>

<style scoped>

</style>
