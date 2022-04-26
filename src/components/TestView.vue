<template>
  <div style="height:100%">
    <el-container>
      <el-header class="header">
        椒图后台管理系统 <i @click="isCollapse=!isCollapse" class="el-icon-s-grid"></i>
     <div class="right">
     <el-dropdown @command="handleCommand">
     <div ><i class="el-icon-s-custom"></i> admin <i class="el-icon-caret-bottom"></i></div>
      <el-dropdown-menu slot="dropdown">
    <el-dropdown-item command="loginout">退出登陆</el-dropdown-item>
   
  </el-dropdown-menu>
</el-dropdown>
</div>
      </el-header>
      <el-container>
        <el-aside style="width: auto !important;height:100%">
           
<el-menu style="height:100%" :default-active="this.$route.path" :router="true" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
  
  <el-menu-item index="/home">
    <i class="el-icon-menu"></i>
    <span slot="title">首页</span>
  </el-menu-item>
  <el-menu-item index="3" >
    <i class="el-icon-document"></i>
    <span slot="title">导航三</span>
  </el-menu-item>
  <el-menu-item index="4">
    <i class="el-icon-setting"></i>
    <span slot="title">导航四</span>
  </el-menu-item>
</el-menu>


        </el-aside>
        <el-main>
          <router-view/>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isCollapse:false
    };
  },
  mounted() {},
  methods: {
    handleCommand(command) {
        if(command=='loginout'){
          window.sessionStorage.clear();
          this.$message({
            message:'欢迎下次登陆，再见！',
            type:'success'
          })
          this.$router.push('/')
        }
      },
    handleOpen(e){
      console.log(e)
    },
    handleClose(e){
        console.log(e)
    }
  },
};
</script>

<style lang="less" scoped>
.header{
  // height: 50px;
  background-color: #409Eff;
  font-size: 28px;
  color: #fff;
  line-height: 60px;
}
.el-container{
  height: 100%;
}
.el-aside{
  height: 100%;
}
.right{
  float:right;
  display: inline-block;
  font-size: 26px;
  .el-dropdown{
    color: #fff;
    font-size: 24px;
  }
}
</style>