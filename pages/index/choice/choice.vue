<template>
	<view class="uni-con">
		<button type="default" @tap="gotoPage(0)">家长</button>
		<button type="default" @tap="gotoPage(1)">园长</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			gotoPage(val) {
				switch (val) {
					case 0:
						uni.switchTab({
							url: "../../child/introduce/introduce"
						})
						break;
					case 1:
						uni.navigateTo({
							url: "../../teacher/teacher"
						})
						break;
					default:
						break;
				}
			}
		}
	}
</script>

<style>
	.uni-con {
		padding-left: 40upx;
		padding-right: 40upx;
		padding-top: 40upx;
		padding-bottom: 40upx;
	}
.uni-con button {
		margin-bottom: 40upx;
	}
</style>
