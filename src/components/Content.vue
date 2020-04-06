<template>
	<div id="content">
		<ul class="todo-content">
			<li>
				<input type="checkbox" class="chb">
				<span class="text">好好学习，天天向上</span>
				<button class="btn">删除</button>
			</li>
			<li>
				<input type="checkbox" class="chb">
				<span class="text">好好学习，天天向上</span>
				<button class="btn">删除</button>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'Content',
		data: function(){
			return {

			}
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
		/*text-align: center;*/
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
		font-size: 22px;
		margin: 0 50px;
	}
	.todo-content li .btn {
		position: absolute;
		top: 50%;
		right: 10px;
		transform: translateY(-50%);
	}
</style>