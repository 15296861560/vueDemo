<template>
  <div>
    <div id="main"  style="width: 600px;height:400px;">
    </div>
  </div>
</template>

<script>
var echarts = require("echarts");



export default {
  mounted() {
      this.paint();
  },
  data() {
      return{
          xData:["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"],
          yData:[5, 20, 36, 10, 10, 20],
      }
  },
  methods: {
    paint() {

      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById('main'));
      // 绘制图表
      myChart.setOption({
        title: {
          text: "ECharts 入门示例",
        },
        tooltip: {},
        xAxis: {
          data: this.xData,
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: this.yData,
          },
        ],
      });
    },
  },
};
</script>