<template>
  <div class='tab-bar-item' @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-actived"></slot></div>
    <div :style="isActiveColor"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
export default {
  name: 'TabBerItem',
  data(){
    return {}
  },
  props: {
    path: '',
    activeColor: {
      type: String,
      default: 'lightSkyBlue'
    }
  },
  computed: {
    isActive(){
      return this.$route.path.indexOf(this.path) !== -1
    },
    isActiveColor(){
      return this.isActive ? {color: this.activeColor} : {}
    }
  },
  components: {},
  created(){},
  mounted(){},
  methods: {
    itemClick(){
      this.$router.push(this.path)
      // console.log(this.is)
    }
  }
}
</script>
<style scoped>
  .tab-bar-item {
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 16px;
  }
  .tab-bar-item img {
    width: 24px;
    height: 24px;
    vertical-align:middle;
  }
  
</style>
