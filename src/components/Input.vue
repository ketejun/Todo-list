<template>
	<div class="inpt">
		<input type="text" v-on:keyup.enter="handlAdd" v-model="info" placeholder="what's to do?" id="textId">
	</div>
</template>

<script>
	import bus from '../js/bus.js';
	export default {

		name: 'Input',
		data: function(){
			return {
				info: '',
				// list: {
				// 	// title:'',
				// 	// done: false
				// }
				list: [
					// {
					// 	title: 'goodstudy',
					// 	done: false
					// },
					// {	
					// 	title: 'daydayup',
					// 	done: false
					// }
				]
			}
		},
		methods: {
			// 添加
			handlAdd: function(){
				if (this.info != '') {
					this.list.unshift({title:this.info, done: false});
					// this.list.title = this.info;		
					bus.$emit('con-text',this.list);

					// console.log(this.list.title,this.list.done);
					this.info = '';
				}
			}
		}
	}
</script>

<style>
	.inpt {
		text-align: center;
	}
	#textId {
		border: none;
		outline: none;
		width: 25%;
		min-width: 200px;
		height: 36px;
		margin-top: 20px;
		font-size: 22px;
		color: #000;
		padding-left: 20px;
		box-shadow: 0 0 10px #ccc;
	}
</style>