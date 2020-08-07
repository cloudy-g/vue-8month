<template>
  <div id="app">
    <keep-alive>
      <router-view></router-view>
    </keep-alive>
    <main-bar :preference="preference"></main-bar>
  </div>
</template>

<script>
import MainBar from '@/components/MainBar'
export default {
  name: "App",
  data() {
    return {
      preference: [],
      
    };
  },
  computed: {
    
  },
  components: {
    MainBar
  },
  created() {
    let data = {
      details: [
        {
          title: "首页",
          path: "/home",
        },
        {
          title: "分类",
          path: "/category",
        },
        {
          title: "购物车",
          path: "/cart",
        },
        {
          title: "我的",
          path: "/profile",
        },
      ],
    };
    this.preference = data.details;
  },
  mounted() {},
};
</script>

<style lang="less">
@import url("./assets/css/base.less");
</style>
