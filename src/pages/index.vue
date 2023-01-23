<script setup lang="ts">
import Section from '../components/Section.vue'
import { RECOMMEND } from '../constant';
import { ref } from 'vue'

let visible = ref(false)

const handleHref = (url: string) => {
  (window as any).location.href = `#${url}`
}
</script>

<template>
  <div class="header">
    前端资讯导航
  </div>
  <div class="container">
    <el-menu active-text-color="#ffd04b" background-color="#545c64" text-color="#fff" class="menu" default-active="0">
      <el-menu-item :index="`${index}`" v-for="(item, index) in RECOMMEND" @click="handleHref(item.name)">
        <el-icon><icon-menu /></el-icon>
        <span>{{ item.name }}</span>
      </el-menu-item>
    </el-menu>
    <div>
      <div class="tip">
        前端交流群，欢迎加入，与500名前端开发者一起交流，<span class="join" @click="visible = true">点击加入</span>
      </div>
      <Section />
    </div>
    <el-dialog v-model="visible" title="微信" width="300px" align-center class="dialog" >
      <span class="label">微信号: </span><span class="value">sanmu1598</span>
      <img src="../assets/wechat.jpeg" class="img" />
    </el-dialog>
  </div>

</template>

<style scoped>
.header {
  font-size: 22px;
  height: 60px;
  box-sizing: border-box;
  padding: 12px;
  font-weight: bold;
  box-shadow: 0 1px 4px rgb(0 21 41 / 8%);
}

.join {
  color: #0a7356;
  cursor: pointer;
  font-weight: bold;
}

.tip {
  position: sticky;
  left: 0;
  top: 0;
  background-color: #f0f9eb;
  height: 30px;
  line-height: 30px;
  width: 100%;
  color: #67c23a;
  font-size: 12px;
  padding-left: 20px;
}

.container {
  display: flex;
}

.menu {
  width: 200px;
  height: calc(100vh - 60px);
  background-color: #545c64;
}

.img {
  width: 200px;
  display: block;
  margin: 10px auto;
}

.dialog .label {
  margin-bottom: 12px;
}
.dialog .value {
  color: #3c4dc5;
  font-weight: bold;
}
</style>
<style>
.dialog .el-dialog__body {
  padding-top: 10px;
}
</style>