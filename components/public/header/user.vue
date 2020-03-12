<!--
  功能：功能描述
  作者：jinyini
  时间：2020年02月28日 11:09:27
  版本：v1.0
  应用名称：用户登录 
-->
<template>
    <div class="m-user">
        <template v-if="user">
            欢迎您，
            <span class="username">{{ user }}</span>
            [
            <nuxt-link to="/exit">退出</nuxt-link>]
        </template>
        <template v-else>
            <nuxt-link to="/login" class="login">立即登录</nuxt-link>
            <nuxt-link to="/register" class="register">注册</nuxt-link>
        </template>
    </div>
</template>
<script>
export default {
    data() {
        return {
            user: ""
        };
    },
    async mounted() {
        const {
            status,
            data: { user }
        } = await this.$axios.get("/users/getUser");
        if (status === 200) {
            this.user = user;
        }
    }
};
</script>
<style lang='stylus'></style>