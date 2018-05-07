<template>
	<div class="com-input">
		学生姓名：
		<input type="text" v-model="userName"><br>
		学生学号：
		<input type="text" v-model="userCode"><br>
		学生个人信息：
		<textarea v-model="userInfo" name="" id="" cols="30" rows="10"></textarea><br>
		<el-button round @click="_handleClick()">圆角按钮</el-button>
	</div>
</template>
<script type="text/javascript">
	export default{
		name:"Demo2",
		data(){
			return{
				userName:'',
				userCode:'',
				userInfo:''
			};
		},
		create(){},
		methods:{
			_handleClick(){
				let params:{
					userName:this.userName,
					userCode:this.userCode,
					userInfo:this.userInfo
				};
				this.$emit('sendMsg',params)
			}
		},
		mounted:function(){
			this.$nextTick(function(){

			});
		}
	}
</script>