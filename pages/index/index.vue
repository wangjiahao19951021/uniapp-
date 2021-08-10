<template>
	<view>
		<!-- 轮播图 -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="200" style="width: 100%; height: 250rpx;">
			<swiper-item v-for="i of 6">
				<image :src="'/static/banner/OIP-C%20(' + i + ').jpg'" style="width: 100%; height: 100%;"></image>
			</swiper-item>
		</swiper>
		
		<!-- 列表 -->
		<view class="" style="display: flex; flex-wrap: wrap; padding-bottom: 50rpx;">
			<view class="" style="width: 375rpx;padding: 5rpx; box-sizing: border-box; position: relative;" v-for="i of 6" @click="openLive">
				<image :src="'/static/banner/OIP-C%20(' + i + ').jpg'" style="width: 365rpx; height: 365rpx; border-radius: 5rpx;"></image>
				<view style="border-radius: 50rpx; position: absolute; left: 15rpx; top: 15rpx; background-color: rgba(0, 0, 0, 0.4); display: flex; align-items: center; padding: 0 20rpx;  height: 50rpx;">
					<text class="icon">&#xe633</text>
					<text style="color: #FFFFFF; margin-left: 5rpx;">0</text>
				</view>
				<view style="border-radius: 50rpx; position: absolute; right: 15rpx; top: 15rpx; background-color: rgba(0, 0, 0, 0.4); display: flex; align-items: center; padding: 0 20rpx; height: 50rpx;">
					<text style="color: #FFFFFF;">人气</text>
					<text style="color: #FFFFFF; margin-left: 5rpx;">0</text>
				</view>
				<view style="border-radius: 50rpx; position: absolute; left: 15rpx; bottom: 15rpx; background-color: rgba(0, 0, 0, 0.4); display: flex; align-items: center; padding: 0 20rpx; height: 50rpx;">
					<text style="color: #FFFFFF;">标题{{i}}</text>
					<text style="color: #FFFFFF; margin-left: 5rpx;"></text>
				</view>
				<view style="border-radius: 50rpx; position: absolute; right: 15rpx; bottom: 15rpx; background-color: rgba(0, 0, 0, 0.4); display: flex; align-items: center; padding: 0 20rpx; height: 50rpx;">
						<text class="icon" style="color: #ff0000;">&#xe639;</text>
						<text style="color: #FFFFFF; margin-left: 5rpx;">已结束</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				flag: false,
			}
		},
		methods: {
			openLive() {
				uni.navigateTo({
					url: "/pages/live/live"
				})
			}
		}
	}
</script>
<style>
	.icon {
		font-size: 40rpx;
		color: #ffff00;
		font-family: iconfont;
	}
	button {
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
</style>
