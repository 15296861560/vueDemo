<template>
  <div>
    <footer>Copyright © {{year}}· LGY社区 · 服务器赞助: {{server}} · 网站程序: {{website}}</footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      year: 2020,
      server: "未发布",
      website: "Vue"
    };
  },
  methods: {}
};
</script>

<style scoped>
</style>
