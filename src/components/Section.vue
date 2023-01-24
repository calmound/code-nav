<script setup lang="ts">
import { RECOMMEND } from '../constant';
</script>

<template>
  <div class="section">
    <div v-for="(item, index) in RECOMMEND" :id="item.name">
      <div class="main-title">{{ item.name }}</div>
      <div class="list">
        <a href="p.url" v-for="p in item.list" target="_blank">
          <el-card :body-style="{ padding: '12px' }" shadow="hover" class="box-card">
            <div class="title">
              {{ p.title }}
            </div>
            <div class="desc">{{ p.desc }} </div>
          </el-card>
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.section {
  height: calc(100vh - 90px);
  overflow-y: auto;
  padding: 32px;
  box-sizing: border-box;
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
  margin-bottom: 12px;
}

.box-card {
  width: 250px;
  margin-bottom: 20px;
  margin-right: 20px;
}

.box-card:hover {
  cursor: pointer;
}

.title {
  font-size: 20px;
  margin-bottom: 12px;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
}

.box-card:hover .title {
  color: rgb(117, 82, 232);
  white-space: nowrap;
}

.desc {
  height: 30px;
  font-size: 12px;
  overflow: hidden;
}
</style>
