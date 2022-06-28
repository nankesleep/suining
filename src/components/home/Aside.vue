<template>
    <div class="aside">
        <!-- 展开折叠 -->
        <el-radio-group v-model="isCollapse" style="margin-bottom: 20px">
            <el-radio-button :label="false">
                <el-icon>
                    <Menu />
                </el-icon>
            </el-radio-button>
            <el-radio-button :label="true">
                <el-icon>
                    <Close />
                </el-icon>
            </el-radio-button>
        </el-radio-group>
        <!-- 导航栏  -->
        <el-menu default-active="0" class="el-menu-vertical-demo" :collapse="isCollapse" @select="handleSelect">
            <el-menu-item index="0">
                <el-icon>
                    <House />
                </el-icon>
                <template #title>主页</template>
            </el-menu-item>
            <el-menu-item index="1">
                <el-icon>
                    <FullScreen />
                </el-icon>
                <template #title>大屏</template>
            </el-menu-item>
            <el-menu-item index="2">
                <el-icon>
                    <PriceTag />
                </el-icon>
                <template #title>检查任务</template>
            </el-menu-item>
            <!-- 检查报告 -->
            <el-sub-menu index="3">
                <template #title>
                    <el-icon>
                        <List />
                    </el-icon>
                    <span>检查报告</span>
                </template>
                <el-menu-item index="3-1">现场记录</el-menu-item>
                <el-menu-item index="3-2">混接点</el-menu-item>
                <el-menu-item index="3-3">管段缺陷</el-menu-item>
            </el-sub-menu>
            <!-- 缺陷评估 -->
            <el-sub-menu index="4">
                <template #title>
                    <el-icon>
                        <DocumentChecked />
                    </el-icon>
                    <span>缺陷评估</span>
                </template>
                <el-menu-item index="4-1">缺陷状况评估表</el-menu-item>
                <el-menu-item index="4-2">缺陷数量统计</el-menu-item>
            </el-sub-menu>
            <!-- 基础数据 -->
            <el-sub-menu index="5">
                <template #title>
                    <el-icon>
                        <Search />
                    </el-icon>
                    <span>缺陷评估</span>
                </template>
                <el-menu-item index="5-1">管点信息</el-menu-item>
                <el-menu-item index="5-2">管线信息</el-menu-item>
                <el-menu-item index="5-3">检查井</el-menu-item>
                <el-menu-item index="5-4">雨水口</el-menu-item>
                <el-menu-item index="5-5">连接暗井</el-menu-item>
                <el-menu-item index="5-6">排放口</el-menu-item>
                <el-menu-item index="5-7">排水管</el-menu-item>
                <el-menu-item index="5-8">排水渠</el-menu-item>
            </el-sub-menu>
        </el-menu>
    </div>
</template>

<script>
import { ref } from 'vue'
export default {
    setup() {
        const isCollapse = ref(true)
        const handleSelect = (key, keyPath) => {
            console.log(key, keyPath)
        }
        return { isCollapse, handleSelect }
    }
}

</script>

<style lang="scss" scoped>
.aside{
    position: absolute;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 335px;
}

.el-radio-group {
    padding: 20px 0 0 5px;
    width: 60px;
}

/deep/.el-radio-button__inner {
    padding: 5px;
    width: 30px;
}
</style>