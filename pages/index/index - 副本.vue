<template>
	<view>
		<button @click="flag=!flag">
			<text class="icon" v-if="flag">&#xe633;</text>
			<text class="icon" v-else>&#xe634;</text>
		</button>
		<button>
			<text class="icon">&#xe635;</text>
		</button>
		<button>
			<text class="icon">&#xe63a;</text>
		</button>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				flag: false,
			}
		}
	}
</script>
<style>
	.icon {
		font-size: 50rpx;
		color: #0055ff;
		font-family: iconfont;
	}
	button {
		display: flex;
		align-items: center;
		justify-content: center;
	}
</style>
