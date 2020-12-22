<template>
  <div>
    <h2>我是首页</h2>
    <p>我是首页内容，哈哈哈</p>
    <router-link to="/home/news">新闻</router-link>
    <router-link to="/home/message">消息</router-link>
    <router-view></router-view>
    <h2>{{message}}</h2>
  </div>
</template>

<script>
  export default {
    name: "Home",
    data() {
      return {
        message:'你好啊',
        path:'/home/news'
      }
    },
    // 这两个函数，只有该组件被保持了状态使用了keep-alive时，才是有效的。
    activated() {
      console.log('activated');
      this.$router.push(this.path)
    },
    deactivated() {
      // console.log(this.$route.path);
      console.log('deactivated');
      // this.path = this.$route.path;
    },
    created() {
      console.log('home created');
      document.title="首页"
    },
    destroyed() {
      console.log('home destroyed');
    },
    // 组件内导航守卫，页面跳转时记住之前页面地址。
    beforeRouteLeave (to, from, next){
      console.log(this.$route.path);
      this.path = this.$route.path;
      next();
    },
    // beforeRouteUpdate: (to, from, next) => {
    //   console.log('beforeRouteUpdate');
    // }
    /* mounted() {
       console.log('mounted');
     },
     updated() {
       console.log('updated');
     }*/
  }
</script>

<style scoped>

</style>
