<!--  -->
<template>
<div class='send-box-inner'>
    <ul>
        <li v-for="item in options" :class="{'active':componentId==item.componentId}" :key="item" @click="componentId=item.componentId">{{item.name}}</li>
    </ul>
    <div class="send-content">
        <keep-alive>
            <component :is="componentId"></component>
        </keep-alive>
    </div>
</div>
</template>

<script>
import sendMicro from '@/components/sendBox/sendMicro'
import sendArticle from '@/components/sendBox/sendArticle'
import sendQuestion from '@/components/sendBox/sendQuestion'
import sendVideo from '@/components/sendBox/sendVideo'
// import {sendMicro,sendArticle,sendQuestion,sendVideo} from '@/components/sendBox/'
export default {
    name:'',
    components: {
        sendMicro,sendArticle,sendQuestion,sendVideo
    },
    data() {
        return {
            componentId:"sendArticle",
            options:[
                {name:"发微头条",componentId:"sendMicro"},
                {name:"写文章",componentId:"sendArticle"},
                {name:"提问题",componentId:"sendQuestion"},
                {name:"发视频",componentId:"sendVideo"},
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
    .send-box-inner{
        width: 100%;
        ul{
            list-style: none;
            height: 44px;
            li{
                float: left;
                height: 44px;
                margin-left: 19px;
                line-height: 42px;
                border-bottom: 2px solid transparent;
                cursor: pointer;
            }
            li.active{
                border-bottom: 2px solid #ed4040;
                font-weight: 600;
            }
        }
    }
</style>