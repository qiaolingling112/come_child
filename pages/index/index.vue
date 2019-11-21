<template>
		<view class="bananer-page">
			<image src="../../static/banner.jpg"  @tap="gotoLogin()"></image>
		</view>
</template>
<script>
	var _self;
	export default{
		data(){
			return{
				
			}
		},
		onLoad() {
			_self = this;
			setTimeout(function() {
				_self.gotoLogin();
			}, 3000);
		},
		methods:{
			gotoLogin() {
				uni.navigateTo({
					url: 'choice/choice'
				});
			}
		}
	}
</script>
<style>
	.bananer-page image {
		position: absolute;
		z-index: 10;
		left: 0;
		right: 0;
		top: 0;
		bottom: 0;
		width: 100%;
		height: 100%;
		display: block;
		overflow: hidden;
		z-index: 20;
	}
</style>