<template>
  <div class="school">
    <h2>学校名称:{{ name }}</h2>
    <h2>学校地址:{{ address }}</h2>
  </div>
</template>
<script>
export default {
  name: "School",
  data() {
    return {
      name: "牛马atguigu",
      address: "北京",
    };
  },
  mounted() {
    this.$bus.$on("hello", (data) => {
      console.log("我是School组件,收到了数据", data);
    });
  },
};
</script>
<style scoped>
.school {
  background-color: skyblue;
  padding: 5px;
}
</style>
