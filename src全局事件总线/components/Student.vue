<template>
  <div class="student">
    <h2>学校姓名：{{ name }}</h2>
    <h2>学校性别：{{ sex }}</h2>
    <button @click="sendStudentName">把学生组件给School组件</button>
  </div>
</template>
<script>
export default {
  name: "Student",
  data() {
    return {
      name: "张三",
      sex: "男",
    };
  },
  mounted() {},
  methods: {
    sendStudentName() {
      this.$bus.$emit("hello", this.name);
    },
  },
  beforeDestroy() {
    this.$bus.$off("hello");
  },
};
</script>
<style scoped>
.student {
  background-color: pink;
  padding: 5px;
  margin: 5px;
}
</style>
