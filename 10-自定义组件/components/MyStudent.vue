<template>
	<div class="student">
		<h2>学生姓名：{{name}}</h2>
		<h2>学生性别：{{sex}}</h2>
		<h2>当前求和为：{{number}}</h2>
		<button @click="sendStudentlName">把学生给App</button>
		<button @click="unbind">解绑自定义事件</button>
		
	</div>
</template>

<script>
	export default {
		name:'MyStudent',
		data() {
			return {
				name:'张三',
				sex:'男',
				number:0
			}
		},
		methods:{
			sendStudentlName(name){
				// console.log(this);
				this.$emit('atguigu',name)
				this.$emit('deemo')
			},
			unbind(){
				//this.$off(['deemo','atguigu'])//解绑的事件要写在数组里
				this.$off()//不传参 ， 解绑所有自定义事件
			}
		}
		
	}
</script>

<style scoped>
	.student{
		background-color: pink;
		padding: 5px;
		margin-top: 30px;
	}
</style>
