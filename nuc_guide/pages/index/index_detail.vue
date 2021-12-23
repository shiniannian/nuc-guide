<template>
	<view>
		<view class="banner">
			<image class="banner-img" :src="data.photo"></image>
			<view class="banner-title">{{data.title}}</view>
		</view>
		<view class="article-meta">
			<text class="article-author">{{data.title}}</text>
			<text class="article-text">于</text>
			<text class="article-time">{{data.time}}</text>
		</view>
		<view class="article-content">
			<text>{{data.detailContent}}</text>
		</view>
		<view>
			<video class="video" :src="data.video"></video>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				data:{}
			}
		},
		onLoad:function(options){
			this.data = JSON.parse(options.news)
		}
}
</script>

<style>
    .banner {
		height: 360rpx;
		overflow: hidden;
		position: relative;
		background-color: #ccc;
	}

	.banner-img {
		width: 100%;
	}

	.banner-title {
		max-height: 84rpx;
		overflow: hidden;
		position: absolute;
		left: 30rpx;
		bottom: 30rpx;
		width: 90%;
		font-size: 32rpx;
		font-weight: 400;
		line-height: 42rpx;
		color: white;
		z-index: 11;
	}

	.article-meta {
		padding: 20rpx 40rpx;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		color: gray;
	}

	.article-text {
		font-size: 26rpx;
		line-height: 50rpx;
		margin: 0 20rpx;
	}

	.article-author,
	.article-time {
		font-size: 30rpx;
	}

	.article-content {
		padding: 0 30rpx;
		overflow: hidden;
		font-size: 30rpx;
		margin-bottom: 30rpx;
	}
	.video{
		width: 100%;
	}
</style>
