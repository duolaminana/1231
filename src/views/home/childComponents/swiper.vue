<template>
  <div>
    <mt-swipe :auto="4000" class="mt-swipe">
      <mt-swipe-item :key="index" v-for="(item,index) in banner" @click="imgClick(i)">
        <img :src="item.image" />
      </mt-swipe-item>
    </mt-swipe>
  </div>
</template>

<script>
export default {
  name: "swiper",
  props: {
    banner: {
      type: Array,
      default(){
        return []
      }
    }
  }
};
</script>

<style lang=scss scoped>
.mint-swipe {
  height: 200px;
  .mint-swipe-item {
    text-align: center;
  }
  img {
    //全部的轮播图都是高度100%；
    height: 100%;
  }
}
</style>