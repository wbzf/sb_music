<template>
  <div class="header" @click="changeTheme">
    <div class="header-left"></div>
    <p class="header-title">骨灰拌饭</p>
    <div class="header-right"></div>
  </div>
</template>

<script lang="js">
export default {
  name: 'Header',
  data () {
    return {
      themes: ['theme', 'theme1', 'theme2'],
      index: 0
    }
  },
  methods: {
    changeTheme () {
      this.index++
      if (this.index >= this.themes.length) {
        this.index = 0
      }
      document.documentElement.setAttribute('data-theme', this.themes[this.index])
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../assets/css/variable";
@import "../assets/css/mixin";
.header{
  width: 100%;
  height: 100px;
  @include bg_color();
  display: flex;
  justify-content: space-between;
  .header-left, .header-right{
    width: 84px;
    height: 84px;
    //background: #000;
    margin-top: 8px;
  }
  .header-left{
    @include bg_img('../assets/images/logo')
  }
  .header-right{
    @include bg_img('../assets/images/account')
  }
  .header-title{
    text-align: center;
    line-height: 100px;
    color: #fff;
    font-weight: bold;
    @include font_size($font_medium)
  }
}
</style>
