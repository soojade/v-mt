<template>
  <div class="menu">
    <h3>全部分类</h3>
    <ul @mouseleave="onLeave">
      <!-- 防止重复的key报错 -->
      <li v-for="item in menu" :key="item.type+''+Math.random().toFixed(5)" @mouseenter="onEnter">
        <i :class="item.type"></i>
        <nuxt-link :to="'/'+item.type">
          <span class="menu-item">{{ item.name }}</span>
          <span v-if="item.hot" class="hot">HOT</span>
        </nuxt-link>
        <span class="arrow"></span>
      </li>
    </ul>
    <div class="menu-detail" v-if="kind" @mouseenter="onSubEnter" @mouseleave="onLeave">
      <template v-for="item in detail">
        <dl class="clearfix" :key="item.title+''+Math.random().toFixed(5)">
          <dt>
            <nuxt-link :to="'/'+kind">{{ item.title }}</nuxt-link>
            <span class="more">
              <nuxt-link :to="'/'+kind">更多</nuxt-link>
            </span>
          </dt>
          <dd v-for="nav in item.child" :key="nav+''+Math.random().toFixed(5)">
            <nuxt-link :to="'/'+kind">{{ nav }}</nuxt-link>
          </dd>
        </dl>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kind: '',
      menu: [
        {
          type: 'meishi',
          name: '美食',
          child: [
            {
              title: '美食',
              child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']
            }
          ]
        },
        {
          type: 'waimai',
          name: '外卖',
          child: [
            {
              title: '外卖',
              child: ['美团外卖']
            }
          ]
        },
        {
          type: 'jiudian',
          name: '酒店',
          hot: true,
          child: [
            {
              title: '酒店星级',
              child: ['经济型', '舒适/三星', '高档/四星', '豪华/五星']
            }
          ]
        },
        {
          type: 'inn',
          name: '榛果民宿',
          child: [
            {
              title: '热门城市',
              child: ['上海', '成都', '北京', '重庆']
            },
            {
              title: '热门房源',
              child: ['复式Loft', '别墅']
            }
          ]
        },
        {
          type: 'cat',
          name: '猫眼电影',
          child: [
            {
              title: '热映电影',
              child: ['宠爱', '误杀', '美人生', '叶问4']
            },
            {
              title: '热门影院',
              child: ['新世纪影城', '万达影城']
            }
          ]
        },
        {
          type: 'ticket',
          name: '机票 / 火车票',
          child: [
            {
              title: '机票',
              child: ['国内机票', '国际/港澳台机票']
            },
            {
              title: '火车票',
              child: ['火车票']
            }
          ]
        },
        {
          type: 'entertainment',
          name: '休闲娱乐 / KTV',
          child: [
            {
              title: '休闲娱乐',
              child: [
                '足疗按摩',
                '洗浴/汗蒸',
                '游乐游艺',
                'VR',
                '桌面游戏',
                '真人CS',
                '棋牌室',
                '其他玩乐'
              ]
            },
            {
              title: 'KTV',
              child: ['KTV']
            }
          ]
        },
        {
          type: 'beauty',
          name: '丽人 / 美发/医学美容',
          child: [
            {
              title: '丽人',
              child: [
                '美发',
                '美甲',
                '美睫',
                '美容',
                '美体',
                '医学美容',
                '瑜伽舞蹈'
              ]
            }
          ]
        },
        {
          type: 'ticket',
          name: '机票 / 火车票',
          child: [
            {
              title: '机票',
              child: ['国内机票', '国际/港澳台机票']
            },
            {
              title: '火车票',
              child: ['火车票']
            }
          ]
        },
        {
          type: 'cat',
          name: '猫眼电影',
          child: [
            {
              title: '热映电影',
              child: ['宠爱', '误杀', '美人生', '叶问4']
            },
            {
              title: '热门影院',
              child: ['新世纪影城', '万达影城']
            }
          ]
        },
        {
          type: 'meishi',
          name: '美食',
          child: [
            {
              title: '美食',
              child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']
            }
          ]
        },
        {
          type: 'inn',
          name: '榛果民宿',
          child: [
            {
              title: '热门城市',
              child: ['上海', '成都', '北京', '重庆']
            },
            {
              title: '热门房源',
              child: ['复式Loft', '别墅']
            }
          ]
        },
        {
          type: 'waimai',
          name: '外卖',
          child: [
            {
              title: '外卖',
              child: ['美团外卖']
            }
          ]
        },
        {
          type: 'jiudian',
          name: '酒店',
          hot: true,
          child: [
            {
              title: '酒店星级',
              child: ['经济型', '舒适/三星', '高档/四星', '豪华/五星']
            }
          ]
        },
        {
          type: 'ticket',
          name: '机票 / 火车票',
          child: [
            {
              title: '机票',
              child: ['国内机票', '国际/港澳台机票']
            },
            {
              title: '火车票',
              child: ['火车票']
            }
          ]
        },
        {
          type: 'pub',
          name: '酒吧 / 密室逃脱',
          child: [
            {
              title: '酒吧',
              child: ['酒吧', '网吧', '网咖', '私人影院']
            },
            {
              title: '密室逃脱',
              child: ['密室逃脱', '游乐游艺']
            }
          ]
        }
      ]
    }
  },
  computed: {
    detail() {
      return this.menu.filter(item => item.type === this.kind)[0].child
    }
  },
  methods: {
    onEnter(e) {
      this.kind = e.target.querySelector('i').className
    },
    onLeave() {
      this.timer = setTimeout(() => {
        this.kind = ''
      }, 200)
    },
    onSubEnter() {
      clearInterval(this.timer)
    }
  }
}
</script>

