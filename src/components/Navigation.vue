<template>
  <div>
<el-menu
  :default-active="activeIndex2"
  class="el-menu-demo"
  mode="horizontal"
  @select="handleSelect"
  background-color="#FFFFFF"
  text-color="black"
  active-text-color="#ffd04b">
    <el-menu-item ><img src="../assets/logo.png" style="height: 100%;"></el-menu-item>
    <el-menu-item><el-input placeholder="搜索内容" v-model="search" clearable></el-input></el-menu-item>
    <el-menu-item ><el-button type="primary" icon="el-icon-search">搜索</el-button></el-menu-item>

  <el-submenu index="1">
    <template slot="title">LGY社区</template>
    <el-menu-item index="1-1">RRS</el-menu-item>
    <el-menu-item index="1-2">SBB</el-menu-item>
    <el-menu-item index="1-3">BMS</el-menu-item>
    <el-submenu index="1-4">
      <template slot="title">选项4</template>
      <el-menu-item index="1-4-1">选项1</el-menu-item>
      <el-menu-item index="1-4-2">选项2</el-menu-item>
      <el-menu-item index="1-4-3">选项3</el-menu-item>
    </el-submenu>
  </el-submenu>
  <el-menu-item index="2"><el-link :underline="false" href="/a">注册登录</el-link></el-menu-item>
  <el-menu-item index="1"><el-link :underline="false">个人中心</el-link></el-menu-item>
</el-menu>
  </div>
</template>

<script>
export default {
  name: 'Navigation',
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1',
        search: ''
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
