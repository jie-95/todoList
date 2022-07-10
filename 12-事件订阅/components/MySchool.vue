<template>
	<div class="school">
		<h2>学校名称：{{name}}</h2>
		<h2>学校地址：{{address}}</h2>
	</div>
</template>

<script>
	import pubsub from 'pubsub-js'
	export default {

		name:'MySchool',
		data() {
			return {
				name:'尚硅谷',
				address:'北京',
			}
		},
		mounted(){
			//console.log('MySchool',this);
				this.pubid = pubsub.subscribe('hello', (msg,data)=>{
				console.log('有人触发了HELLO事件',msg,data);
			})
		},
		methods:{
			sendStudentName(){
			pubsub.unsubscribe('pubid')	
			}
		}
			
	}
</script>

<style scoped>
	.school{
		background-color: skyblue;
		padding: 5px;
	}
</style>