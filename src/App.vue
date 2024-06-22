<script setup lang="ts">
import { Menu } from '@element-plus/icons-vue'
import { ref } from 'vue'
const drawer = ref(false)
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath)
  if (key == "menu") {
    drawer.value = !drawer.value;
  }
}

</script>
<template>
  <el-container>
    <el-drawer v-model="drawer" title="" direction="ltr" :with-header="false">

    </el-drawer>
    <el-header>
      <el-menu :default-active="'none'" mode="horizontal" :ellipsis="false" @select="handleSelect">
        <el-menu-item index="menu">
          <el-icon>
            <Menu />
          </el-icon>
          <el-text tag="b">Menu</el-text>
        </el-menu-item>
        <div class="flex-grow" />
        <el-menu-item index="logo">
          <el-avatar alt="logo" class="logo" src="./logo.jpg" fit="fill" size="small" />
          <el-text tag="b">Novarc</el-text>
        </el-menu-item>
      </el-menu>
    </el-header>
    <el-main>
      <RouterView />
    </el-main>
  </el-container>
</template>
<style scoped>
.flex-grow {
  flex-grow: 1;
}
</style>
