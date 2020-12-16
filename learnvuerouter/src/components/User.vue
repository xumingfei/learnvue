<template>
  <div>
    <h2>我是用户界面</h2>
    <p>我是用户相关信息{{userId}}</p>
    <h2>{{userId}}</h2>
    <h2>{{$route.params.userId}}</h2>
    <button @click="btnClick">按钮</button>
<!--    <p>{{message}}</p>-->
  </div>
</template>

<script>
  export default {
    name: "User",
    /*data() {
      return {
        message: 'aaa'
      }
    },*/

    methods: {
      btnClick() {
        // 所有组件都继承Vue类的原型
        console.log(this.$router);
        console.log(this.$route);

        console.log(this.name);;
      }
    },
    computed:{
      userId(){
        return this.$route.params.userId
      },
      /*finalMessage(){
        return this.message
      }*/
    }
  }
</script>

<style scoped>

</style>
