<template>
	<div id="content">
		<ul class="todo-content">
			<li v-for='(item,index) in msg'>
				<input type="checkbox" class="chb" :disabled="flag" v-on:click="selected">
				<span class="text">{{item}}</span>
				<button class="btn" v-on:click="deleteTodo(index)">删除</button>
			</li>
		</ul>
	</div>
</template>

<script>
	import bus from '../js/bus.js';

	export default {
		name: 'Content',
		data: function(){
			return {
				msg: [],
				flag: false
			}
		},
		methods: {
			deleteTodo: function(num){
				this.msg.splice(num,1);
			},
			selected: function(){
				this.flag != this.flag;
			}
		},
		mounted: function(){
			bus.$on('con-text', (val) => {
				this.msg = val;
			})
		}
	}
</script>

<style>
	#content {
		width: 33.3%;
		min-width: 360px;
		margin: 20px auto;
		/*background-color: pink;*/
	}

	.todo-content {
		margin: 0;
		padding: 0;
		list-style: none;
		
	}
	.todo-content li {
		position: relative;
		height: 46px;
		line-height: 44px;
		margin-bottom: 10px;
		/*background-color: #ccc;*/
		box-shadow: 0 0 10px #ccc;
	}

	.todo-content li .chb {
		position: absolute;
		top: 50%;
		left: 10px;
		transform: translateY(-50%);
	}
	.todo-content li .text {
		display: inline-block;
		width: 70%;
		font-size: 22px;
		margin: 0 50px;
		overflow: hidden;
		white-space: nowrap;
		text-overflow:ellipsis;
	}
	.todo-content li .btn {
		position: absolute;
		top: 50%;
		right: 10px;
		transform: translateY(-50%);
	}
</style>