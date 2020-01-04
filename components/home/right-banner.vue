<template>
  <div class="right-banner">
    <el-carousel height="240px">
      <el-carousel-item v-for="item in urls" :key="item.id">
        <nuxt-link :to="'/'+item.name">
          <img :src="item.url" alt="item.alt" />
        </nuxt-link>
      </el-carousel-item>
    </el-carousel>
    <div class="relaxation">
      <nuxt-link to="/relaxation">
        <img
          src="http://p0.meituan.net/codeman/e473bb428f070321269b23370ff02ba956209.jpg"
          alt="休闲娱乐"
        />
      </nuxt-link>
    </div>
    <div class="login-card">
      <img class="avatar" src="//s0.meituan.net/bs/fe-web-meituan/e350c4a/img/avatar.jpg" alt="头像" />
      <p class="user-name">Hi！你好</p>
      <nuxt-link class="btn-login" to="/register">注册</nuxt-link>
      <nuxt-link class="btn-login" to="/login">立即登录</nuxt-link>
    </div>
    <div class="inn">
      <nuxt-link to="/hotel">
        <img
          src="http://p1.meituan.net/codeman/8cce56c467a17e04f3094d1e455462a0132772.png"
          alt="酒店"
        />
      </nuxt-link>
    </div>
    <div class="learning">
      <nuxt-link to="/learning">
        <img
          src="http://p1.meituan.net/codeman/16442c19da1f1c4544f794e29d99c92051716.jpg"
          alt="教育培训"
        />
      </nuxt-link>
    </div>
    <div class="business">
      <nuxt-link to="/business">
        <img
          src="http://p1.meituan.net/codeman/5b21cddb4bb1cbc3a9c3bce0f726c75940469.jpg"
          alt="商业合作"
        />
      </nuxt-link>
    </div>
    <div class="download-app">
      <img src="//s1.meituan.net/bs/fe-web-meituan/60ac9a0/img/download-qr.png" alt="下载APP" />
      <p class="app-name">美团APP手机版</p>
      <p class="sl">
        <span class="red">1元起</span>
        <span class="gary">吃喝玩乐</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      urls: [
        {
          id: 1,
          name: 'hotel',
          alt: '酒店',
          url:
            'http://p0.meituan.net/codeman/daa73310c9e57454dc97f0146640fd9f69772.jpg'
        },
        {
          id: 2,
          name: 'food',
          alt: '美食',
          url:
            'http://p1.meituan.net/codeman/826a5ed09dab49af658c34624d75491861404.jpg'
        },
        {
          id: 3,
          name: 'takeout',
          alt: '外卖',
          url:
            'http://p0.meituan.net/codeman/33ff80dc00f832d697f3e20fc030799560495.jpg'
        },
        {
          id: 4,
          name: 'movie',
          alt: '电影',
          url:
            'http://p0.meituan.net/codeman/33ff80dc00f832d697f3e20fc030799560495.jpg'
        },
        {
          id: 5,
          name: 'queue',
          alt: '排队',
          url:
            'https://p1.meituan.net/travelcube/01d2ab1efac6e2b7adcfcdf57b8cb5481085686.png'
        }
      ]
    }
  }
}
</script>
<style lang="scss" scoped>
.right-banner {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: space-between;
  width: 950px;
  height: 425px;

  /* 跑马灯 */
  .el-carousel img {
    width: 550px;
    height: 240px;
  }

  .relaxation,
  .relaxation img {
    width: 150px;
    height: 240px;
  }
  /*最右侧一列 */
  .login-card,
  .download-app {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    width: 228px;
    padding: 20px 0;
    box-sizing: border-box;
    border: 1px solid #e5e5e5;
    background-color: #fff;
    .app-name,
    .user-name {
      font-weight: 500;
      font-size: 16px;
      color: #222;
    }
  }
  .login-card {
    height: 238px;
    .avatar {
      width: 47px;
      height: 47px;
      border-radius: 50%;
      border: 4px solid #e5e5e5;
    }

    a {
      width: 118px;
      margin: 5px 0;
      line-height: 38px;
      text-align: center;
      background: #fff;
      border: 1px solid #e5e5e5;
      border-radius: 40px;
      font-size: 14px;
      color: #333;
      transition: background-color 0.5s;
      display: block;

      &:hover {
        background-color: #f6f6f6;
      }
    }
  }

  .inn,
  .learning,
  .inn img,
  .learning img {
    width: 270px;
    height: 165px;
  }

  .business,
  .business img {
    width: 150px;
    height: 165px;
  }

  .download-app {
    height: 165px;
    img {
      width: 95px;
      height: 95px;
    }
    .sl {
      margin-top: -5px;
      font-size: 12px;
    }
    .red {
      color: #ec5330;
      margin-right: 5px;
    }
    .grey {
      color: #3f3f3f;
    }
  }
  /* 添加图片悬浮高亮效果*/
  img:hover {
    // filter: opacity(85%);
    opacity: 0.85;
  }
}
.el-carousel {
  width: 550px;
  height: 240px;
}
.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>
