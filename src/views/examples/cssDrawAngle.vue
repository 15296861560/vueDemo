<template>
  <div>
    <div class="box fillet">
      <span class="traA"></span>
      <span class="traB"></span>
      <span class="line45-b">
        <span></span>
      </span>
      <span class="traC"></span>
    </div>
  </div>
</template>
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
</style>