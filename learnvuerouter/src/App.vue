<template>
  <div id="app">
    <h2>我是APP组件</h2>
<!--    <router-link to="/home" tag="button" replace active-class="active">首页</router-link>-->
<!--    <router-link to="/about" tag="button" replace active-class="active">关于</router-link>-->
    <!--<router-link to="/home" tag="button" replace active-class="active">首页</router-link>
    <router-link to="/about" tag="button" replace active-class="active">关于</router-link>-->
<!--    <button @click="homeClick">首页</button>-->
<!--    <button @click="aboutClick">关于</button>-->
    <router-link to="/home">首页</router-link>
    <router-link to="/about">关于</router-link>

<!--    <router-link :to="'/user/'+userId">用户</router-link>-->
<!--    <router-link to="/Profile">档案</router-link>-->
<!--    <router-link :to="{path: '/profile',query: {name: 'why',age: '18',height: '180cm'}}">档案</router-link>-->
    <button @click="userClick">用户</button>
    <button @click="profileClick">档案</button>

    <keep-alive>
<!--      <router-view></router-view>-->
      <router-view/>
    </keep-alive>

<!--    <HomeNews></HomeNews>-->
<!--    <home-news></home-news>-->
  </div>
</template>

<script>
import HomeNews from "./components/HomeNews";
export default {
  name: 'App',
  components: {HomeNews},
  data() {
    return {
      userId: 'zhangsan'
    }
  },
  methods: {
    homeClick() {
      // 通过代码的方式修改路由 vue-router
      // push => pushState
      // this.$router.push('/home');
      this.$router.replace('/home')
      console.log('homeClick');
    },
    aboutClick() {
      // this.$router.push('/about');
      this.$router.replace('/about')
      console.log('aboutClick');
    },
    userClick() {
      this.$router.push('/user/'+this.userId)
    },
    profileClick() {
      this.$router.push({
        path: '/profile',
        query: {
          name: 'kobe',
          age: 18,
          height: 1.87
        }
      })
    }
  }
}
</script>

<style>
  /*.router-link-active{
    color: #ff0000;
  }*/
  .active{
    color: #f00;
  }
</style>
