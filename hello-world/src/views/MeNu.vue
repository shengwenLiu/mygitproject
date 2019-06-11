

<template>
	<div>
		<h1>今日新闻</h1>
		<ul>
			<li v-for="(item,index) in pagelists" :key="index">
				{{item.title}}-{{item.content}}
			</li>
		</ul>
	</div>
</template>


<script>
import store from '@/store'
	export default{
		name:"MeNu",
		store,
		computed:{
			pagelists(){
				return store.state.lists
			}
		}
	}
//	Vue.component('todo-item',{
//		props:['todo'],
//		template:'<li>{{todo.text}}</li>'
//	})
//	var app7 = new Vue({
//		el:'#app7',
//		data: {
//			grocerylist:[
//				{id:0,text: '蔬菜'},
//				{id:1,text: '肉类'},
//				{id:2,text: '奶酪'}
//			]
//		}
//	})
</script>

<style scoped>
h1{
	font-family: "微软雅黑";
}
</style>