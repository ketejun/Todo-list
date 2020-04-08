<template>
	<div id="content">
		<ul class="todo-content">
			<li :key="index" v-for='(item,index) in msg'>
				<span v-show="editIndex == index">
					<input type="text" 
					@keyup.esc="disEdit(item,index)" 
					@keyup.enter="editItem(item,index)" 
					class="text" 
					v-model="tempTitle"
					v-focus="editIndex == index"
					>
				</span>
				<span v-show="editIndex != index">
					<input type="checkbox" class="chb" v-model="item.done">
					<span class="text" v-on:dblclick="toEdit(item,index)">{{item.title}}</span>
					<button class="btn" v-on:click="deleteTodo(index)">删除</button>
				</span>
			</li>
			<div><span>已经完成({{doneList.length}})</span></div>
		</ul>
	</div>
</template>

<script>
	import bus from '../js/bus.js';

	export default {
		name: 'Content',
		data: function(){
			return {
				msg: [
					// {
					// 	title: 'goodstudy',
					// 	done: false
					// },
					// {	
					// 	title: 'daydayup',
					// 	done: false
					// }
				],
				editIndex: null,
				tempTitle: null
			}
		},
		directives: {
			focus: function(el,data){
				if (data.value) {
					el.focus();
				}
			}
		},
		methods: {
			// 删除
			deleteTodo: function(num){
				this.msg.splice(num,1);
			},

			// 双击编辑
			toEdit: function(item,index){
				// console.log(item,index);
				this.editIndex = index;
				this.tempTitle = item.title;
			},

			// 按键回车
			editItem:function(item,index){
				item.title = this.tempTitle;
				this.tempTitle = '';
				this.editIndex = null;
			},
			// esc键回撤
			disEdit: function(item,index){
				this.tempTitle = '';
				this.editIndex = null;
			}
		},
		computed: {
			doneList: function(){
				return this.msg.filter(item => item.done);
			}
		},
		mounted: function(){
			bus.$on('con-text', (val) => {
				// this.msg.unshift(val);
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
		height: 40px;
		line-height: 40px;
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