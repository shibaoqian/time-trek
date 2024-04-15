<script setup>

import HeaderBox from '@/layout/components/headerBox.vue'
import ContentBox from '@/layout/components/contentBox.vue'
import FooterBox from '@/layout/components/footerBox.vue'
</script>

<template>
  <div class="app-box">
    <header-box></header-box>
    <content-box></content-box>
    <footer-box></footer-box>
  </div>
</template>

<style scoped>
.app-box{
  width: 100%;
}
</style>
