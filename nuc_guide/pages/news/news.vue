<template>
	<view class="news">
		<view class="news_item" @click="goDetail1">
			<image src="../../static/iocn/news-detail1.jpg"></image>
			<view class="right">
				<view class="tit">
					校长熊继军到招生录取现场慰问与调研
				</view>
				<view class="info">
					<text>发表时间：2021年08月05日</text>
					<text>浏览：2411</text>
				</view>
			</view>
		</view>
		<view class="news_item" @click="goDetail2">
			<image src="../../static/iocn/news-detail2.jpg"></image>
			<view class="right">
				<view class="tit">
					我校与大同市新荣区签署省校合作框架协议
				</view>
				<view class="info">
					<text>发表时间：2021年08月06日</text>
					<text>浏览：1851</text>
				</view>
			</view>
		</view>
		<view class="news_item" @click="goDetail3">
			<image src="../../static/iocn/news-detail3.jpg"></image>
			<view class="right">
				<view class="tit">
					金奖及奖牌总数居首位！我校在第七届山西省“互联网+”大学生创新创业大赛获佳绩
				</view>
				<view class="info">
					<text>发表时间：2021年08月04日</text>
					<text>浏览：853</text>
				</view>
			</view>
		</view>
		<view class="news_item" @click="goDetail4">
			<image src="../../static/iocn/news-detail4.png"></image>
			<view class="right">
				<view class="tit">
					我校8项科技成果荣获山西省科学技术奖
				</view>
				<view class="info">
					<text>发表时间：2021年08月04日</text>
					<text>浏览：1932</text>
				</view>
			</view>
		</view>
		<view class="news_item" @click="goDetail5">
			<image src="../../static/iocn/news-detail5.jpg"></image>
			<view class="right">
				<view class="tit">
					第二十一届全国运动生物力学学术交流大会在我校举办
				</view>
				<view class="info">
					<text>发表时间：2021年08月04日</text>
					<text>浏览：842</text>
				</view>
			</view>
		</view>
		<view class="news_item" @click="goDetail6">
			<image src="../../static/iocn/news-detail6.jpg"></image>
			<view class="right">
				<view class="tit">
					我校李红霞老师在首届全国高校教师教学创新大赛中荣获三等奖
				</view>
				<view class="info">
					<text>发表时间：2021年08月04日</text>
					<text>浏览：853</text>
				</view>
			</view>
		</view>
		<view class="news_item" @click="goDetail7">
			<image src="../../static/iocn/empty.png"></image>
			<view class="right">
				<view class="tit">
					关于2021年秋季学期学生返校及新生报到有关安排的通知
				</view>
				<view class="info">
					<text>发表时间：2021年08月20日</text>
					<text>浏览：1182</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		methods:{
			goDetail1(){
				uni.navigateTo({
					url:"news-detail/news-detail1" 
				})
			},
			goDetail2(){
				uni.navigateTo({
					url:"news-detail/news-detail2" 
				})
			},
			goDetail3(){
				uni.navigateTo({
					url:"news-detail/news-detail3" 
				})
			},
			goDetail4(){
				uni.navigateTo({
					url:"news-detail/news-detail4" 
				})
			},
			goDetail5(){
				uni.navigateTo({
					url:"news-detail/news-detail5" 
				})
			},
			goDetail6(){
				uni.navigateTo({
					url:"news-detail/news-detail6" 
				})
			},
			goDetail7(){
				uni.navigateTo({
					url:"news-detail/news-detail7" 
				})
			}
			
		}
	}
</script>

<style lang="scss">
	.news{
		.news_item{
			display: flex;
			padding: 10rpx 20rpx;
			border-bottom: 1px solid #C21F39;
			image{
				min-width: 200rpx;
				max-width: 200rpx;
				height: 150rpx;
			}
			.right{
				margin-left: 15rpx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				.tit{
					font-size: 30rpx;
				}
				.info{
					font-size: 24rpx;
					text:nth-child(2){
						margin-left: 30rpx;
					}
				}
			}
		}
	}
</style>
