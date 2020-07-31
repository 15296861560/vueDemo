<template>
  <div>


    <div>
      <el-table
        ref="checkList"
        :row-class-name="tableRowClassName"
        :data="tableData1"
        height="140"
        class="my-table"
        style=" background-color:rgba(122,15 ,15, 0.5);"
        @mouseenter.native="stopMove1"
        @mouseleave.native="keepMove1"
      >
        <el-table-column prop="inspectionNo" label="检验单号"></el-table-column>
        <el-table-column prop="workNo" label="工单号"></el-table-column>
        <el-table-column prop="productCode" label="产品编码"></el-table-column>
        <el-table-column prop="productName" label="产品名称"></el-table-column>
        <el-table-column prop="qty" label="数量"></el-table-column>
        <el-table-column prop="workshop" label="车间"></el-table-column>
        <el-table-column prop="productionLine" label="产线"></el-table-column>
        <el-table-column prop="team" label="班组"></el-table-column>
        <el-table-column prop="customer" label="客户"></el-table-column>

      </el-table>
        <el-table
          :data="tableData2"
          height="228"
          class="my-table"
          :show-header="status"
          @mouseenter.native="stopMove2"
          @mouseleave.native="keepMove2"
        >
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
    </div>
  </div>
</template>
<script>
export default {

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
  methods: {
    //调整表1样式
    tableRowClassName({ row, rowIndex }) {
      return "warning-row";
    },


    tableMove1() {
      var x = this.tableData2[0];
      let t = document.getElementsByClassName("el-table__body-wrapper");
      let maxHeight = t[0].scrollHeight - t[0].offsetHeight;
      t[0].scrollTop++;

      if (t[0].scrollTop > maxHeight) {
        t[0].scrollTop = 0;
      }

    },
    tableUpdate1() {
      let t = document.getElementsByClassName("el-table__body-wrapper");
      var x = this.tableData1[0];
      this.tableData1.shift();
      this.tableData1.push(x);
      t[0].scrollTop -= 59;
    },
    tableUpdate2() {
      let t = document.getElementsByClassName("el-table__body-wrapper");
      var y = this.tableData2[0];
      this.tableData2.shift();
      this.tableData2.push(y);
      t[1].scrollTop -= 59;
    },
    tableMove2() {
      // var y = this.tableData2[0];
      // this.tableData2.shift();
      // this.tableData2.push(y);
      let t = document.getElementsByClassName("el-table__body-wrapper");
      let maxHeight = t[1].scrollHeight - t[1].offsetHeight;
      t[1].scrollTop++;

      if (t[1].scrollTop > maxHeight) {
        t[1].scrollTop = 0;
      }

      // this.tableDataB = this.tableData2.slice(0, this.b);
      // this.tableData2.splice(0, this.b);
      // this.tableDataB.forEach((element) => {
      //   this.tableData2.push(element);
      // });
    },

    //表一停止移动
    stopMove1() {
      this.flat1 = false;
    },
    //表一继续移动
    keepMove1() {
      this.flat1 = true;
    },
    //表二停止移动
    stopMove2() {
      this.flat2 = false;
    },
    //表二继续移动
    keepMove2() {
      this.flat2 = true;
    },
  },

  mounted() {
    if (this.timer1) {
      clearInterval(this.timer1);
    } else {
      this.timer1 = setInterval(() => {
        //滚动表格
        if (this.flat1) this.tableMove1();
        if (this.flat2) this.tableMove2();
      }, 100);
    }

    if (this.timer2) {
      clearInterval(this.timer2);
    } else {
      this.timer2 = setInterval(() => {
        //删除添加数据
        if (this.flat1) this.tableUpdate1();
        if (this.flat2) this.tableUpdate2();
      }, 5900);
    }
  },
  destroyed(){
    clearInterval(this.timer1);
    clearInterval(this.timer2);
  }
};
</script>

<style >
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active 用于 2.1.8 以下版本 */ {
  transform: translateX(10px);
  opacity: 0;
}

.el-table .warning-row {
  background: rgba(122, 15, 15, 0.5);
  /* position:fixed;
	top:30px;
	right:5px; */
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
  bottom: 10px;
  top: 10px;
  /* box-shadow: 0px 0px 10px #21dce3 inset; */
}

.pos_fixed {
  position: fixed;
  top: 30px;
  right: 5px;
}
</style>