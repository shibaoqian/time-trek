<script setup>
import { ref } from 'vue'

const footerData = ref(
  [
    {
      name: 'Explore',
      children: ['Your teams','Features','Pricing','Free 60 day trial','About us']
    },
    {
      name: 'Help',
      children: ['Getting started','Knowledge base','Video Guides & webinars','Keyboard shortcuts','Tips & tricks','Contact support']
    },
    {
      name: 'Features',
      children: ['Employee scheduling','Time & attendance','Reporting & payroll','Reminders & notifications','Time off management','Free for small teams']
    },
    {
      name: 'Resources',
      children: ['Developer API','Integrations','Blog','Time dock','Customisations','Free Excel template']
    },
    {
      name: 'More',
      children: ['Terms & conditions','Privacy policy','Cookie policy','Data protection','Site map','Visit our UK site']
    },
  ]
)
</script>

<template>
  <div class="footer">
    <div class="list-box">
      <div v-for="(item,index) in footerData" :key="index" class="list-item">
        <h3>{{item.name}}</h3>
        <ul>
          <li v-for="(child,index) in item.children" :key="index">{{child}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
.footer{
  background: #004163;
  .list-box{
    display: flex;
    justify-content: center;
    padding: 60px 0;
    .list-item{
      margin: 0 30px;
    }
    h3{
      font-size: 20px;
    }
    ul{
      margin-top: 20px;
      padding: 0;
      line-height: 30px;
    }
    li{
      list-style-type: none;
      font-size: 16px;
    }
  }
}
</style>
