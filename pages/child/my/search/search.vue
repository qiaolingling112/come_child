<template>
	<view>
		<view class="example-body">
			<uni-search-bar @confirm="search" @input="input" @cancel="cancel" />
			<view class="" style="margin-bottom: 20px;text-align: left;padding-left:40upx">
				{{ searchVal }}
			</view>
		</view>
		<view class="example-body" @tap="add()">
			<uni-steps :options="list2" :active="active" direction="column" />
		</view>
		<!-- <button type="primary" @tap="change">改变状态</button> -->
	</view>
</template>
<script>
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue'
	import uniSteps from '@/components/uni-steps/uni-steps.vue'
	export default {
		components: {
			uniSearchBar,
			uniSteps
		},
		data() {
			return {
				searchVal: '',
				active:2,
				list2: [{
					title: '表单提交成功',
					desc: '2018-11-11'
				}, {
					title: '表单审核中',
					desc: '2018-11-12'
				}, {
					title: '补充资料（去补充）',
					desc: '2018-11-13'
				}, {
					title: '办理入园手续',
					desc: '2018-11-14'
				}, {
					title: '恭喜您！报名成功！',
					desc: '2018-11-15'
				}]
			}
		},
		methods: {
			search(res) {
				uni.showModal({
					content: '搜索：' + res.value,
					showCancel: false
				})
			},
			input(res) {
				this.searchVal = res.value
			},
			cancel(res) {
				uni.showModal({
					content: '点击取消，输入值为：' + res.value,
					showCancel: false
				})
			},
			change() {
				if (this.active < this.list2.length - 1) {
					this.active += 1
				} else {
					this.active = 0
				}
			},
			add:function(){
				if(this.active==2){
					uni.showModal({
						title:'提示',
						content:'现在去补充资料？',
						confirmText:"现在就去",
						cancelText:"稍后再去",
						success:function(res){
							if(res.confirm){
								uni.navigateTo({
									url:'../../../child/child-supplement/child-supplement'
								})
							}else if(res.cancel){
								console.log("取消")
							}
						}
						
					})
				}
			}
		}
	}
</script>

<style>
	.example-info {
		padding: 30upx;
		color: #3b4144;
		background: #fff
	}

	.search-result {
		margin-top: 10px;
	}
	.example-body {
		padding: 30upx;
		background: #fff
	}
	
	.example-info {
		padding: 30upx;
		color: #3b4144;
		background: #fff
	}
	
	/* button {
		margin: 30upx;
	} */
</style>
