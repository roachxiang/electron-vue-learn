<template>
  <el-container>
    <el-header>
      <div>
        <el-row :gutter="10">
          <el-col :span="4">
            <div><img :src="imgUrl" width="100%" height="50px"></div>
          </el-col>
          <el-col :span="16">
            <div class="title">一证通电子录入系统</div>
          </el-col>
          <el-col :span="4">
            <div class="icon">
              <i id='min' style='font-size:25px' class="el-icon-minus" @click="click"></i>
              <i id='close' style='font-size:25px' class="el-icon-close" @click="click"></i>
            </div>
          </el-col>
        </el-row>
      </div>
    </el-header>
    <el-main>Main</el-main>
  </el-container>
</template>

<script>
  const {ipcRenderer: ipc} = require('electron')
export default {
    components: {
    },
    name: 'landing-page',
    data () {
      return {
        imgUrl: 'static/dian_logo.png'
      }
    },
    methods: {
      click: function (e) {
        var targetid = e.target.id
        if (targetid === 'min') {
          ipc.send('min')
        }

        if (targetid === 'close') {
          ipc.send('close')
        }
      }
    }
  }
</script>

<style>
  .el-container {
    height: 100%;
  }

  .el-header {
    background-color: #E6EAED;
    color: #333;
    text-align: center;
    line-height: 60px;
    -webkit-app-region: drag;
  }

  .el-header .title {
    font-size: 20px;
  }

  .el-header .icon {
    float: right;
  }

  .el-header .icon .el-icon-minus{
    -webkit-app-region: no-drag;
  }

  .el-header .icon .el-icon-close{
    -webkit-app-region: no-drag;
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
</style>