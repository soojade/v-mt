<template>
  <div class="page-login">
    <div class="login-header">
      <a href="/" class="logo" />
    </div>
    <div class="login-panel">
      <div class="banner">
        <img
          src="//s0.meituan.net/bs/file/?f=fe-sso-fs:build/page/static/banner/www.jpg"
          width="480"
          height="370"
          alt="美团网"
        />
      </div>
      <div class="form">
        <h4 v-if="error" class="tips">
          <i />
          {{ error }}
        </h4>
        <p>
          <span>账号登录</span>
          <a
            class="code"
            href="/account/unitivelogin?service=www&amp;continue=http%3A%2F%2Fwww.meituan.com%2Faccount%2Fsettoken&amp;_nsmobilelogin=true"
          >手机动态码登录</a>
        </p>
        <div :class="['phone',{'focus':userFocus}]">
          <span class="country-area">
            <span class="plus">+</span>
            <span>86</span>
            <i class="right-arrow"></i>
          </span>
          <input
            type="text"
            class="phone-number"
            name="username"
            placeholder="手机号"
            maxlength="15"
            @focus="onFocus"
            @blur="onBlur"
          />
        </div>
        <div :class="['password',,{'focus':pwdFocus}]">
          <i class="el-icon-lock"></i>
          <input
            type="password"
            id="login-password"
            class="f-text pw-input"
            name="password"
            placeholder="密码"
            @focus="onFocus"
            @blur="onBlur"
          />
        </div>
        <div class="foot">
          <el-checkbox v-model="checked">7天内自动登录</el-checkbox>
          <a
            tabindex="-1"
            href="https://passport.meituan.com/useraccount/retrievepassword?risk_partner=0&amp;service=www&amp;continue=http%3A%2F%2Fwww.meituan.com%2Faccount%2Fsettoken"
            target="_top"
            class="forget-password"
          >忘记密码？</a>
        </div>
        <el-button class="btn-login" size="mini" @click="login">登录</el-button>
        <p class="signup-guide">
          还没有账号？
          <nuxt-link to="/register">免费注册</nuxt-link>
        </p>
      </div>
    </div>
    <div class="footer">
      <div class="site-info">
        <ul>
          <li class="first">
            <a rel="nofollow" href="https://about.meituan.com/about.html">关于美团</a>
          </li>
          <li>
            <a rel="nofollow" href="https://zhaopin.meituan.com/">加入我们</a>
          </li>
          <li>
            <a rel="nofollow" href="http://emis.meishi.meituan.com/merchantsSettled">商家入驻</a>
          </li>
          <li>
            <a rel="nofollow" href="https://www.meituan.com/help/faq">帮助中心</a>
          </li>
          <li class="last">
            <a href="http://meituan.com/mobile">美团手机版</a>
          </li>
        </ul>
      </div>
      <div class="copyright">
        <p>
          ©
          <span>2020</span>
          <a href="https://www.meituan.com">美团网团购</a>
          meituan.com
          <a href="http://www.miibeian.gov.cn/" target="_blank">京ICP证070791号</a>
          京公网安备11010502025545号
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import CryptoJS from 'crypto-js'
export default {
  data: () => {
    return {
      userFocus: false,
      pwdFocus: false,
      checked: '',
      username: '',
      password: '',
      error: ''
    }
  },
  layout: 'blank',
  methods: {
    login() {
      const self = this
      self.$axios
        .post('/users/signin', {
          username: window.encodeURIComponent(self.username),
          password: CryptoJS.MD5(self.password).toString()
        })
        .then(({ status, data }) => {
          if (status === 200) {
            if (data && data.code === 0) {
              location.href = '/'
            } else {
              self.error = data.msg
            }
          } else {
            self.error = `服务器出错`
          }
        })
    },
    onFocus(e) {
      e.target.name === 'username'
        ? (this.userFocus = true)
        : (this.pwdFocus = true)
    },
    onBlur() {
      this.userFocus = false
      this.pwdFocus = false
    }
  }
}
</script>

