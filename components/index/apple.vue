<!--
  功能：功能描述
  作者：jinyini
  时间：2020年03月02日 09:22:24
  版本：v1.0
  应用名称：
-->
<template>
    <div class="m-istyle">
        <dl>
            <dt>有格调</dt>
            <dd :class="{active:kind==='all'}" kind="all" keyword="景点" @mouseenter="enter">全部</dd>
            <dd :class="{active:kind==='part'}" kind="part" keyword="美食" @mouseenter="enter">约会聚餐</dd>
            <dd :class="{active:kind==='spa'}" kind="spa" keyword="丽人" @mouseenter="enter">丽人SPA</dd>
            <dd :class="{active:kind==='movie'}" kind="movie" keyword="电影" @mouseenter="enter">电影演出</dd>
            <dd
                :class="{active:kind==='travel'}"
                kind="travel"
                keyword="旅游"
                @mouseenter="enter"
            >品质出游</dd>
        </dl>
        <ul class="ibody">
            <li v-for="item in cur" :key="item.title">
                <el-card>
                    <img :src="item.img" class="image" alt="封面" />
                    <ul class="cbody">
                        <li class="title">{{item.title}}</li>
                        <li class="pos">
                            <span>{{item.pos}}</span>
                        </li>
                        <li class="price">
                            ￥
                            <em>{{item.price}}</em>
                            <span>/起</span>
                        </li>
                    </ul>
                </el-card>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data() {
        return {
            kind: "all",
            list: {
                all: [
                    {
                        title: "东星贝儿凯克生日蛋糕",
                        img:
                            "//p0.meituan.net/bbia/850ce195a4db8d447644429ac6e32c20330100.jpg@368w_208h_1e_1c",
                        pos:
                            "人气星选：6英寸生日礼物欧式水果蛋糕（卡通蛋糕）新鲜先做，传统十大阿萨",
                        price: "58"
                    }
                ],
                part: [
                    {
                        title: "东星贝儿凯克生日蛋糕1",
                        img:
                            "//p0.meituan.net/bbia/850ce195a4db8d447644429ac6e32c20330100.jpg@368w_208h_1e_1c",
                        pos:
                            "人气星选：6英寸生日礼物欧式水果蛋糕（卡通蛋糕）新鲜先做，传统十大阿萨",
                        price: "58"
                    },
                    {
                        title: "东星贝儿凯克生日蛋糕2",
                        img:
                            "//p0.meituan.net/bbia/850ce195a4db8d447644429ac6e32c20330100.jpg@368w_208h_1e_1c",
                        pos:
                            "人气星选：6英寸生日礼物欧式水果蛋糕（卡通蛋糕）新鲜先做，传统十大阿萨",
                        price: "58"
                    }
                ],
                spa: [],
                movie: [],
                travel: []
            }
        };
    },
    computed: {
        cur() {
            return this.list[this.kind];
        }
    },
    methods: {
        enter(e) {
            this.kind = e.target.getAttribute("kind");
            // this.kind = e.target;
            console.log(this.kind);
        }
    }
};
</script>
<style lang='scss' scoped>
@import "@/assets/css/index/artistic.scss";
</style>