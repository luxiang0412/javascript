<template>
	<div id="hello">
		<ul>
			<li v-for="(item,index) in message":key="item.id">{{item.userName}}--{{item.userCode}}--{{item.userInfo}} <span @click="_handleDel(index)">删除</span></li>
		</ul>
	</div>
</template>

<script>
    export default {
        name: "Demo01",
        data() {
            return {
                person: {
    
                }
            };
        },
        created() {},
        //从demo05 父组件中获取 数据，并展示
        props: ['message'],
        methods: {
            
            _handleDel(index) {
                this.$emit('delInfo', index)
            }
        },
        mounted: function() {
            this.$nextTick(function() {
    
            });
        },
    };
</script>

<style scoped lang="less">
    .hello {
        height: 200px;
        h2 {
            background: #dcdc3e;
        }
    }
</style>