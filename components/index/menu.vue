<!--
  功能：功能描述
  作者：jinyini
  时间：2020年02月28日 16:31:25
  版本：v1.0
  应用名称：
-->
<template>
    <div class="m-menu">
        <dl class="nav" @mouseleave="leave">
            <dt>全部分类</dt>
            <dd v-for="(item,index) in $store.state.home.menu" :key="index" @mouseenter="enter">
                <i :class="item.type" />
                {{item.name}}
                <span class="arrow" />
            </dd>
        </dl>
        <div class="detail" v-if="kind" @mouseenter="sover" @mouseleave="sout">
            <template v-for="(item,idx) in curdetail.child">
                <h4 :key="idx">{{item.title}}</h4>
                <span v-for="v in item.child" :key="v">{{v}}</span>
                <span>子项</span>
            </template>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            kind: ""
        };
    },
    computed: {
        curdetail() {
            return this.$store.state.home.menu.filter(
                item => item.type === this.kind
            )[0];
        }
    },
    methods: {
        leave() {
            let self = this;
            self._timer = setTimeout(function() {
                self.kind = "";
            }, 150);
        },
        enter(e) {
            this.kind = e.target.querySelector("i").className;
        },
        sover() {
            clearTimeout(this._timer);
        },
        sout() {
            this.kind = "";
        }
    }
};
</script>
<style lang='scss'>
</style>