<template>
  <div id="home" class="wrapper">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <div class="content">
      <!-- 轮播图 -->
      <swiper :banner="banner" />
      <!-- recommend -->
      <recommend :recommend="recommend" />
      <!-- 本周流行 -->
      <feature />
      
      <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>


    </div>
  </div>
</template>

<script>
import NavBar from "@/components/common/navBar/navBar";
import Swiper from "./childComponents/swiper";
import Recommend from "./childComponents/recommend";
import Feature from "./childComponents/feature";

import { getHomeSwipe } from "@/api/home";

export default {
  name: "home",
  components: {
    NavBar,
    Swiper,
    Recommend,
    Feature
  },
  data() {
    return {
      banner: [],
      recommend: []
    };
  },
  methods: {
    // 获取banner,recommend数据
    homeSwipe() {
      getHomeSwipe().then(res => {
        console.log(res);
        this.banner = res.data.banner.list;
        this.recommend = res.data.recommend.list;
      });
    }
  },
  created() {
    this.homeSwipe();
  }
};
</script>

<style lang="scss" scoped>
#home {
  height: 100vh;
  // position: relative;
  .home-nav {
    width: 100%;
    background-color: var(--color-tint);
    color: #fff;
  }
}
</style>