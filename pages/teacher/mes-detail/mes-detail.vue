<template>
	<view>
		<uni-swiper-dot :info="info" :current="current" :mode="mode" field="content">
			<swiper class="swiper-box" @change="change">
				<swiper-item>
					<view class="swiper-item">
						<table class="mes">
								<tr>
								<th>姓名:</th>
								<td>李雷</td>
								</tr>
								<tr>
									<th>性别:</th>
									<td>男</td>
								</tr>
								<tr>
									<th>年龄:</th>
									<td>3</td>
								</tr>
								<tr>
									<th>身高:</th>
									<td>98</td>
								</tr>
								<tr>
									<th>体重:</th>
									<td>35</td>
								</tr>
								<tr>
									<th>监护人姓名:</th>
									<td>李雷</td>
								</tr>
								<tr>
									<th>关系:</th>
									<td>爹</td>
								</tr>
								<tr>
									<th>手机号:</th>
									<td>18234355453</td>
								</tr>
						</table>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<table class="mes">
							<tr>
							<th>姓名:</th>
							<td>李雷</td>
							</tr>
							<tr>
								<th>性别:</th>
								<td>男</td>
							</tr>
							<tr>
								<th>年龄:</th>
								<td>3</td>
							</tr>
							<tr>
								<th>身高:</th>
								<td>98</td>
							</tr>
							<tr>
								<th>体重:</th>
								<td>35</td>
							</tr>
							<tr>
								<th>监护人姓名:</th>
								<td>李雷</td>
							</tr>
							<tr>
								<th>关系:</th>
								<td>爹</td>
							</tr>
							<tr>
								<th>手机号:</th>
								<td>18234355453</td>
							</tr>
						</table>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<table class="mes">
							<tr>
							<th>姓名:</th>
							<td>李雷</td>
							</tr>
							<tr>
								<th>性别:</th>
								<td>男</td>
							</tr>
							<tr>
								<th>年龄:</th>
								<td>3</td>
							</tr>
							<tr>
								<th>身高:</th>
								<td>98</td>
							</tr>
							<tr>
								<th>体重:</th>
								<td>35</td>
							</tr>
							<tr>
								<th>监护人姓名:</th>
								<td>李雷</td>
							</tr>
							<tr>
								<th>关系:</th>
								<td>爹</td>
							</tr>
							<tr>
								<th>手机号:</th>
								<td>18234355453</td>
							</tr>
						</table>
					</view>
				</swiper-item>
			</swiper>
		</uni-swiper-dot>
		<view class="btn">
			<button type="default" size="default" class="ok" @tap="arg">通过</button>
			<button type="default" size="default" class="no" @tap="con">拒绝</button>
		</view>
	</view>
</template>

<script>
	import uniSwiperDot from '@/components/uni-swiper-dot/uni-swiper-dot.vue'
	export default{
		components: {
			uniSwiperDot
		},
		data(){
			return {
				modeIndex: -1,
				styleIndex: -1,
				current: 0,
				mode: 'default',
				dotsStyles: {},
				info:[],
				detailList:[]
			}
		},
		onLoad() {
		/*	uni.request({
				url:"http://localhost/childDetail",
				method:"GET",
				data:{stat:true},
				success:result=>{
					console.log(result.data.data);
					this.detailList.push(result.data.data)
					console.log(this.detailList);
				},
				fail:result=>{
					console.log(result)
				}
			})*/
		},
		methods: {
			change(e) {
				this.current = e.detail.current
			},
			con(){
				uni.showModal({
					title:"确认要拒绝吗？"
				})
			},
			arg(){
				uni.showToast({
					title:'提交成功',
					icon:'success'
				})
			}
		},
		
	}
</script>

<style>
	.swiper-box {
		height: 800upx;
	}
	.swiper-item {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100%;
		background: #fff;
		color: #fff;
	}
	.swiper-item .mes{
		font-size:24upx;
		color:#000;
		border:2upx solid #000;
		border-radius: 16upx;
		width:500upx;height:500upx;
		text-align: center;
	}	
	.swiper-item image {
		height: 100%;width: 100%;
	}
	.btn{
		width:100%;
	}
	.btn .ok{
		width:80%;
		float:left;
		background: #F0AD4E;
		color:#fff;
	}
	.btn .no{
		width:20%;
		float:left;
		background:red;
		color:#fff;
	}
</style>
