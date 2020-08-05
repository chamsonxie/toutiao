
<!--  -->
<template>
<div class='article-box'>
    <input id="title"  type="text" placeholder="请输入标题">
    <vue-editor id="editor" use-custom-image-handler @image-added="handleImageAdded" v-model="htmlForEditor"> </vue-editor>
    <div class="editor-footer">
        <div class="send-btn">发布</div>
    </div>
</div>
</template>

<script>
import { VueEditor } from "vue2-editor";

export default  {
    name:'',
    components: {
        VueEditor
    },
    data() {
        return {
            htmlForEditor:""
        };
    },
    computed: {},
    watch: {},
    methods: {
        handleImageAdded: function(file, Editor, cursorLocation, resetUploader) {
            // An example of using FormData
            // NOTE: Your key could be different such as:
            // formData.append('file', file)

            var formData = new FormData();
            formData.append("file", file);

            this.$axios({
                url: "http://tt.linweiqin.com/api/tt/aliossUpload",
                method: "POST",
                data: formData
            })
            .then(result => {
                let url = result.data.url; // Get url from response
                Editor.insertEmbed(cursorLocation, "image", url);
                resetUploader();
                })
                .catch(err => {
                console.log(err);
            });
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
    .article-box{
        height: 400px;
        position: relative;
        padding: 20px;
        #title{
            width: 100%;
            height: 40px;
            font-size: 30px ;
            line-height: 40px ;
        }
        #editor{
            width: 100%;
            height: 300px;
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