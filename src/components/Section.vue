<script setup lang="ts">
import { RECOMMEND } from '../constant';
</script>
<template>
  <div class="section">
    <div v-for="(item, index) in RECOMMEND">
      <div class="main-title">{{ item.name }}</div>
      <div class="list">
        <a href="p.url" v-for="p in item.list" target="_blank">
          <el-card shadow="hover" class="box-card">
            <template #header>
              <div class="card-header">
                {{ p.title }}
              </div>
            </template>
            <div>{{ p.desc }}</div>
          </el-card>
        </a>
      </div>
    </div>
  </div>
</template>
<style scoped>
.section {
  flex: 1;
  flex-wrap: wrap;
  margin-left: 32px;
}

.main-title {
  font-size: 25px;
  font-weight: bold;
  margin-bottom: 12px;
}

.list {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
}

.box-card {
  width: 250px;
  margin-bottom: 20px;
  margin-right: 20px;
}

.box-card:hover {
  cursor: pointer;
}

.box-card:hover .card-header {
  color: rgb(117, 82, 232);
}
</style>