<style lang="scss" scoped>
.menu {
  position: relative;
  width: 230px;
  height: 480px;
  margin-top: -50px;
  color: #646464;
  background: #fff;
  box-sizing: border-box;
  border: 1px solid #e5e5e5;

  li {
    padding: 3px;
    cursor: pointer;
  }
  h3 {
    text-align: center;
    padding: 20px 0;
  }
  .menu-item {
    font-size: 13px;
    color: #646464;
    &:hover {
      color: #222;
      font-weight: 700;
    }
  }
  .hot {
    padding: 2px 5px;
    border-radius: 12px;
    background-color: #fdfdc3;
    color: #222;
    &:hover {
      font-weight: 400;
      background: linear-gradient(to bottom right, #ffd000, #ffbd00);
    }
  }
  .arrow {
    float: right;
    display: block;
    width: 4px;
    height: 4px;
    margin: 10px;
    color: #bfbfbf;
    border-bottom: 1px solid #bfbfbf;
    border-right: 1px solid #bfbfbf;
    transform: rotate(-45deg);
  }
  i {
    width: 16px;
    height: 16px;
    padding: 0 10px;
    font-style: normal;
    font-family: 'iconfontNew';
    font-size: 16px;
    &::before {
      display: inline-block;
      vertical-align: middle;
      line-height: 18px;
    }
  }
  .meishi::before {
    content: '\e60e';
    color: #ff8200;
  }
  .waimai::before {
    content: '\e60a';
    color: #ffb500;
  }
  .jiudian::before {
    content: '\e616';
    color: #9b5e3e;
  }
  .inn::before {
    content: '\e60c';
    color: #ffb500;
  }
  .cat::before {
    content: '\e612';
    color: #ff3d00;
  }
  .ticket::before {
    content: '\e615';
    color: #03a9f4;
  }
  .entertainment::before {
    content: '\e607';
    color: #00bf96;
  }
  .beauty::before {
    content: '\e60f';
    color: #ff4081;
  }
  .pub::before {
    content: '\e606';
    color: #00bf96;
  }
  /* 详情菜单 */
  .menu-detail {
    position: absolute;
    box-sizing: border-box;
    left: 230px;
    top: 58px;
    width: 400px;
    height: 416px;
    padding: 30px;
    background-color: #fff;
    color: #666;
    overflow: hidden;
    z-index: 999;
    dl {
      margin-top: 20px;
    }
    dt {
      text-align: left;
      margin-bottom: 10px;
      padding-bottom: 15px;
      border-bottom: 1px solid #e8dddd;
      a {
        font-size: 16px;
        color: #222;
      }
      .more {
        float: right;
        a {
          font-size: 12px;
          color: #999;
        }
        &::after {
          content: '';
          display: inline-block;
          width: 4px;
          height: 4px;
          margin-left: 1px;
          color: #bfbfbf;
          vertical-align: middle;
          border-bottom: 1px solid #bfbfbf;
          border-right: 1px solid #bfbfbf;
          transform: rotate(-45deg);
        }
      }
    }
    dd {
      float: left;
      padding: 2px 5px;
      a {
        font-size: 12px;
        color: #999;
        &:hover {
          color: #fe8c00;
        }
      }
    }
  }
}
</style>
