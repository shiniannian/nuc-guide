<template>
	<view>
		<view class="banner">
			<image class="banner-img" src="../../../static/iocn/news-detail1.jpg"></image>
			<view class="banner-title">校长熊继军到招生录取现场慰问与调研</view>
		</view>
		<view class="article-meta">
			<text class="article-author">所念皆星河</text>
			<text class="article-text">发表于：</text>
			<text class="article-time">2021年08月05日</text>
		</view>
		<view class="article-content">
			<text>
				8月5日下午，校长熊继军一行到招生录取现场慰问并调研本科招生工作。
			招就处处长李博详细汇报了今年各省的招生情况。截止目前，我校已高质量且顺利完成31个省市自治区的全部本科招生任务，生源质量明显好于去年，共计录取8896人。录取通知书即将全部寄出。
			熊继军要求，要认真总结今年的招生情况，切实做好数据统计与分析，同时认真总结近几年招生工作的开展情况，为下一步更好地开展工作提供借鉴与支撑。他同时对暑期坚守岗位的工作人员表示亲切慰问，希望大家再接再厉，给今年的招生录取工作画上圆满的句号。
			</text>
		</view>
	</view>
</template>

<script>

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
</style>
