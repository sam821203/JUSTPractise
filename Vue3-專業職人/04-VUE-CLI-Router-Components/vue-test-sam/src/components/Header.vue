<script>
import { ref } from 'vue';

export default {
  setup(){

    const isOpen = ref(false);
    const handleMenuOpen = () => {
      isOpen.value = !isOpen.value;
    };

    return {
      isOpen, 
      handleMenuOpen,
    }
  }
};
</script>

<template>
  <header :class="{openMenu: isOpen}">
    <nav>
      <!-- <h1>Mike</h1> -->
      <router-link class="title" to="/">Mike</router-link>
      <a id="moblie_menu" href="javascript:;" @click="handleMenuOpen"></a>
      <div>
        <router-link to="/rwd">RWD</router-link>
        <router-link to="/vuejs">VUEJS</router-link>
        <a href="javascript:;">REACTJS</a>
        <a href="javascript:;">HTML5</a>
        <a href="javascript:;">NODEJS</a>
      </div>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
$color_1: #fff;
$background-color_1: #373c3f;

header {
  background-color: $background-color_1;
  width: 100%;
  height: 97px;
  @media screen and (max-width: 640px) {
    transition: height 0.2s;
    height: 37px;
    overflow: hidden;
    &.openMenu {
      height: 232px;
    }
  }
  > nav {
    position: relative;
    width: 1024px;
    height: 100%;
    margin: 0 auto;
    @media screen and (max-width: 1044px) {
      width: 100%;
    }
    @media screen and (max-width: 640px) {
      width: 100%;
      height: 232px;
    }
    > .title {
        line-height: 97px;
        font-size: 18px;
        float: left;
        color: $color_1;
        margin-right: 20px;
        @media screen and (max-width: 1044px) {
          margin-left: 5%;
        }
        @media screen and (max-width: 640px) {
          line-height: 37px;
        }
    }
    > div {
      width: 100%;
      height: 100%;
      @media screen and (max-width: 640px) {
        clear: both;
        width: 100%;
        height: 195px;
      }
      > a {
        display: block;
        line-height: 97px;
        font-size: 15px;
        float: left;
        color: $color_1;
        padding: 0 10px;
        @media screen and (max-width: 640px) {
          width: 100%;
          height: auto;
          overflow: hidden;
          line-height: 37px;
          text-align: center;
        }
      }
    }
  }
}
a#moblie_menu {
  display: none;
  @media screen and (max-width: 640px) {
    position: absolute;
    top: 0;
    right: 0;
    display: block;
    width: 37px;
    height: 37px;
    background-image: url("~@/assets/images/menu.jpg");
    background-position: 50% 50%;
    background-size: 95% auto;
    background-repeat: no-repeat;
  }
}
</style>
