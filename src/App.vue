<script setup>
import { reactive } from 'vue'
let index = 0
const tableData = reactive([])
function load() {
  for (let i = 0; i < 5; i++)
    tableData.push({ name: index++ })
}
</script>

<template>
  <main>
    <div class="cal">
      <el-table :data="tableData">
        <el-table-column prop="name" label="Name" width="120" />
        <template #append>
          <el-button type="primary" text style="width: 100%;" @click="load">加载更多</el-button>
        </template>
      </el-table>
    </div>
    <div class="cal">
      <div style="height: 40px;">name</div>
      <div v-for="i in tableData" style="height: 40px;">{{ i.name }}</div>
      <el-button type="primary" text style="width: 100%;" @click="load">加载更多</el-button>
    </div>
  </main>
</template>

<style>
.cal {
  height: 200px;
  overflow: auto;
}
</style>
