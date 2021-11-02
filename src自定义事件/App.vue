<template>
  <div class="app">
    <h1>{{ msg }} 学生名字是：{{ studentName }}</h1>
    <School :getSchoolName="getSchoolName" />
    <!-- <Student @atguigu="getStudentName" @demo="m1" /> -->
    <Student ref="student" @click.native="show" />
  </div>
</template>
<script>
import Student from "./components/Student";
import School from "./components/School";
export default {
  name: "App",
  components: { School, Student },
  data() {
    return {
      msg: "你好啊！",
      studentName: "",
    };
  },
  methods: {
    getSchoolName(name) {
      console.log("App收到了学校名：", name);
    },
    getStudentName(name, ...params) {
      console.log("App收到了学生名：", name, params);
      this.studentName = name;
    },
    show() {
      alert(123);
    },
    m1() {
      console.log("demo事件被触发了");
    },
  },
  mounted() {
    this.$refs.student.$on("atguigu", this.getStudentName); //绑定自定义事件l
    // this.$refs.student.$once("atguigu", this.getStudentName);只触发一次
  },
};
</script>
<style scoped>
.app {
  background-color: gray;
  padding: 5px;
}
</style>
