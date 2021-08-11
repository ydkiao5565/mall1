<template>
  <tab-ber>
    <tab-ber-item path="/home" activeColor="lightPink">
      <img slot="item-icon" src="~assets/img/tabbar/home.svg" />
      <img slot="item-icon-actived" src="~assets/img/tabbar/home_active.svg" />
      <div slot="item-text">首页</div>
    </tab-ber-item>
    <tab-ber-item path="/category" activeColor="lightPink">
      <img slot="item-icon" src="~assets/img/tabbar/category.svg" />
      <img slot="item-icon-actived" src="~assets/img/tabbar/category_active.svg" />
      <div slot="item-text">分类</div>
    </tab-ber-item>
    <tab-ber-item path="/cart" activeColor="lightPink">
      <img slot="item-icon" src="~assets/img/tabbar/cart.svg" />
      <img slot="item-icon-actived" src="~assets/img/tabbar/cart_active.svg" />
      <div slot="item-text">购物车</div>
    </tab-ber-item>
    <tab-ber-item path="profile" activeColor="lightPink">
      <img slot="item-icon" src="~assets/img/tabbar/profile.svg" />
      <img slot="item-icon-actived" src="~assets/img/tabbar/profile_active.svg" />
      <div slot="item-text">我的</div>
    </tab-ber-item>
  </tab-ber>
</template>

<script>
import TabBer from "components/common/tabber/TabBer.vue"
import TabBerItem from "components/common/tabber/TabBerItem.vue"
export default {
  name: "MainTab",
  data() {
    return {};
  },
  components: {
    TabBer,
    TabBerItem
  },
  created() {},
  mounted() {},
  methods: {},
};
</script>
<style scoped>
</style>
