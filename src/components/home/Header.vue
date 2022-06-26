<template>
  <div class="header">
    <!-- 左侧logo区 -->
    <div class="logo">
      <el-link :underline="false">遂宁经济技术开发区智慧排水管理平台</el-link>
    </div>
    <!-- 中间搜索框 -->
    <div class="input">
      <el-input v-model="input" placeholder="请输入搜索内容" class="input-with-select" color="#fff">
        <template #prepend>
          <el-select v-model="select" placeholder="选项" style="width: 80px" class="option" size="large">
            <el-option label="一" value="1" />
            <el-option label="二" value="2" />
            <el-option label="三" value="3" />
          </el-select>
        </template>
        <template #append>
          <el-button>
            <el-icon>
              <Search />
            </el-icon>
          </el-button>
        </template>
      </el-input>
    </div>
    <!-- 右侧下拉菜单 -->
    <div class="dropdown">
      <el-menu :default-active="activeIndex" class="menu" mode="horizontal" :ellipsis="false" @select="handleSelect">
        <a href="">
          <el-icon :size="20">
            <Refresh />
          </el-icon>
        </a>
        <el-sub-menu index="0">
          <template #title>
            <el-icon>
              <Setting />
            </el-icon>
            <span>系统设置</span>
          </template>
          <el-menu-item index="0-1">用户管理</el-menu-item>
          <el-menu-item index="0-2">角色管理</el-menu-item>
          <el-menu-item index="0-3">组织机构</el-menu-item>
          <el-menu-item index="0-4">岗位管理</el-menu-item>
          <el-menu-item index="0-5">值码表</el-menu-item>
        </el-sub-menu>
        <el-sub-menu index="1">
          <template #title>
            <el-icon>
              <User />
            </el-icon>
            <span>{{ username }}</span>
          </template>
          <el-menu-item index="1-1">我的信息</el-menu-item>
          <el-menu-item index="1-2">修改密码</el-menu-item>
          <el-menu-item index="1-3">退出</el-menu-item>
        </el-sub-menu>
      </el-menu>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  setup() {
    const activeIndex = ref('0')
    const input = ref('')
    const select = ref('')
    const username = ref('admin')
    const handleSelect = (key, keyPath) => {
      console.log(key, keyPath)
    }

    return { input, select, username, activeIndex, handleSelect }
  }
}
</script>

<style lang="scss" scoped>
.header {
  height: 60px;
  line-height: 60px;
  width: 100%;
  display: flex;
  border-bottom: 1px solid #409eff;
}

.logo,
.input,
.dropdown {
  flex: 1;
}

.logo .el-link {
  font-size: 20px;
  padding-left: 30px;
}

.dropdown {
  overflow: hidden;

  .menu {
    float: right;
  }

  a {
    padding-right: 40px;
  }
}


.el-menu--horizontal {
  height: 60px;
  border-bottom: none;
}

.el-select {
  ::placeholder {
    color: #ffffff;
  }
}

/deep/.input .el-icon {
  color: #fff !important;
}

/deep/.el-input-group__prepend .el-input__inner {
  color: #fff !important;
}
</style>  
