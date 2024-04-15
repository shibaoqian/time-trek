<script setup>
import { ref } from 'vue'
const softwareList = ref(
  [
    'bars, restaurants & cafes',
    'call centers & support',
    'Cinemas & live events',
    'Emergency workers & first responders',
    'Gym & fitness centers',
    'Hospitals, medical care centers',
    'Retail stores & supermarkets',
    'Schools & universities',
    'Shipping & transportation',
  ]
)
</script>

<template>
  <div class="home-box">
    <div  id="Main" class="box-1-class">
      <h1 class="title">Employee Roster<br/>software made<br/>simple.</h1>
      <p class="text">Generate employee schedules, oversee shift requests, monitor labor expenses, and facilitate communication with your workforce.</p>
      <button class="btn">GET STARTED</button>
    </div>
    <div class="box-2-class">
      <h1 class="box-title">Manage your staff on<br/>the go.</h1>
      <p class="text center">Whether you're working remotely or on the move, Timetrek is accessible wherever you are. No installations or downloads required. All the tools for managing your staff are conveniently available directly in your web browser.</p>
      <img class="box2-img" src="@/assets/img/box2.png" alt="">
    </div>
    <div class="box-3-class">
      <h1 class="box-title">SCHEDULING<br/>SOFTWARE FOR<br/>EVERYONE.</h1>
      <div class="software-list">
        <div class="software" v-for="(item,index) in softwareList" :key="index">
          <img :src="`/images/box3-img${index + 1}.png`" alt="">
          <p>{{ item }}</p>
        </div>
      </div>
    </div>
    <div id="Features" class="box-4-class">
      <h1 class="box-title">Loaded with features<br/>you'll appreciate.</h1>
      <div class="features-list">
        <img v-for="item in 12" :src="`/images/features${item}.png`" :key="item" alt="">
      </div>
    </div>
    <div id="Pricing" class="box-5-class">
      <h1 class="box-title">Continuously<br/>benefit from free<br/>scheduling for small<br/>teams.</h1>
      <p class="text center">Managing a small team of 5 or less? You get to <a href="https://www.findmyshift.com/pricing/free-for-small-teams">schedule your staff for free</a>,<br/> forever!</p>
      <div class="pricing-list">
        <img v-for="item in 4" :src="`/images/pricing${item}.png`" :key="item" alt="">
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.home-box {
  max-width: 100%;
  display: flex;
  align-items: center;
  margin: 0 0 0 50px;
  flex-direction: column;
  .box-1-class{
    width: calc(100vh - 110px);
    height: calc(100vh - 110px);
    position: relative;
    text-align: center;
    .title{
      color: white;
      font-size: 80px;
      line-height: 120px;
      font-weight: 900;
      text-align: left;
    }
    .text{
      color: white;
      margin-top: 40px;
      text-align: left;
    }
    .btn{
      background: #16EE1F;
      color: white;
      text-align: center;
      margin-top: 100px;
      width: 160px;
      height: 50px;
      border-radius: 40px;
      border: none;
      cursor: pointer;
      font-weight: 600;
      &:hover{
        background: #16bb1a;
      }
      &:active{
        background: #0f8412;
      }

    }
    &::after {
      content: ' ';
      background-image: url("@/assets/img/logo.png");
      background-size: cover;
      background-repeat: no-repeat;
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      opacity: 0.2;
      z-index: -1;
    }
  }
  .box-title{
    font-size: 80px;
    line-height: 90px;
  }
  .box-2-class{
    width:1000px;

    .text{
      margin-top: 40px;
      font-size: 20px;
    }
    .box2-img{
      width: 100%;
      margin-top: 40px;
    }
  }
  .box-3-class{
    width:1000px;
    margin-top: 100px;
    .software-list{
      display: flex;
      flex-flow: wrap;
      justify-content: center;
      gap: 20px;
      margin-top: 50px;
      .software{
        width: 18%;
        text-align: center;
        display: flex;
        flex-flow: column;
        justify-content: space-between;
        align-items: center;
      }
    }
  }
  .box-4-class{
    margin-top: 100px;
    width:1000px;
    .box-title{
      text-align: right;
    }
    .features-list{
      margin-top: 50px;
      display: flex;
      flex-flow: wrap;
      gap: 20px;
      justify-content: center;
      img{
        width: calc(33% - 10px);
        &:hover{
          transform: scale(1.05);
          transition: all 0.2s ease-in-out;
        }
      }
    }
  }
  .box-5-class{
    margin-top: 100px;
    width:1000px;
    .text{
      font-size: 20px;
      margin-top: 40px;
      a{
        text-decoration: white 1px underline;
      }
    }
    .pricing-list{
      display: flex;
      gap: 20px;
      margin: 50px 0;
      img{
        width: calc(33% - 20px);
        &:hover{
          transform: scale(1.05);
          transition: all 0.2s ease-in-out;
        }
      }
    }
  }
}
</style>
