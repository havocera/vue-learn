<template>
<!-- 模版部分，html部分，主节点只有一个，里面无所谓 -->
  <!-- <div id="app"> -->
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- {{test}} -->
<!-- <button @click="test1">变了吗？</button> -->
    <!-- 导入helloworld组件1111 -->
    <!-- <HelloWorld msg="helloword" :fater="test"/> -->
  <!-- </div> -->
  <router-view />
</template>

<script>
//js，javascript 代码部分
//improt 导入子组件
// import HelloWorld from './components/HelloWorld.vue'

export default {
  //组件名称
  name: 'App',
  //导入该组件的子组件
components: {
    // HelloWorld
  },
  //所有的公共变量
  data(){
    return{
      test:123

    }
  },
  mounted(){
    this.test=345

  },
  created(){
    this.test=567

  },
  methods:{

  test1(){
    this.test=789
    console.log(this.test)
  },
  test2(){
    
  }

  },
}
</script>

<style lang="less">
/* css样式 */
html,body,#app{
  height: 100%;
  margin: 0;
  padding: 0;
  // background:rgba(38, 24, 49,.6);
}
</style>
