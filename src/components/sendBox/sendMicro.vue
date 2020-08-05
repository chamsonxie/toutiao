<!-- 发微头条 -->
<template>
<div class='send-micro'>
    <textarea name=""  id="" ></textarea>
    <div class="editor-footer">
        <div class="send-btn">发布</div>
    </div>
</div>
</template>

<script>
export default {
    name:'',
    components: {},
    data() {
        return {};
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
    .send-micro{
        height: 300px;
        position: relative;
        padding: 20px;
        textarea{
            width: 575px;
            height: 182px;
            padding: 20px;
            resize: none;
            outline-color: #e8e8e8;
        }
        .editor-footer{
            height: 40px;
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            border-top: 1px solid #e8e8e8;
            .send-btn{
                position: absolute;
                right: 0;
                height: 40px;
                width: 120px;
                background-color: #ed4040;
                opacity: .8;
                text-align: center;
                line-height: 40px;
                color: white;
            }
        }
    }
</style>