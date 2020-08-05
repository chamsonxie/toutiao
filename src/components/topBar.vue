<!--  -->
<template>
<div class='top-bar'>
    <div class="left">
        <a v-for="(item,index) in leftList" :key="item+index" :href="item.url"  >{{item.name}}</a>
    </div>
    <div class="right">
        <a v-for="(item,index) in rightLinks"  :key="item+index" :href="item.url" >{{item.name}}</a>
    </div>
</div>
</template>

<script>
export default {
    name:'',
    components: {},
    data() {
        return {
            leftList:[
                {name:"下载app",url:"#/"},
                {name:"注册头条号",url:"#/"}
            ],
            weather:{

            },
            rightLinks:[
                {
                    name:"侵权投诉",
                    url:"#/"
                },
                {
                    name:"头条产品",
                    url:"#/"
                }
            ]
        };
    },
    computed: {},
    watch: {},
    methods: {},
    created() {},
    mounted() {},
    beforeCreate() {},
    beforeMount() {},
    beforeUpdate() {},
    updated() {},
    beforeDestroy() {},
    destroyed() {},
    activated() {},
}
</script>
<style lang='less'  scoped>
    .top-bar{
        height: 34px;
        min-width: 1220px;
        background-color: #333;
        padding: 0 16px;
        a{
            padding: 0 18px;
            line-height: 34px;
            color: rgb(255, 255, 255) !important;
            font-size: 14px;
        }
        .left{
            float: left;
            a:first-child{
                position: relative;
            }
            a:first-child::after{
                content: "";
                display: block;
                position: absolute;
                right: 0;
                top: -50%;
                height: 34px;
                width: 1px;
                background-color:    #666;
            }
        }
        .right{
            float: right;
            a:last-child{
                position: relative;
            }
            a:last-child::before{
                content: "";
                display: block;
                position: absolute;
                left: 0;;
                top: -50%;
                height: 34px;
                width: 1px;
                background-color:    #666;
            }
        }
    }   
</style>