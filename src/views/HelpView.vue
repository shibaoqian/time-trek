<script setup>
import { ref } from 'vue'

const tableData = ref([])
const inputData = ref('')
const helpData = [
  {
    title: 'what files can I upload?',
    content: 'You can upload any CSV, XLS, XLSX, TSV, TXT or TAB file that contains the names of your employees. The ordering of the columns in the file isn\'t important, but you should include a "name", "first name" or "last name" column. If you don\'t have a file ready then we recommend you start with our template, or you can just enter your employees manually above.'
  },
  {
    title: 'what happens after I upload my employees?',
    content: 'After you upload your employees we\'ll add them to a new team and you can begin scheduling on your 60 day trial. Don\'t forget - you\'ll need to save an account (email and password) to keep your access to the data that you\'ve just uploaded. If you don\'t save an account and you change browsers or computers, you might lose access to your data. You don\'t need a credit card to save an account and you can always delete your data if you choose not to continue with Tiimetrek.'
  },
  {
    title: 'How my staff log in?',
    content: 'When you\'re ready to give your employees access to Timetrek you will need to send them a welcome message from the "Outbox" or via "Send a message". This message will include a special single-use link that will allow them to choose a password and log in to Timetrtek. If your employees ever forget the password they have chosen they can always use the "Forgotten your password" link on the log in page to restart the process and choose a new password.'
  },
]



const handleEnter = () => {
  tableData.value.push(inputData.value)
  inputData.value = ''
}
</script>

<template>
<div class="help-box">
  <div class="box-1-class">
    <h1 class="title">Let's craft a<br/>schedule at no cost!</h1>
    <p class="text">Use the form below to enter your employees, or upload a spreadsheet, or import your employees from another app.</p>
    <div class="table-box">
      <div class="tips">
        <img src="@/assets/img/tips.png" alt="">
      </div>
      <div class="table-col">
        <div class="table-row" v-for="(item,index) in tableData" :key="index">
          {{ index + 1 }}.
          {{ item }}
        </div>
        <div class="table-row">
          {{ tableData.length + 1 }}.
          <input v-model="inputData" @keydown.enter="handleEnter" type="text">
        </div>
      </div>
      <button @click="handleEnter" class="add-btn">ADD EMPLOYEES</button>
      <a class="bottom-tis">upload a CSV or Excel file</a>
    </div>
  </div>
  <div class="help-list">
    <div class="box" v-for="(item,index) in helpData" :key="index">
      <div class="title">{{ item.title }}</div>
      <div class="content">{{ item.content }}</div>
    </div>
  </div>
</div>
</template>

<style scoped>
.help-box{
  max-width: 100%;
  display: flex;
  align-items: center;
  margin: 0 0 0 50px;
  flex-direction: column;
  .box-1-class{
    position: relative;
    .title{
      color: white;
      font-size: 80px;
      line-height: 120px;
      font-weight: 900;
      text-align: left;
    }
    .text{
      color: white;
      margin-top: 20px;
      text-align: left;
      width: 600px;
    }
    .table-box{
      background: white;
      padding: 20px;
      margin-top: 20px;
      .tips{
        text-align: right;
      }
      .table-col{
        display: flex;
        flex-flow: column;
        .table-row{
          display: flex;
          height: 80px;
          align-items: center;
          color: black;
          border-bottom: #cccccc 1px solid;
          input{
            margin-left: 20px;
            border: none;
            outline: none;
            font-size: 20px;
          }
        }
      }
      .add-btn{
        color: white;
        background: #267198;
        border: none;
        width: 160px;
        height: 40px;
        margin-top: 40px;
        cursor: pointer;
        &:hover{
          background: #1e5775;
        }
        &:active{
          background: #133649;
        }
      }
      .bottom-tis{
        margin-top: 50px;
        color: #267198;
        font-size: 12px;
        display: block;
        text-decoration: #267198 1px underline;
      }
    }

  }
  .help-list{
    margin: 100px 0;
    width: 1200px;
    .box{
      margin-top: 40px;
      .title{
        font-size: 50px;
      }
      .content{
        margin-top: 20px;
      }
    }

  }
}

</style>
