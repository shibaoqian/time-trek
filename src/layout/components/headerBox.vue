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
      <div v-for="(item,index) in menuData" :key="index" >
        <router-link v-if="item.name !== 'Login'" :class="{activeMenu: activeMenu === item.name}" :to="item.path"
                     class="menu"
                     @click="activeMenu = item.name" >
          {{ item.name }}
        </router-link>
        <a v-else class="menu" href="http://ec2-13-212-13-238.ap-southeast-1.compute.amazonaws.com:8075/admin/login">{{ item.name }}</a>
      </div>

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
    gap: 20px;
    .menu{
      //margin: 0 20px;
      font-size: 22px;
      cursor: pointer;

    }
    .activeMenu{
      color: #0000ff;
    }
  }
}
@media screen and (max-width: 1200px) {
  .logo-box{
    width: 30% !important;
    .logo-img{
      width: 20vw !important;
      height: 20vw !important;
    }
  }
  .menu-box{
    gap: 10px!important;
  }
  .menu{
    margin: 0 !important;
    font-size: 12px !important;
    cursor: pointer;

  }
}
</style>
