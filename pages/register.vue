<template>
  <el-container>
    <el-header>
      <div class="wrapper">
        <nuxt-link to="/" class="site-logo">logo</nuxt-link>
        <div class="login-block">
          <span class="tip">已有美团账号？</span>
          <nuxt-link to="/login" class="btn-login">登录</nuxt-link>
        </div>
      </div>
    </el-header>
    <el-main>
      <el-form :model="ruleForm" status-icon :rules="rules" ref="ruleForm" label-width="100px">
        <el-form-item label="手机号" prop="phone">
          <el-input type="phone" v-model="ruleForm.phone" autocomplete="off"></el-input>
        </el-form-item>
        <input type="button" class="btn-mini" value="免费获取短信动态码" />
        <el-form-item label="短信动态码" prop="code">
          <el-input type="code" v-model="ruleForm.code" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item label="创建密码" prop="password" class="password">
          <el-input type="password" v-model="ruleForm.password" autocomplete="off" show-password></el-input>
        </el-form-item>
        <el-form-item label="确认密码" prop="checkPass">
          <el-input type="password" v-model="ruleForm.checkPass" autocomplete="off"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('ruleForm')">同意以下协议并注册</el-button>
        </el-form-item>
        <div class="term">
          <a
            class="f1"
            href="https://rules-center.meituan.com/rules-detail/4"
            target="_blank"
          >《美团点评用户服务协议》</a>
          <a
            class="f1"
            href="https://rules-center.meituan.com/rules-detail/2"
            target="_blank"
          >《美团点评隐私政策》</a>
        </div>
      </el-form>
    </el-main>
    <el-footer>
      <p class="copyright">
        ©
        <a class="f1" href="https://www.meituan.com">meituan.com</a>&nbsp;
        <a class="f1" target="_blank" href="http://www.miibeian.gov.cn/">京ICP证070791号</a>&nbsp;
        <span class="f1">京公网安备11010502025545号</span>
      </p>
    </el-footer>
  </el-container>
</template>
<script>
export default {
  layout: 'blank',

  data() {
    return {
      ruleForm: {
        phone: '',
        code: '',
        password: '',
        checkPass: ''
      },
      rules: {
        phone: [
          { required: true, message: '请输入手机号', trigger: 'blur' },
          { min: 11, max: 11, message: '请输入11位手机号', trigger: 'blur' }
        ],
        code: [
          { required: true, message: '请输入短信动态码', trigger: 'blur' },
          { min: 6, max: 6, message: '请输入6位数验证码', trigger: 'blur' }
        ],
        password: [
          { required: true, message: '请填写密码', trigger: 'blur' },
          { min: 8, max: 18, message: '密码太短，至少8个字符', trigger: 'blur' }
        ],
        checkPass: [
          { required: true, message: '请再次输入密码', trigger: 'blur' },
          {
            min: 8,
            max: 18,
            message: '两次输入的密码不一致，请重新输入',
            trigger: 'blur'
          }
        ]
      }
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          alert('恭喜!注册成功，请登录！')
        } else {
          return false
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.el-header {
  border-bottom: 2px solid #d8d8d8;
}
.wrapper {
  margin: 0 auto;
  padding: 10px 0;
  width: 980px;
  line-height: 28px;

  .site-logo {
    display: inline-block;
    width: 128px;
    height: 36px;
    text-indent: -1000px;
    overflow: hidden;
    background: url(https://s0.meituan.net/bs/file/?f=fe-sso-fs:build/assets/logo.6a89007.png)
      no-repeat;
    background-size: contain;
  }
  .login-block {
    float: right;
    .tip {
      margin-right: 10px;
      vertical-align: sub;
    }
    .btn-login {
      display: inline-block;
      line-height: 22px;
      padding: 2px 13px;
      background: #ffd000;
      text-align: center;
      color: #222;
      box-shadow: 0 2px 1px rgba(191, 105, 0, 0.15);
    }
  }
}
.el-form {
  margin: 30px auto;
  padding: 0 30px;
  width: 980px;
  min-height: 300px;

  .el-input {
    width: 260px;
    input {
      border: 1px solid #aaa;
      line-height: 24px;
      vertical-align: top;
    }
  }
  .btn-mini {
    margin: -3px 0 8px 100px;
    padding: 2px 8px 2px;
    font-size: 12px;
    color: #333;
    background-image: linear-gradient(to bottom, #f7f7f7, #dedede);
    border: 1px solid #e3e3e3;
    border-bottom: 1px solid #aaa;
    outline: none;
    cursor: pointer;

    /*注意顺序*/
    &:hover {
      color: #333;
      background-color: #e9e9e9;
      border: 1px solid #e5e5e5;
      border-bottom: 1px solid #b3b3b3;
      background-image: linear-gradient(to bottom, #fff, #e9e9e9);
    }
    &:active {
      color: #333;
      background-color: #efeffe;
      border: 1px solid #ddd;
      border-bottom: 1px solid #aaa;
      background-image: linear-gradient(to bottom, #ddd, #eee);
    }
  }

  .el-button {
    color: #222;
    background-image: linear-gradient(135deg, #ffd000 0, #ffbd00 100%);
    border-width: 0;
    box-shadow: 0 2px 1px rgba(191, 105, 0, 0.15);
    font-size: 14px;
    font-weight: 700;
  }
}
.term {
  position: relative;
  padding: 3px 10px 3px 110px;
  margin: 0 auto 8px;
  a {
    font-size: 13px;
    color: #fe8c00;
  }
}
.el-footer {
  border-top: 1px solid #eee;
  padding-top: 20px;
  text-align: center;
  color: #999;
}
</style>
