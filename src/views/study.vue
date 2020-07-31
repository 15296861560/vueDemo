<template>
  <div>
    <el-row type="flex" justify="start" :gutter="10" style="text-align: left;">
      <el-col :xs="leftSize" :sm="leftSize" :lg="leftSize">
        <el-radio-group v-model="isCollapse" style="margin-bottom: 20px;">
          <el-radio-button :label="false">展开</el-radio-button>
          <el-radio-button :label="true">收起</el-radio-button>
        </el-radio-group>
        <el-menu
          default-active="1-1"
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose"
          :collapse="isCollapse"
        >
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item-group>
              <span slot="title">例子</span>
              <el-menu-item index="1-1" @click="choose('1-1')">自动滚动表格</el-menu-item>
              <el-menu-item index="1-2" @click="choose('1-2')">画角</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <span slot="title">选项4</span>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3" disabled>
            <i class="el-icon-document"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">导航四</span>
          </el-menu-item>
        </el-menu>
      </el-col>
      <el-col :xs="rightSize" :sm="rightSize" :lg="rightSize">
        <el-time-select
          v-model="value"
          :picker-options="{
    start: '08:30',
    step: '00:15',
    end: '18:30'
  }"
          placeholder="选择时间"
        ></el-time-select><br><br>
        <inspectionList v-if="selectIndex=='1-1'"></inspectionList>
        <cssDrawAngle v-else-if="selectIndex=='1-2'"></cssDrawAngle>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import InspectionList from "@/views/examples/inspectionList.vue";
import CssDrawAngle from "@/views/examples/cssDrawAngle.vue";
export default {
    components: {
    InspectionList,
    CssDrawAngle,
  },
  data() {
    return {
      isCollapse: true,
      leftSize: 6,
      rightSize: 18,
      value: "",
      selectIndex:'1-1'
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    choose(index){
      this.selectIndex=index;
    }
  }
};
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
</style>
