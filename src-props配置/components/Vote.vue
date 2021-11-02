<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>学生姓名：{{ name }}</h2>
    <h2>性别{{ sex }}</h2>
    <h2>年龄{{ myAge }}</h2>
    <button @click="Add">修改年龄</button>
    <header />
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  data() {
    console.log(this);
    return {
      msg: "我是标题msg",
      myAge: this.age,
    };
  },
  methods: {
    Add() {
      this.myAge++;
    },
  },
  // props: ["name", "sex", "age"],
  props: {
    name: {
      type: String,
      required: true, //name是必要的
    },
    age: {
      type: Number,
      default: 99, //默认值
    },
    sex: {
      type: String,
      required: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
