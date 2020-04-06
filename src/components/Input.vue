<template>
	<div class="inpt">
		<input type="text" placeholder="what's to do?" id="textId">
	</div>
</template>

<script>
	export default {
		name: 'Input',
		data: function(){
			return {

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