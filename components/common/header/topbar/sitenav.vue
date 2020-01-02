<template>
  <div class="nav-site">
    <dl class="hotel">
      <dt>酒店旅游</dt>
      <dd>
        <nuxt-link to="/hotel">国际机票</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">榛果民宿</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">火车票</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">经济型酒店</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">主题酒店</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">商务酒店</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">公寓</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">豪华酒店</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">客栈</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">青年旅社</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">度假酒店</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">别墅</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/hotel">农家院</nuxt-link>
      </dd>
    </dl>
    <dl class="food">
      <dt>吃美食</dt>
      <dd>
        <nuxt-link to="/fish">烤鱼</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/fish">特色小吃</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/fish">烧烤</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/fish">自助餐</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/fish">火锅</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/fish">代金券</nuxt-link>
      </dd>
    </dl>
    <dl class="movie">
      <dt>看电影</dt>
      <dd>
        <nuxt-link to="/movie">热映电影</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/movie">热门影院</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/movie">热映电影口碑榜</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/movie">最受期待电影</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/movie">国内票房榜</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/movie">北美票房榜</nuxt-link>
      </dd>
      <dd>
        <nuxt-link to="/movie">电影排行榜</nuxt-link>
      </dd>
    </dl>
    <dl class="app">
      <dt>手机应用</dt>
      <dd>
        <a href="https://i.meituan.com/mobile/down/meituan" target="_blank">
          <img
            class="appicon"
            src="//s0.meituan.net/bs/fe-web-meituan/2d53095/img/appicons/meituan.png"
            title="美团app"
            alt="美团app"
          />
        </a>
      </dd>
      <dd>
        <a href="https://waimai.meituan.com/mobile/download/default" target="_blank">
          <img
            class="appicon"
            src="//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/waimai.png"
            title="外卖app"
            alt="外卖app"
          />
        </a>
      </dd>
      <dd>
        <a href="https://phoenix.meituan.com/app/" target="_blank">
          <img
            class="appicon"
            src="//s0.meituan.net/bs/fe-web-meituan/404d350/img/appicons/zhenguo.png"
            title="榛果app"
            alt="榛果app"
          />
        </a>
      </dd>
      <dd>
        <a href="https://www.dianping.com/events/m/index.htm" target="_blank">
          <img
            class="appicon"
            src="//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/dianping.png"
            title="点评app"
            alt="点评app"
          />
        </a>
      </dd>
      <dd>
        <a href="https://maoyan.com/app" target="_blank">
          <img
            class="appicon"
            src="//s1.meituan.net/bs/fe-web-meituan/404d350/img/appicons/maoyan.png"
            title="猫眼app"
            alt="猫眼app"
          />
        </a>
      </dd>
    </dl>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.nav-site {
  display: none;
  box-sizing: border-box;
  position: absolute;
  width: 1188px;
  left: -1110px;
  padding: 30px 36px 36px 47px;
  background-color: #fff;
}
.hotel,
.food,
.movie,
.app {
  float: left;
  margin-right: 47px;
  dd {
    line-height: 30px;
  }
}
.hotel {
  width: 235px;
  dd {
    float: left;
    width: 33%;
    text-align: center;
  }
}
.food {
  width: 156px;
  dd {
    float: left;
    width: 50%;
    text-align: center;
  }
}
.movie {
  width: 95px;
  text-align: center;
}
.app {
  float: right;
  dd {
    float: left;
    margin: 0 8px;
  }
  img {
    width: 60px;
    height: 60px;
  }
}
dt {
  margin-bottom: 26px;
  text-align: center;
  font-size: 14px;
  color: #222222;
  font-weight: 500;
  color: #222;
}
</style>
