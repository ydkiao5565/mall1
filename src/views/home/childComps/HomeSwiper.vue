<template>
  <swiper>
      <swiper-item v-for="item in banners" :key="item.link">
        <a :href="item.link">
          <img :src="item.image" alt="">
        </a>
      </swiper-item>
    </swiper>
</template>

<script>
import {Swiper, SwiperItem} from "components/common/swiper/index.js"
export default {
  name: 'HomeSwiper',
  data(){
    return {}
  },
  components: {
    Swiper,
    SwiperItem
  },
  created(){},
  mounted(){},
  methods: {},
  props: {
    banners: {
      type: Array,
      defualt(){
        return []
      }
    }
  }
}
</script>
<style scoped>
</style>
