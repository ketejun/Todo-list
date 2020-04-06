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
				arr: []
			}
		},
		methods: {
			handlAdd: function(){
				if (this.info != '') {
					this.arr.push(this.info);
					this.info = '';
					bus.$emit('con-text',this.arr);
				}
				// console.log(this.arr);
				
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