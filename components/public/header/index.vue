<!--
  功能：功能描述
  作者：jinyini
  时间：2020年02月28日 14:56:54
  版本：v1.0
  应用名称：
-->
<template>
    <div class="m-header">
        <el-row>
            <el-col>
                <top-bar />
            </el-col>
        </el-row>
        <el-row>
            <el-col>
                <search-bar />
            </el-col>
        </el-row>
    </div>
</template>
<script>
import topBar from "./topbar.vue";
import searchBar from "./searchbar.vue";
export default {
    method: {},
    components: {
        topBar,
        searchBar
    }
};
</script>
<style lang='scss'>
@import "@/assets/css/public/header/index.scss";
</style>