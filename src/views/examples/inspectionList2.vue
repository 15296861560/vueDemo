<template>
  <div>
    <div style="border: solid;border-color: aqua;">
      <tr>
        <th>检验单号</th>
        <th>工单号</th>
        <th>产品编码</th>
        <th>产品名称</th>
        <th>数量</th>
        <th>车间</th>
        <th>产线</th>
        <th>班组</th>
        <th>客户</th>
      </tr>

      <transition-group name="flip-list" tag="ul" style="padding: 0px;height: 100px; overflow: hidden;">
        <li v-for="item in tableData1" v-bind:key="item">
          <tr>
            <td>
              <span>{{item.inspectionNo}}</span>
            </td>
            <td>
              <span>{{item.workNo}}</span>
            </td>
            <td>
              <span>{{item.productCode}}</span>
            </td>
            <td>
              <span>{{item.productName}}</span>
            </td>
            <td>
              <span>{{item.qty}}</span>
            </td>
            <td>
              <span>{{item.workshop}}</span>
            </td>
            <td>
              <span>{{item.productionLine}}</span>
            </td>
            <td>
              <span>{{item.team}}</span>
            </td>
            <td>
              <span>{{item.customer}}</span>
            </td>
          </tr>
        </li>
      </transition-group>
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
        {
          inspectionNo: "55555",
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

    tableUpdate1() {
      let x = this.tableData1[0];
      this.tableData1.shift();
      this.tableData1.push(x);
    },
    tableUpdate2() {
      let x = this.tableData2[0];
      this.tableData2.shift();
      this.tableData2.push(x);
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
    this.timer1 = setInterval(() => {
      //滚动表格
      if (this.flat1) this.tableUpdate1();
      if (this.flat2) this.tableUpdate2();
    }, 1000);
  },
  destroyed() {
    clearInterval(this.timer1);
    // clearInterval(this.timer2);
  },
};
</script>

<style >
th,
td {
  /* padding: 1rem; */
  width: 5rem;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  max-width: 5rem;
  height: 20px;
}

.td:hover {
  overflow: auto;
  text-overflow: inherit;
}

li {
  list-style-type: none;
}

.flip-list-move {
  transition: transform 1s;
}
</style>