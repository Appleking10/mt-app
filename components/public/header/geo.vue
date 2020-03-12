<!--
  功能：功能描述
  作者：jinyini
  时间：2020年02月28日 10:41:55
  版本：v1.0
  应用名称：定位
-->
<template>
    <div class="m-geo">
        <i class="el-icon-location" />{{$store.state.geo.position.city}}
        <nuxt-link class="changeCity" to="/changeCity">切换城市</nuxt-link>[广州 深圳 汕头]
    </div>
</template>

<script>
export default {};
</script>

<style scoped>

</style>