<template>
  <div>
    <div style="border: solid;border-color: aqua;">
      <transition-group
        name="flip-list"
        tag="ul"
        style="padding: 0px;height: 100px; overflow: hidden;"
      >
        <li v-for="item in tableData1" :key="item.inspectionNo">
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

    <div class="ani-area">
      <div class="ani">
        <li v-for="item in tableData2" :key="item.inspectionNo">
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
      </div>
      <div class="ani2">
        <li v-for="item in tableData2" :key="item.inspectionNo">
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
      </div>
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
    this.timer1 = setInterval(() => {
      //滚动表格
      if (this.flat1) this.tableUpdate1();
    }, 1000);
  },
  destroyed() {
    clearInterval(this.timer1);
    // clearInterval(this.timer2);
  },
};
</script>

<style lang="less">
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

.ani-area {
  /* width: 500px; */
  height: 140px;
  margin-top: 10px;
  position: relative;
  border: solid;
  border-color: aqua;
  overflow: hidden;
}



.ani {
  background: red;
  position: relative;
  animation-name: myfirst;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-delay: 2s;
  animation-iteration-count: infinite;
  animation-direction: normal;
  animation-play-state: running;
  position: absolute;
}

@keyframes myfirst {
  0% {
    background: red;
    left: 0px;
    top: 0%;
  }

  100% {
    background: red;
    left: 0px;
    top: 100%;
  }
}

.ani2 {
  background: red;
  position: relative;
  animation-name: myfirst2;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-delay: 2s;
  animation-iteration-count: infinite;
  animation-direction: normal;
  animation-play-state: running;
  position: absolute;
}

@keyframes myfirst2 {
  0% {
    background: red;
    left: 0px;
    top: -100%;
  }

  100% {
    background: red;
    left: 0px;
    top: 0%;
  }
}
</style>