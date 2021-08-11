<template>
	<view>
		<gal-css-animate
		:animateName="animateName" 
		duration="2s" 
		timingFunction="ease-in">
			<text style="color: #ffaa00; font-size: 30rpx;">我的</text>
		</gal-css-animate>
	</view>
</template>

<script>
	export default {
		data () {
			return {
				animateName: "wobble"
			}
		}
	}
</script>

<style>
</style>
