<template>
  <el-container>
    <el-header>
      <div>
        <el-row :gutter="10">
          <el-col :span="4">
            <div><img :src="imgUrl" width="150%" height="50px"></div>
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
    <el-main>
      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="4"></el-col>
        <el-col :span="8">
          <span class="op-text">手工录入</span>
          <i style='font-size:75px' class="el-icon-edit-outline" @click="click"></i>
        </el-col>
        <el-col :span="8">
          <span class="op-text">批量导入</span>
          <i style='font-size:75px' class="el-icon-upload" @click="click"></i>
        </el-col>
        <el-col :span="4"></el-col>
      </el-row>
    </el-main>
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
    background-color: #FFFFFF;
    color: #333;
    text-align: center;
    line-height: 400px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }

  .op-text {
    position: relative;
    top: 2em;
    right: -3em;
  }

  .el-main .el-icon-edit-outline{
    -webkit-app-region: no-drag;
    right: -3em;
  }

  .el-main .el-icon-upload{
    -webkit-app-region: no-drag;
    right: -3em;
  }
</style>