<template>
	<view>
		<view class="content_title">
			<h2>孩子们在一起拼插积木，锻炼动手能力,开发智力</h2>
			<view class="date">
				<text>2019-09-08</text>
			</view>
			
			<view class="content_image">
				<image src="../../../../static/index_1.jpg" mode="aspectFill"></image>
			</view>
		</view>
		<view class="content_main">
			<p>
孩子们最高兴的事和最不高兴的事，不是我们成人能想象到的，在我们眼里微不足道的小事，在孩子的心理就是大事，看看孩子们最高兴和最不高兴的是什么？对我们的教育是不是有一些启迪呢？让我们分享一下孩子们的感受吧！</p>
			<p>最高兴的事

　　和许多小朋友玩。

　　玩大型玩具、和小朋友做游戏，跳舞给爸爸妈妈看。

　　学习画画、和小朋友在一起捉虫子；六一学习跳舞、演出。

　　帮老师干活、和小朋友做游戏。

　　和小朋友一起玩，非常高兴。

　　大班六一儿童节。

　　认识好多朋友。大家一起玩，六一大家一起跳舞。

　　在幼儿园玩大型玩具很开心。

　　那天到爱地老人院给爷爷奶奶们唱歌、跳舞非常高兴。因为我们给爷爷奶奶带来了开心和欢乐，所以我感到高兴。</p>
		</view>
		<view class="pl">
			<view class="dz">
				<image src="../../../../static/zan.png" mode="aspectFill"></image>
				<text>已点赞225</text>
			</view>
			<view class="fx">
				<image src="../../../../static/share.png" mode="aspectFill"></image>
				<text>分享给朋友</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.content_title{
		width:100%;
		display: flex;
		justify-content: center;
		flex-direction: column;
		padding:20upx;
	}
	.content_title h2{
		width:100%;height:80upx;
		line-height: 80upx;
		font-size: 32upx;
		text-align: center;
	}
	.content_title .date{
		text-align: right;
		padding-right:26upx;
		font-size: 26upx;
		color:#CCCCCC;
	}
	.content_title image{
		width:100%;height:400upx;
		margin:20upx auto;
	}
	.content_main{
		width:100%;height:780upx;
		padding:20upx;
	}
	.pl{
		width:100%;height:120upx;
		display: flex;
		justify-content: space-between;
		flex-direction: row;
		align-items: center;
	}
	.pl view{
		width:50%;height:100upx;
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items:center;
	}
	.pl view image{
		width:50upx;height:50upx;
	}
</style>
