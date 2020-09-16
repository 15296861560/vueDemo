<template>
  <div>
    <label>定时器实现自动滚动</label>
    <div>
      <el-table
        :row-class-name="tableRowClassName"
        :data="tableData1"
        :show-header="status"
        height="140"
        class="my-table"
        @mouseenter.native="stopMove1"
        @mouseleave.native="keepMove1"
      >
        <el-table-column prop="inspectionNo" ></el-table-column>
        <el-table-column prop="workNo" ></el-table-column>
        <el-table-column prop="productCode" ></el-table-column>
        <el-table-column prop="productName" ></el-table-column>
        <el-table-column prop="qty" ></el-table-column>
        <el-table-column prop="workshop" label></el-table-column>
        <el-table-column prop="productionLine" ></el-table-column>
        <el-table-column prop="team" ></el-table-column>
        <el-table-column prop="customer" ></el-table-column>
      </el-table>
    </div>
    <div style="margin-top:50px;">插件实现自动滚动</div>
    <div>
      <vueSeamlessScroll :data="tableData2" class="auto-scorll-table" :class-option="classOption">
        <el-table :data="tableData2" class="custom-table-2 hidden-thead">
          <el-table-column prop="inspectionNo"></el-table-column>
          <el-table-column prop="workNo"></el-table-column>
          <el-table-column prop="productCode"></el-table-column>
          <el-table-column prop="productName"></el-table-column>
          <el-table-column prop="qty"></el-table-column>
          <el-table-column prop="workshop"></el-table-column>
          <el-table-column prop="productionLine"></el-table-column>
          <el-table-column prop="team"></el-table-column>
          <el-table-column prop="customer"></el-table-column>
        </el-table>
      </vueSeamlessScroll>
    </div>

    <div style="margin-top:50px;">html标签实现自动滚动</div>
    <div>
      <!-- 重要属性：
1.滚动方向direction（包括4个值：up、 down、 left和 right）
2.滚动方式behavior（scroll:循环滚动，默认效果； slide:只滚动一次就停止； alternate:来回交替进行滚动）
3.滚动速度scrollamount（滚动速度是设置每次滚动时移动的长度，以像素为单位）
4.滚动延迟scrolldelay（设置滚动的时间间隔，单位是毫秒）
5.滚动循环loop（默认值是-1，滚动会不断的循环下去）
6.滚动范围width、height
7.滚动背景颜色bgcolor
8.空白空间hspace、vspace-->
      <marquee
        direction="up"
        behavior="scroll"
        scrollamount="5"
        scrolldelay="0"
        loop="-1"
        width="1000"
        height="100"
        bgcolor="white"
        hspace="10"
        vspace="10"
      >
        <el-table :data="tableData3" class="custom-table-2 hidden-thead">
          <el-table-column prop="inspectionNo"></el-table-column>
          <el-table-column prop="workNo"></el-table-column>
          <el-table-column prop="productCode"></el-table-column>
          <el-table-column prop="productName"></el-table-column>
          <el-table-column prop="qty"></el-table-column>
          <el-table-column prop="workshop"></el-table-column>
          <el-table-column prop="productionLine"></el-table-column>
          <el-table-column prop="team"></el-table-column>
          <el-table-column prop="customer"></el-table-column>
        </el-table>
      </marquee>
    </div>
  </div>
