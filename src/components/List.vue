<template>
  <div class="row">
    <div
      v-show="users.length"
      class="card"
      v-for="user in users"
      :key="user.login"
    >
      <a :href="user.html_url" target="_blank">
        <img :src="user.avatar_url" style="width: 100px" />
      </a>
      <p class="card-text">{{ user.login }}</p>
    </div>
    <h1>欢迎使用！</h1>
  </div>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      users: [],
      isLoading: false,
      errMsg: "",
      isFirst: true,
    };
  },
  mounted() {
    this.$bus.$on("getUsers", (users) => {
      console.log("我是List组件，收到数据", users);
      this.users = users;
    });
  },
};
</script>

<style></style>
