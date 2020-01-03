<template>
  <div class="menu">
    <h3>全部分类</h3>
    <ul>
      <li></li>
    </ul>
    <div class="menu-detail"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kind: '',
      menu: [
        {
          type: 'food',
          name: '美食',
          child: [
            {
              title: '美食',
              child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']
            }
          ]
        },
        {
          type: 'takeout',
          name: '外卖',
          child: [
            {
              title: '外卖',
              child: ['美团外卖']
            }
          ]
        },
        {
          type: 'hotel',
          name: '酒店',
          child: [
            {
              title: '酒店星级',
              child: ['经济型', '舒适/三星', '高档/四星', '豪华/五星']
            }
          ]
        }
      ]
    }
  },
  computed: {},
  methods: {}
}
</script>

<style lang="scss" scoped>
.menu {
  position: relative;
  width: 230px;
  height: 475px;
  margin-top: -50px;
  color: #646464;
  background: #fff;
  box-sizing: border-box;
  border: 1px solid #e5e5e5;

  h3 {
    text-align: center;
    padding-top: 10px;
  }

  /* 详情菜单 */
  .menu-detail {
    position: absolute;
    left: 230px;
    top: 58px;
    width: 400px;
    height: 416px;
    background-color: #fff;
    color: #666;
    overflow: hidden;
    z-index: 999;
  }
}
</style>
