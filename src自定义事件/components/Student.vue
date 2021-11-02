<template>
  <div class="student">
    <h2>学校姓名：{{ name }}</h2>
    <h2>学校性别：{{ sex }}</h2>
    <h2>当前求和为：{{ number }}</h2>
    <button @click="add">点我number++</button>
    <button @click="sendStudntName">把学生名给App</button>
    <button @click="unbind">解绑atguigu事件</button>
    <button @click="death">销毁当前Student组件的实例vc</button>
  </div>
</template>
<script>
export default {
  name: "Student",
  data() {
    return {
      name: "张三",
      sex: "男",
      number: 0,
    };
  },
  methods: {
    sendStudntName() {
      this.$emit("atguigu", this.name, 666, 88, 99);
      // this.$emit("demo");
      // this.$emit("click");
    },
    add() {
      console.log("add被调用了");
      this.number++;
    },
    unbind() {
      // this.$off("atguigu");
      // this.$off(["atguigu", "demo"]);
      // this.$off();
    },
    death() {
      this.$destroy();
    },
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
