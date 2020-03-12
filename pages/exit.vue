<!--
  功能：功能描述
  作者：jinyini
  时间：2020年03月02日 16:03:18
  版本：v1.0
  应用名称：
-->
<template>
    <div class="page-exit"></div>
</template>
<script>
export default {
    layout: "blank",
    middleware: async ctx => {
        let { status, data } = await ctx.$axios.get("/users/exit");
        if (status === 200 && data && data.code === 0) {
            window.location.href = "/";
        }
    }
};
</script>
<style lang='scss' scoped>
</style>