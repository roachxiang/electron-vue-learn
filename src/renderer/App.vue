<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'qrcode'
  }
</script>

<style>
    * {
    margin: 0;
    padding: 0;
    font-family:"Microsoft YaHei",Arial;
  }

  html,
  body,
  #app { height: 100%; }
</style>
