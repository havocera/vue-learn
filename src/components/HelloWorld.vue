<template>
  <transition name="el-zoom-in-top">
    <div class="hello">
      <el-row :gutter="20">
        <el-col :span="10">
          <div class="left main-title">
            椒图<br />
            后台管理系统
          </div>
        </el-col>
        <el-col :span="10" :offset="0">
          <div class="right">
            <el-card class="box-card">
              <p class="title">登陆</p>
              <el-form
                ref="form"
                :model="form"
                :rules="rules"
                label-width="80px"
              >
                <el-form-item label="用户名" prop="name">
                  <el-input v-model="form.name"></el-input>
                </el-form-item>
                <el-form-item label="密码" prop="pwd">
                  <el-input v-model="form.pwd"></el-input>
                </el-form-item>
              </el-form>
              <el-button type="primary" @click="tologin">登陆</el-button>
            </el-card>
          </div>
        </el-col>
      </el-row>
    </div>
  </transition>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
    fater: Number,
  },
  data() {
    return {
      isshow: false,
      lastname: "",
      form: {
        name: "",
        pwd: "",
      },
      rules: {
        name: [
          { required: true, message: "请输入用户名", trigger: "blur" },
          // { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        pwd: [
          { required: true, message: "请输入密码", trigger: "blur" },
          // { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
      },
    };
  },
  methods: {
    catinput() {
      this.lastname = "dddd";
      console.log(this.lastname);
    },
    totest() {
      this.$router.push({
        name: "test",
        params: { name: "wangzhen", age: 30 },
        query: { token: "ydhddjjddjdjdjj" },
      });
    },
    tologin() {
      this.$refs["form"].validate((valid) => {
        if (valid) {
          if (this.form.name == "admin" && this.form.pwd == "admin") {
            window.localStorage.setItem("token", "dddddddd");
            window.sessionStorage.setItem("token", "hdhhhdhdhdhdhd");
            this.$message({
              message: "欢迎你，登陆成功",
              type: "success",
            });
            this.$router.push("/test");
          } else {
            this.$message({
              message: "用户名或密码错误！",
              type: "error",
            });
          }
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- varchar String char -->
<style lang="less" scoped>
.hello {
  height: 100%;
  background-color: #409eff;
  margin: 0;
  padding: 0;
}
.left-f {
  background-color: aquamarine;
  width: 100%;
  height: 100%;
  position: absolute;
}
.main-title {
  font-size: 55px;
  color: #ffffff;
}
.left {
  text-align: center;
  height: 400px;
  margin-top: 35%;
}
.box-card {
  width: 400px;
  margin-top: 30%;
  text-align: center;
  font-size: 28px;
  .title {
    margin-bottom: 15px;
    color: #409eff;
  }
}
</style>
