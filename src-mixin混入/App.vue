<template>
  <div id="app">
    <h2>根组件</h2>

    <vote />
    <hr />
    <vote-b />
  </div>
</template>

<script>
import Vote from "./components/Vote.vue";
import VoteB from "./components/VoteB.vue";
export default {
  name: "App",
  components: {
    Vote,
    VoteB,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 16px;
}
</style>
