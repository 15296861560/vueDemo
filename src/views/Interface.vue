<template>
  <div>
    <h1>{{data}}</h1>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return{
      data:null,
    }
  },
  methods: {
    getData() {
      axios
        .post("https://www.runoob.com/try/ajax/demo_axios_post.php")
        .then((response) => (this.data= response))
        .catch(function (error) {
          // 请求失败处理
          console.log(error);
        });
    },
  },
  mounted() {
      this.getData();
  },
};
</script>