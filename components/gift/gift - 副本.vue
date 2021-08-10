<template>
	<list style="width: 520rpx; height: 500rpx; display: flex; white-space: nowrap; padding-left: 40rpx;" :show-scrollbar="false" :bounce="false">
		<cell style="display: flex; justify-content: flex-start; flex-direction: row; align-items: center; padding-top: 10; padding-bottom: 10;"  v-for="(item, index) of gifts" :key="index" insert-animation="default" delete-animation="default" :ref="'item' + index">
			<view
					style="width: 325rpx; display: flex; background-image: linear-gradient(to right, #BCABB1, #65AAF0); border-radius: 20;justify-content: space-between; height: 80rpx; flex-direction: row; align-items: center; padding-left: 10; padding-right: 10;">
					<view style="">
						<image :src="item.avant_img || defaults_img" style="width: 70rpx; height: 70rpx; border-radius: 100;">
						</image>
					</view>
					<view style="flex: 1; padding-left: 10;">
						<text style="color: #FFFFFF; font-size: 25rpx;">{{item.username}}</text>
						<text style="color: #FFFFFF; font-size: 20rpx;">送{{item.gift_name}}</text>
					</view>
					<view style="">
						<image :src="item.gift_image" style="width: 70rpx; height: 70rpx; border-radius: 100;">
						</image>
					</view>
				</view>
				<text style="color: #ea9518; padding-left: 3;">X {{item.num}}</text>
			</view>
		</cell>
	</list>
</template>

<script>
	const dom = weex.requireModule('dom')
	export default {
		data () {
			return {
				gifts: [],
				defaults_img: "/static/banner/OIP-C%20(6).jpg"
			}
		},
		created () {
			let a = 1;
			setInterval(() => {
				this.gifts.push({
					username: "发送人" + a,
					avant_img: "/static/banner/OIP-C%20(" + Math.floor(Math.random()*6+1) + ").jpg",
					gift_name: "蛋糕",
					gift_image: "/static/gift/gift_" +  Math.floor(Math.random()*4+1) + ".png",
					num: Math.floor(Math.random()*10+1),
				})
				this.toBotton()
				this.autoHide()
				a ++
			}, 2000)
		},
		methods: {
			// 置于底部
			toBotton () {
				this.$nextTick(function(){
					let index = this.gifts.length - 1
					let ref = "item" + index
					if (this.$refs[ref]) {
						dom.scrollToElement(this.$refs[ref][0], {})
					}
				})
			},
			// 自动消失
			autoHide () {
				if (this.gifts.length) {
					let timer = setTimeout(() => {
						this.gifts.splice(0, 1);
					}, 5000)
				}
			}
		}
	}
</script>

<style>
</style>
