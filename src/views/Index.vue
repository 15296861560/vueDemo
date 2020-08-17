<template>
  <div>
    <!-- 导航栏 -->
    <navigation></navigation>
    <div>
      <div class="main">
        <el-row type="flex" justify="start" :gutter="10" style="text-align: left;">
          <el-col :xs="leftSize" :sm="leftSize" :lg="leftSize">
            <div>
              <h1>
                <i class="el-icon-menu">发现</i>
              </h1>
            </div>
              <el-tabs>
    <el-tab-pane label="最新" name="first">最新</el-tab-pane>
    <el-tab-pane label="本月最热" name="second">
      本月最热内容
      </el-tab-pane>
    <el-tab-pane label="本周最热" name="third">
      本周最热内容
      </el-tab-pane>
    <el-tab-pane label="echart绘图" name="fourth">
      <echart></echart>
      </el-tab-pane>
          <el-tab-pane label="学习" name="fifth">
      <study></study>
      </el-tab-pane>
      <el-tab-pane label="接口" name="sixth">
      <interface></interface>
      </el-tab-pane>
  </el-tabs>

          </el-col>
          <el-col :xs="rightSize" :sm="rightSize" :lg="rightSize">
            <h1>广告</h1>
          </el-col>
        </el-row>
      </div>
    </div>
    <myfooter></myfooter>
  </div>
</template>

<script>
import Study from "@/views/study.vue";
import Echart from "@/views/echart.vue";
import Interface from "@/views/interface.vue";
export default {
  components: {
    Study,
    Echart,
    Interface
  },
  data() {
    return {
      leftSize: 18,
      rightSize: 6
    };
  }
};
</script>

<style>
.main {
  padding: 20px;
  margin: 50px;
  background-color: white;
}
.font-size-l{
  font-size: large;
}
</style>
