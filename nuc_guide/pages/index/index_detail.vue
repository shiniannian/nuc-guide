<template>
	<view>
		<view class="banner">
			<image class="banner-img" :src="data.photo"></image>
			<view class="banner-title">{{data.title}}</view>
		</view>
		<view class="article-meta">
			<text class="article-author">{{data.title}}</text>
			<text class="article-text">即</text>
			<text class="article-time">{{data.time}}</text>
		</view>
		<view class="article-content">
			<text>{{data.detailContent}}</text>
		</view>
		<view>
			<video class="video" :src="data.video"></video>
		</view>
		
		<view class="top-bar">
			<text class="top-title">请选择终点</text>
		</view>
		
		<view class="main">
			<view class="news">
				<view class="news_item" @tap="onClick(news)" v-for="news in newsList">
					<view class="news_item_l">
						<image :src="news.photo"></image>
					</view>
					<view class="news_item_r">
						<view class="upper">
							<view class="name">{{news.title}}</view>
							<view class="time">编号：{{news.id}}</view>
						</view>
					    <view class="person">{{news.content}}</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				data:{},
				newsList:[]
			}
		},
		onLoad:function(options){
			this.data = JSON.parse(options.news)
			this.newsList = JSON.parse(options.newsList)
		},
		onReady() {
			
		},
		methods:{
			onClick(news){
				uni.navigateTo({
					url:"index_detail2?news="+JSON.stringify(news)+"&data="+ JSON.stringify(this.data)
				})
			}
		}
}
</script>

<style lang="scss">
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
	.top-bar{
			display: flex;
			width: 100%;
			height: 70rpx;
			box-shadow: 0rpx 1rpx 0rpx 0rpx rgba(0,0,0,0.1);
			justify-content: center;
			align-items:center;
		}
	.main{
			padding: 70rpx 32rpx 0;
		}
		.news{
			width: 100%;
			.news_item{
			height: 96rpx;
			padding: 16rpx 0;
			border-bottom: 1rpx solid #F1F1F1;
			.news_item_l{
				position:relative;
				float: left;
				image{
					width: 96rpx;
				 	height: 96rpx;
					border-radius: 50%;
				}
				.tip{
					position: absolute;
					z-index: 100;
					top: -6rpx;
					left: 68rpx;
					min-width: 36rpx;
					height: 36rpx;
					background: rgba(255,93,91,1);
					border-radius: 18rpx;
					line-height: 36rpx;
					text-align: center;
					color: white;
				}
			}
			.news_item_r{
				padding-left: 128rpx;
				//width: 100%;
				.upper{
					height: 50rpx;
					.name{
						float: left;
						font-size: 28rpx;
						font-weight: 400;
						//color:rgba(39,40,50,1);
						font-weight:540;
						line-height: 50rpx;
					}
					.time{
						float: right;
						font-size: 24rpx;
						color: rgba(39,40,50,0.6);
						line-height: 50rpx;
					}
				}
			}
			.person{
				font-size: 24rpx;
				color: rgba(39,40,50,0.6);
				line-height: 40rpx;
			}
		 }
	    }
</style>