</template>
<script>
import vueSeamlessScroll from "vue-seamless-scroll";
export default {
  components: {
    vueSeamlessScroll,
  },
  data() {
    return {
      tableData1: [
        {
          inspectionNo: "111111111111",
          workNo: "lab",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "222222222222",
          workNo: "lae",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "3333",
          workNo: "lbe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "444444",
          workNo: "abe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
      ],
      tableData2: [
        {
          inspectionNo: "1",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "2",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "2016",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "2-05-02-001",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "20101",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "001",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "02-001",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
      ],
      tableData3: [
        {
          inspectionNo: "1",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "2",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "2016",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "2-05-02-001",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "20101",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "001",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
        {
          inspectionNo: "02-001",
          workNo: "labe",
          productCode: "A001",
          productName: "ASN",
          qty: 10,
          workshop: "GTN",
          productionLine: "x1",
          team: "t1",
          customer: "LGY",
        },
      ],

      status: false,
      tableDataA: [],
      tableDataB: [],
      a: 2,
      b: 5,
      timer2: null,
      flat1: true,
      flat2: true,
    };
  },
  computed: {
    classOption() {
      return {
        step: 1, // 数值越大速度滚动越快
        limitMoveNum: 2, // 开始无缝滚动的数据量 this.dataList.length
        hoverStop: true, // 是否开启鼠标悬停stop
        direction: 1, // 0向下 1向上 2向左 3向右
        openWatch: true, // 开启数据实时监控刷新dom
        singleHeight: 0, // 单步运动停止的高度(默认值0是无缝不停止的滚动) direction => 0/1
        singleWidth: 0, // 单步运动停止的宽度(默认值0是无缝不停止的滚动) direction => 2/3
        waitTime: 1000, // 单步运动停止的时间(默认值1000ms)
      };
    },
  },

  methods: {
    //调整表1样式
    tableRowClassName({ row, rowIndex }) {
      return "warning-row";
    },

    // 滚动
    tableMove1() {
      var x = this.tableData2[0];
      let t = document.getElementsByClassName("el-table__body-wrapper");
      let maxHeight = t[0].scrollHeight - t[0].offsetHeight;//最大滚动高度
      t[0].scrollTop++;

      if (t[0].scrollTop > maxHeight) {
        t[0].scrollTop = 0;
      }
    },
    //更新数据
    tableUpdate1() {
      let t = document.getElementsByClassName("el-table__body-wrapper");
      var x = this.tableData1[0];
      this.tableData1.shift();
      this.tableData1.push(x);
      t[0].scrollTop -= 59;//矫正因数据变动而发生的视图变化
    },

    //表一停止移动
    stopMove1() {
      this.flat1 = false;
    },
    //表一继续移动
    keepMove1() {
      this.flat1 = true;
    },
  },

  mounted() {
    if (this.timer1) {
      clearInterval(this.timer1);
    } else {
      this.timer1 = setInterval(() => {
        //滚动表格
        if (this.flat1) this.tableMove1();
      }, 100);
    }

    if (this.timer2) {
      clearInterval(this.timer2);
    } else {
      this.timer2 = setInterval(() => {
        //删除添加数据
        if (this.flat1) this.tableUpdate1();
      }, 5900);
    }
  },
  destroyed() {
    clearInterval(this.timer1);
    clearInterval(this.timer2);
  },
};
</script>

<style lang="less">
.el-table .warning-row {
  background: rgba(122, 15, 15, 0.5);
}

.el-table tr {
  background-color: rgba(178, 190, 23, 0.5);
}

.el-table th {
  color: #80ffff;
}

.el-table--enable-row-hover .el-table__body tr:hover > td {
  background-color: #4a9899;
}

.el-table__body-wrapper::-webkit-scrollbar {
  width: 10px;
  height: 0px;
}
.my-table {
  width: 100%;
  color: white;
  background-color: rgba(23, 23, 21, 0.5);
  border-color: #00a5bb;
  border-style: solid;
  border-width: 1px;
}

.pos_fixed {
  position: fixed;
  top: 30px;
  right: 5px;
}

.auto-scorll-table {
  // height: calc(100% - 34px);
  overflow: hidden;
  height: 100px;
  border: solid;
}
.hidden-tbody.el-table {
  height: 34px;
  box-sizing: border-box;
  tbody {
    //隐藏上面表格的tbody
    display: none;
    overflow: hidden;
  }
}
.hidden-thead.el-table {
  border-top: none; //防止边框重叠
  thead {
    //隐藏下面表格的thead
    display: none;
    overflow: hidden;
  }
}
</style>