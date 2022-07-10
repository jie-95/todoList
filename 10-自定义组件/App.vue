<template>
	<div class="app">
		<h1>{{msg}}</h1>

		<MySchool :getSchoolName='getSchoolName'/>

	
		<MyStudent @atguigu="getStudentName" @deemo='m1' @click.native='show'/>
		<!-- <MyStudent ref='student'  /> -->
	</div>
</template>

<script>
	import MyStudent from './components/MyStudent'
	import MySchool from './components/MySchool'

	export default {
		name:'App',
		components:{MySchool,MyStudent},
		data() {
			return {
				msg:'你好啊！',
			
			}
		},
		methods: {
			getSchoolName(name){
				console.log('App收到了学校名',name);
			},
			getStudentName(name){
				console.log('App收到了学生名',name);
			},
			m1(){
				console.log('m1')
			},
			show(){
				alert('132')
			}
			
		},
		mounted(){
			// this.$refs.student.$on('atguigu',this.getStudentName)
		}
	}
</script>

<style scoped>
	.app{
		background-color: gray;
		padding: 5px;
	}
</style>
