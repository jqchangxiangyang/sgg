<template>
  <div class="hello">
    <h2 @click="showName">学生姓名：{{ name }}</h2>
    <h2>性别{{ sex }}</h2>
  </div>
</template>
<script>
import { mixin } from "../mixin";

export default {
  name: "VoteB",
  data() {
    console.log(this);
    return {
      name: "gnmb",
      sex: "男",
    };
  },
  mixins: [mixin],
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
