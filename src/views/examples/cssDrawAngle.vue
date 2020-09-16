<template>
  <div>
    <div class="box fillet">
      <div class="traA-tip" v-if="sta">
        小三角叠在大三角上
        <br />大三角的底边将会被显示出来
      </div>
      <div @mouseover="sta=true" @mouseleave="sta=false">
        <span class="traA"></span>
        <span class="traB"></span>
      </div>
      <div class="line-tip" v-if="slb">
        <div class="el-icon-caret-left line-tip-tra"></div>先画一个大三角
        <br />然后利用伪元素再画一个小三角
        <br />叠加后显示底边
      </div>
      <span class="line45-b" @mouseover="slb=true" @mouseleave="slb=false">
        <span></span>
      </span>
      <div class="traC-tip" v-if="stc">
        四条边设置不同颜色和相同宽度
        <br />不需要哪个三角形则将其颜色设为透明
      </div>
      <span class="traC" @mouseover="stc=true" @mouseleave="stc=false"></span>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      sta: false,
      stc: false,
      slb: false,
    };
  },
  methods: {
    showTraA() {
      this.sta = true;
    },
  },
};
</script>
<style>
.box {
  width: 500px;
  height: 200px;
  border: solid;
  border-width: 10px;
  border-color: aqua;
  position: relative;
}

.traA {
  border-color: red #17141400;
  border-style: solid;
  position: absolute;
  width: 0px;
  height: 0px;
  border-width: 20px 20px 0px 0px;
  top: 0px;
  left: 0px;
}

.traB {
  border-color: black #17141400;
  border-style: solid;
  position: absolute;
  width: 0px;
  height: 0px;
  border-width: 15px 15px 0px 0px;
  top: 0px;
  left: 0px;
}

.line45-b {
  border-color: red #17141400;
  border-style: solid;
  position: absolute;
  border-width: 20px 0px 0px 20px;
  top: 0px;
  right: 0px;
}

.line45-b :before {
  content: "";
  position: absolute;
  top: -20px;
  right: 0px;
  border-color: #1a1919 #17141400;
  border-style: solid;
  border-width: 15px 0px 0px 15px;
}

.traC {
  border-color: red blue yellow green;
  border-style: solid;
  position: absolute;
  width: 0px;
  height: 0px;
  border-width: 20px 20px 20px 20px;
  bottom: 0px;
  left: 0px;
}

.fillet {
  border-radius: 0px 0px 30px 0px;
}

.traA-tip {
  position: absolute;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
  border: 1px solid #ebeef5;
  border-radius: 5px;
  background: white;
  padding: 10px;
  left: -250px;
  top: -20px;
}
.traA-tip:after {
  content: "";
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent transparent transparent lightgray;
  border-style: solid;
  border-width: 10px;
  right: -20px;
  top: 20px;
}

.line-tip {
  position: absolute;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
  border: 1px solid #ebeef5;
  border-radius: 5px;
  background: white;
  padding: 10px;
  right: -280px;
  top: -40px;
}
.line-tip-tra {
  position: absolute;
  left: -14px;
  top: 32px;
  color: #949bab;
  transform: scale(2);
}

.traC-tip {
  position: absolute;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
  border: 1px solid #ebeef5;
  border-radius: 5px;
  background: white;
  padding: 10px;
  left: -315px;
  bottom: -12px;
}
.traC-tip:after {
  content: "";
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent transparent transparent lightgray;
  border-style: solid;
  border-width: 10px;
  right: -20px;
  top: 20px;
}
</style>