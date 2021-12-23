<template>
	<view>
		<view class="banner">
			<image class="banner-img" src="../../../static/iocn/news-detail4.png"></image>
			<view class="banner-title">我校8项科技成果荣获山西省科学技术奖</view>
		</view>
		<view class="article-meta">
			<text class="article-author">所念皆星河</text>
			<text class="article-text">发表于：</text>
			<text class="article-time">2021年08月04日</text>
		</view>
		<view class="article-content">
			<text>
					近日，山西省政府印发《关于2020年度山西省科学技术奖励的决定》，对促进我省科学技术进步和经济社会发展作出突出贡献的科学技术人员和组织给予奖励，共授予19个项目一等奖、85个项目二等奖、89个项目三等奖，10家企业获“企业技术创新奖”。本年度我校共获奖8项，其中技术发明一等奖1项、自然科学二等奖4项、技术发明二等奖2项、科技进步三等奖（参与）1项。
					
					2020年度省科学技术奖突出转型发展政策导向，突出科技成果应用导向，突出企业技术创新主体地位，突出科技前沿和自主创新，鼓励和引导全省科学技术工作者自觉肩负起历史赋予的科技创新重任，着力攻克“卡脖子”关键核心技术，努力形成一批标志性重大科技成果，为我省创新驱动高质量转型发展作出了新的更大贡献。
					
					近年来，我校以冲击“双一流”为目标，坚持“面向科技前沿，面向行业企业；重视基础研究，重视成果转化”的工作思路，推进落实《中北大学科技振兴行动计划》，科研成果产出趋好。
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
