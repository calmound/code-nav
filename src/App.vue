<template>
  <el-config-provider>
    <Index />
  </el-config-provider>
</template>

<script setup lang="ts">
import { defineComponent } from 'vue'
import { ElConfigProvider } from 'element-plus'
import Index from './pages/index.vue'

defineComponent({
  components: {
    ElConfigProvider,
  },
})
</script>