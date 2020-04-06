<template>
	<div class="header">
		<span>{{msg}}</span>
	</div>
</template>

<script>
	export default {
		name: 'Header',
		data: function(){
			return {
				msg: 'Todo-list'
			}
		}
	}
</script>

<style>
	.header {
		width: 100%;
		height: 100px;
		background-color: #03031B;
		text-align: center;
		color: #fff;
		line-height: 100px;
		font-size: 28px;
		font-weight: bold;
	}
</style>