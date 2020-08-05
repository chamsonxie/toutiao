<!--  -->
<template>
<div class='left-nav'>
    <a href="#">
        <img :src="logo" alt="">
    </a>
    <ul>
        <li v-for="(item,index) in navlist" :key="item+index">
            <a :href="item.url" @click="activeItem(index)" :class="{'active':item.isactive}">{{item.name}}</a>
        </li>
    </ul>

</div>
</template>

<script>
export default {
    name:'',
    components: {},
    data() {
        return {
            logo:"https://s3.pstatp.com/toutiao/static/img/logo.271e845.png",
            navlist:[
                {name:"推荐",url:"#/",isactive:true},
                {name:"西瓜视频",url:"#/",isactive:false},
                {name:"热点",url:"#/",isactive:false},
                {name:"直播",url:"#/",isactive:false},
                {name:"图片",url:"#/",isactive:false},
                {name:"科技",url:"#/",isactive:false},
                {name:"娱乐",url:"#/",isactive:false},
                {name:"游戏",url:"#/",isactive:false},
                {name:"体育",url:"#/",isactive:false},
                {name:"懂车帝",url:"#/",isactive:false},
                {name:"财经",url:"#/",isactive:false},
                {name:"搞笑",url:"#/",isactive:false},
                {name:"更多",url:"#/",isactive:false},
            ]
        };
    },
    computed: {},
    watch: {},
    methods: {
        activeItem:function(index){
            this.navlist.map(function(v,i){
                if(i==index){
                    v.isactive = true
                }else{
                    v.isactive = false
                }
            })
        }
    },
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
    .left-nav{
        img{
            width: 110px;
        }
        a{
            width: 110px;
        }
        ul{
            list-style: none;
            margin-top: 16px;
            li{
                a{
                    display: block;
                    height: 40px;
                    line-height: 40px;
                    text-align: center;
                    color: #444;
                    transition: 0.15s ease-in-out;
                    border-radius: 4px;
                }
                a:hover{
                    background-color: #ed4040;
                    color: white;
                }
                a.active{
                    background-color: #ed4040;
                    color: white;
                }
            }
        }

    }
</style>