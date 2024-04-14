<script setup>

</script>

<template>
  <div class="home-box">
    <div  id="Main" class="box-1-class">
      <h1 class="title">Employee Roster<br/>software made<br/>simple.</h1>
      <p class="text">Generate employee schedules, oversee shift requests, monitor labor expenses, and facilitate communication with your workforce.</p>
      <button class="btn">GET STARTED</button>
    </div>
    <div id="Pricing" class="box-1-class">
      <h1 class="title">Employee Roster<br/>software made<br/>simple.</h1>
      <p class="text">Generate employee schedules, oversee shift requests, monitor labor expenses, and facilitate communication with your workforce.</p>
      <button class="btn">GET STARTED</button>
    </div>
    <div id="Help" class="box-1-class">
      <h1 class="title">Employee Roster<br/>software made<br/>simple.</h1>
      <p class="text">Generate employee schedules, oversee shift requests, monitor labor expenses, and facilitate communication with your workforce.</p>
      <button class="btn">GET STARTED</button>
    </div>
    <div id="Features" class="box-1-class">
      <h1 class="title">Employee Roster<br/>software made<br/>simple.</h1>
      <p class="text">Generate employee schedules, oversee shift requests, monitor labor expenses, and facilitate communication with your workforce.</p>
      <button class="btn">GET STARTED</button>
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
  .null-box{
    height: 206px;
  }
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

}
</style>
