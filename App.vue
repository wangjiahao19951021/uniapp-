<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			uni.onTabBarMidButtonTap(function(){
				console.log(132)
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import "@/GAL/css/gal.css";
	/*每个页面公共css */
	@font-face {
		font-family: iconfont;
		font-weight: normal;
		font-style: normal;
		src: url('https://at.alicdn.com/t/font_2723555_4nvkukghlfj.ttf?t=1628216496157') format('truetype');
	}
	
	view{
		font-size: 26rpx;
	}
</style>
