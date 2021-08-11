<template>
	<view style="position: fixed; top: 200rpx;right: 0; width: 520rpx; height: 500rpx;">
		<scroll-view scroll-y="true" style="width: 520rpx; height: 500rpx;" scroll-with-animation :scroll-into-view="scrollInToview">
			<view :id="'danmu' + item.id" style="display: flex; justify-content: flex-start; align-items: center;flex-direction: row; background-color: rgba(255,255,255, 0.2);border-radius: 20rpx; padding-left: 20rpx; padding-top: 10rpx; padding-bottom: 10rpx; margin-bottom: 25rpx;" v-for="(item, index) of list">
				<text style="color: #DD524D; font-size: 30rpx;">{{item.username}}</text>
				<text style="color: #FFFFFF; font-size: 30rpx; padding-left: 20rpx; table-layout: fixed;">{{item.text}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	const dom = weex.requireModule('dom')
	export default {
		data () {
			return {
				scrollInToview: "",
				list: []
			}
		},
		methods: {
			// 弹幕更新
			send (danmu) {
				// this.list.push(danmu)
				this.list = danmu
				this.bottom()
				// this.autoHide()
			},
			// 置于底部
			bottom () {
				setTimeout(() => {
					let len = this.list.length
					if (len > 0 && this.list[len - 1]) {
						this.scrollInToview = 'danmu' + this.list[len - 1].id
					}
				}, 200)
			},
			// 自动消失
			// autoHide () {
			// 	if (this.list.length) {
			// 		let timer = setTimeout(() => {
			// 			this.list.splice(0, 1);
			// 		}, 5000)
			// 	}
			// }
		}
	}
</script>

<style>
</style>