<style lang="scss" scoped>
.page-login {
  .login-header {
    position: relative;
    width: 980px;
    height: auto;
    margin: 40px auto 30px;
    .logo {
      background-image: url(//s0.meituan.net/bs/file/?f=fe-sso-fs:build/assets/sp-retina.b95a7dd.png);
      background-position: 0 !important;
      background-size: contain !important;
      width: 82px;
      height: 54px;
      display: block;
    }
  }
  .login-panel {
    margin: 0 auto 70px;
    width: 980px;
    display: flex;
    .banner {
      margin-right: 115px;
    }
    .form {
      display: flex;
      flex-direction: column;
      width: 270px;

      .tips {
        margin-bottom: 10px;
        padding: 10px;
        border: 1px solid #f5d8a7;
        border-radius: 2px;
        background: #fff6db;
        font-size: 12px;
        padding-left: 26px;
        > i {
          position: relative;
          &:after {
            position: absolute;
            display: inline-block;
            width: 17px;
            height: 17px;
            font-family: iconfont;
            font-style: normal;
            content: '\e64d';
            font-size: 28px;
            top: -9px;
            left: -24px;
          }
        }
      }
      em {
        font-style: normal;
        float: right;
      }
    }
    .focus {
      border-color: #fe8c00 !important;
    }
    .code {
      float: right;
      color: #666;
      &::after {
        display: inline-block;
        position: relative;
        top: 2px;
        content: '';
        width: 14px;
        height: 14px;
        margin-left: 3px;
        background: url(https://s0.meituan.net/bs/file/?f=fe-sso-fs:build/assets/mobile.24bd95a.png);
        background-size: contain;
      }
    }
    .phone,
    .password {
      box-sizing: border-box;
      width: 100%;
      margin: 8px 0;
      padding: 2px;
      border: 1px solid #aaa;
      background-color: #fff;
      overflow: hidden;
      display: flex;
      align-items: center;
    }
    .country-area {
      color: #646464;
      display: inline-block;
      .plus {
        font-weight: 700;
        color: #646464;
      }
      .right-arrow {
        position: relative;
        display: inline-block;
        margin-right: 4px;
        bottom: 2px;
        width: 5px;
        height: 5px;
        border-right: 1px solid #646464;
        border-top: 1px solid #646464;
        transform: rotate(45deg);
      }
    }
    input {
      height: 24px;
      padding: 5px;
      outline: none;
      border: none;
      &:-webkit-autofill {
        // 去除浏览器自动填充表单后的默认背景色
        box-shadow: 0 0 0 1000px white inset;
      }
    }
    .phone-number {
      width: 180px;
      padding-left: 5px;
      max-width: 200px;
    }
    .el-icon-lock {
      color: rgb(192, 185, 185);
      font-size: 20px;
    }
    .foot {
      margin-top: 10px;
      a {
        float: right;
        color: #fe8c00;
      }
    }

    .btn-login {
      margin-top: 10px;
      border: none;
      padding: 12px 15px;
      background-image: linear-gradient(135deg, #ffd000 0, #ffbd00 100%);
      box-shadow: 0 2px 1px rgba(191, 105, 0, 0.15);
      color: #222;
      font-size: 14px;
      font-weight: 700;
    }

    .signup-guide {
      font-size: 14px;
      color: #666;
      a {
        font-size: 14px;
        color: #fe8c00;
      }
    }
  }

  .footer {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin: 0 auto;
    width: 980px;
    height: 88px;

    .site-info,
    .copyright {
      border-top: 1px solid #eee;
    }
    ul {
      display: flex;
      margin: 5px 0;
      width: 600px;
      color: #eee;
      padding: 12px 0;
    }
    .site-info li {
      padding: 0 16px;
      line-height: 14px;
      border-right: 1px solid #eee;
      &:last-child {
        border: none;
      }
    }
    .copyright {
      padding: 20px 0;
      font-size: 12px;
      color: #999;
    }
  }
}
</style>
