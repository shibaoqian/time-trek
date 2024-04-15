<script setup>
import { computed, ref } from 'vue'
import {useRoute} from 'vue-router'

const route = useRoute()
const menuData = ref(
  [
    {
      name: 'Features',
      path: '/#Features'
    },
    {
      name: 'Pricing',
      path: '/#Pricing'
    },
    {
      name: 'Help',
      path: '/Help'
    },
    {
      name: 'Login',
      path: '/Login'
    },
    {
      name: 'Main',
      path: '/#Main'
    }
  ]
)


const activeMenu = computed(() => {
  return route.name === 'Login' || route.name === 'Help' ? route.name : route.hash.split('#')[1] || 'Main'
})
</script>

<template>
  <header class="header-box">
    <div class="logo-box">
      <img class="logo-img" src="@/assets/img/logo.png" alt="">
    </div>
    <div class="menu-box">
      <router-link :class="{activeMenu: activeMenu === item.name}"
           class="menu"
           @click="activeMenu = item.name" v-for="(item,index) in menuData" :key="index" :to="item.path">
        {{ item.name }}
      </router-link>
    </div>
  </header>
</template>

<style scoped lang="scss">
.header-box{
  display: flex;
  .logo-box{
    width: 40%;
    text-align: center;
    .logo-img{
      width: 200px;
      height: 200px;
    }
  }
  .menu-box{
    display: flex;
    padding-top: 40px;
    align-items: start;
    background: var(--vt-c-white);
    height: 100px;
    .menu{
      margin: 0 20px;
      font-size: 22px;
      cursor: pointer;

    }
    .activeMenu{
      color: #0000ff;
    }
  }
}

</style>
