<script setup>
import { ref } from 'vue'

const menuData = ref(
  [
    {
      name: 'Features',
      path: '/Features'
    },
    {
      name: 'Pricing',
      path: '/Pricing'
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
      path: '/Main'
    }
  ]
)


const activeMenu = ref('Main')
</script>

<template>
  <header class="header-box">
    <div class="logo-box">
      <img class="logo-img" src="@/assets/img/logo.png" alt="">
    </div>

    <div class="menu-box">
      <div :class="{activeMenu: activeMenu === item.name}" class="menu" @click="activeMenu = item.name" v-for="(item,index) in menuData" :key="index">
        {{ item.name }}
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
    padding-top: 20px;
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
