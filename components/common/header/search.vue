<template>
  <div class="center">
    <div class="logo">
      <a href="#">
        <img src="@/static/img/logo.png" alt />
      </a>
    </div>
    <div class="search">
      <el-input
        placeholder="搜索商家或地点"
        v-model="msg"
        @focus="handleFocus"
        @blur="handleBlur"
        @input="handleInput"
        @keyup.enter.native="search"
        clearable
      ></el-input>
      <el-button class="sbtn" icon="el-icon-search" @click="search"></el-button>
      <div class="hotword" v-if="isFocus">
        <template v-if="isInput">
          <ul class="suggestion">
            <li v-for="item in suggestion" :key="item">
              <nuxt-link :to="'/s/'+item">{{ item }}</nuxt-link>
            </li>
          </ul>
        </template>
        <template v-else>
          <template v-if="isEmpty">
            <p>近期搜索</p>
            <span class="delete" @click="onDelete">删除搜索历史</span>
            <ul class="words clearfix">
              <li v-for="item in searchList" :key="item">
                <nuxt-link :to="'/s/'+item">{{ item }}</nuxt-link>
              </li>
            </ul>
          </template>
          <p>热门搜索</p>
        </template>
      </div>
    </div>
    <ul class="nav">
      <li>
        <nuxt-link to="/takeout">美团外卖</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/movie">猫眼电影</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/hotel">美团酒店</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/apartment">民宿/公寓</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/business">商家入驻</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/welfare">美团公益</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: '',
      searchList: ['电影', '蛋糕', '电视剧'],
      suggestion: ['电影', '蛋糕', '电视剧'],
      isFocus: false,
      isInput: false
    }
  },
  methods: {
    handleFocus() {
      this.isFocus = true
    },
    handleBlur() {
      setTimeout(() => {
        this.isFocus = false
        this.isInput = false
      }, 500) // 防止丢失焦点后 不能点击
    },
    handleInput() {
      this.isInput = true
    },
    search() {
      if (this.msg.trim !== '') {
        // element ui 不支持v-model.trim
        this.searchList.push(this.msg)
        this.searchList = [...new Set(this.searchList)]
        this.msg = ''
      }
    },
    onDelete() {
      this.searchList = []
    }
  },
  computed: {
    isEmpty() {
      return this.searchList.length !== 0
    }
  }
}
</script>

<style lang="scss">
.logo {
  display: inline-block;
  margin-top: 28px;
  img {
    width: 126px;
    height: 46px;
  }
}
.search {
  position: relative;
  width: 550px;
  height: 40px;
  margin: 0 auto;
  margin-top: -38px;
  div,
  input,
  .hotword {
    width: 470px;
  }
  .el-input__inner {
    border: 1px solid #e5e5e5;
    border-right: none;
    outline: none;
    border-radius: 4px 0 0 4px;
  }
  .hotword {
    position: absolute;
    box-sizing: border-box;
    border: 1px solid #e5e5e5;
    border-top: none;
    min-height: 80px;
    padding: 5px;
    background: #fff;
    box-shadow: 0 3px 5px 0 rgba(0, 0, 0, 0.1);
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    color: #999;
    z-index: 999;
    .suggestion li {
      padding-top: 3px;
      padding-left: 10px;
      color: #222;
      a {
        display: inline-block;
        width: 100%;
        line-height: 25px;
      }
      &:hover {
        background-color: #f8f8f8;
      }
    }
    .words {
      padding: 2px 5px;
      li {
        float: left;
        padding: 0 2px;
      }
    }
    p,
    .delete {
      margin-top: 8px;
      padding-left: 10px;
      font-size: 12px;
      font-weight: 700;
    }
    .delete {
      float: right;
      padding-right: 10px;
      margin-top: -18px;
      font-weight: 500;
      cursor: pointer;
    }
  }
}
.sbtn {
  float: right;
  width: 14.55%;
  background: #ffc300;
  padding: 9px 20px;
  font-size: 20px;
  &:hover {
    background: rgb(247, 176, 46);
  }
}
.nav {
  width: 640px;
  margin: 0 auto;
  margin-top: 46px;
  li {
    float: left;
    padding: 0 20px;
    a {
      font-size: 16px;
      font-weight: 700;
      color: #222;
      &:hover {
        color: #ffc300;
      }
    }
  }
}
</style>
