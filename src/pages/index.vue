<script setup lang="ts">
import Section from '../components/Section.vue'
import { RECOMMEND } from '../constant';

</script>

<template>
  <div class="header">
    前端导航
  </div>
  <div class="container">
    <el-menu default-active="2" class="nav">
      <el-menu-item :index="`${index}`" v-for="(item, index) in RECOMMEND">
        <el-icon><icon-menu /></el-icon>
        <span>{{ item.name }}</span>
      </el-menu-item>
    </el-menu>
    <Section />
  </div>

</template>

<style scoped>
.header {
  font-size: 25px;
  padding: 20px;
  font-weight: bold;
  box-shadow: #888;
}

.container {
  display: flex;
}


.nav {
  width: 200px;
}
</style>
