<template>
	<div>
		<ul>
			<li v-for="(item,index) in lists" @click="choose(index)" :class="{active:index == current && current !== ''}" :key="index">
				{{item}}
			</li>
		</ul>
		<button type="button" @click="add()">添加</button>
		<ul>
			<li v-for="(item,index) in target" :key="index">{{item}}</li>
		</ul>
	</div>
</template>

<script>
	export default{
		name:"index",
		data(){
			return{
				current:'',
				lists:["奶茶","咖啡","可乐","龙井","普洱","果汁","炒粉","粽子","炒饭"],
				target:[]
			}
		},
		methods:{
			choose(index){
				this.current = index;
				console.log(index);
			},
			add(){
				if(this.current === ''){return}
				this.target.push(this.lists[this.current])
				this.current = ''
			}
		}
	}	
//	var app4 = new Vue({
//		el: '#app4',
//		data:{
//			todos:[
//				{text:'学习Vue'},
//				{text:'做好毕业设计'},
//				{text:'找份好工作'}
//			]
//		}
//	})
</script>

<style scoped>
li.active{
	background: green;
}
li{
	text-align: left;
	font-size: 28px;
}
</style>