<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <feature-view></feature-view>

    <tab-control class="tab-control" :titles="['流行','新款','精选']"></tab-control>

    <ul>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
      <li>ssss</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar.vue";
import HomeSwiper from "./childComps/HomeSwiper.vue"
import FeatureView from "./childComps/FeatureView.vue"
import RecommendView from './childComps/RecommendView.vue';

import TabControl from "components/content/tabControl/TabControl.vue"

import {getHomeMultidata , getHomeGoods} from 'network/home.js'
export default {
  name: "",
  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        'pop': {page: 0,list: []},
        'new': {page: 0,list: []},
        'sell': {page: 0,list: []},
      }
    };
  },
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl,
  },
  created() {
    this.getHomeMultidata()
    this.getHomeGoods('pop')
    this.getHomeGoods('new')
    this.getHomeGoods('sell')
  },
  mounted() {},
  methods: {
    getHomeMultidata(){
      getHomeMultidata().then(res => {
      this.banners = res.data.banner.list
      this.recommends = res.data.recommend.list
    })
    },
    getHomeGoods(type){
      const temp = this.goods[type].page ++
      getHomeGoods(type,temp).then(res => {
        console.log(res)
      })
    }
  },
};
</script>
<style scoped>
#home {
  padding-top: 44px;
}
.home-nav {
  background-color: var(--color-tint);
  color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 1;
}
.tab-control {
  position:sticky;
  top: 44px;
  background-color: #fff;
}
</style>
