<template>
  <router-view />
</template>

<script>
//具体项目vue名
import Home from '@/views/Home.vue'

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
.el-menu--collapse .el-menu .el-submenu,.el-menu--popup {
  min-width: 120px !important;
}

.el-input-group__append, .el-input-group__prepend {
    background-color: #409eff !important;
}


</style>