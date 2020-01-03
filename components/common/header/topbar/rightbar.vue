<template>
  <ul class="afont navbar">
    <li>
      <nuxt-link to="/me">我的美团</nuxt-link>
      <dl>
        <dd>
          <nuxt-link to="/order">我的订单</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/order">我的收藏</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/order">抵用券</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/order">账户设置</nuxt-link>
        </dd>
      </dl>
    </li>
    <li class="kid">
      <nuxt-link to="/app">手机APP</nuxt-link>
    </li>
    <li>
      商家中心
      <dl>
        <dd>
          <nuxt-link to="/userCenter">美团餐饮商户中心</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/userCenter">登录商家中心</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/userCenter">美团智能收银</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/coop">我想合作</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/wap">免费手机开店</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/userCenter">餐饮代理商招募</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/kaipiao">商家申请开票</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/userCenter">免费合作美团排队</nuxt-link>
        </dd>
      </dl>
    </li>
    <li>
      美团规则
      <dl>
        <dd>
          <nuxt-link to="/userCenter">规则中心</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/coop">规则目录</nuxt-link>
        </dd>
        <dd>
          <nuxt-link to="/wap">规则评议院</nuxt-link>
        </dd>
      </dl>
    </li>
    <li class="site">
      网站导航
      <sitenav />
    </li>
  </ul>
</template>

<script>
import sitenav from './sitenav'
export default {
  components: {
    sitenav
  }
}
</script>

<style lang='scss'>
.navbar li {
  position: relative;
  float: left;
  padding: 0 15px;

  &:not(.site) dl {
    display: none;
    position: absolute;
    left: 0px;
    width: 78px;
    padding-top: 5px;
    dd {
      line-height: 33px;
      padding-left: 14px;
    }
  }
  &:not(.kid):hover,
  &:not(.site):hover dl {
    display: block;
    color: #fe8c00;
    background-color: #fff;
    box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
    z-index: 999;
  }

  &:nth-child(3) dl {
    width: 120px;
  }
}

.site:hover .nav-site {
  display: block;
  box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
}
</style>
