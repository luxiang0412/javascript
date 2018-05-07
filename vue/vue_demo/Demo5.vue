<template>
    <div class="hello">
        {{msg}}

        <div class="submit-box">
            <!--上面部分是负责用户输入可操作的输入区域，包括输入评论的用户名、评论内容和发布按钮，这一部分功能划分到一个单独的组件 CommentInput 中。-->
            <comment-input  @sendMsg="_handleInputMsg"/>
            <!--下面部分是评论列表-->
            <comment-list :message="comList" @delInfo="_delInfoList"/>
        </div>
    </div>
</template>
<script>
    import commentInput from './children/CommentInput.vue';
    import commentList from './children/CommentList.vue';
    export default {
        name: "Demo05",
        data() {
            return {
                msg: "demo05 -- 深刻理解Vue中的组件（2）--进阶篇",
                comList:[
                    
                ]
            };
        },
        created() {},
        mounted: function() {
            this.$nextTick(function() {
                
            });
        },
        components: {
            commentInput,
            commentList
        },
        methods: {
            //从子组件 CommentInput 获取 采集数据，再传递给 子组件 CommentList 
            _handleInputMsg(data) {
                this.comList.push(data);
            },
            //从子组件 CommentList 获取 index ,删除 this.comList 中的数据
            _delInfoList(index){
                this.comList.splice(index, 1)
            }
        }
    };
</script>
<style scoped lang="less">
    .submit-box{
        min-height: 600px;
        width: 700px;
        border: 1px solid #cccccc;
    }
</style>
