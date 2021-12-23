<template>
	<view class="index-content">
		<map class="map" :longitude="longitude" :latitude="latitude"
		      :markers="markers" :scale="scale"></map>
		
		<view class="top-bar">
			<text class="top-title">共有10个地点</text>
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
									<view class="time">{{news.time}}</view>
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
		data() {
			return {
				//地图的数据
				longitude:112.453582,
				latitude: 38.02132,
				scale:13,
				markers:[
					//东区篮球场
					{
						longitude:112.4527,
						latitude: 38.01571,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//一号楼
					{
						longitude:112.45088,
						latitude: 38.0155,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//十四号楼
					{
						longitude:112.45385,
						latitude: 38.0154,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//十号楼
					{
						longitude:112.45537,
						latitude: 38.01595,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//文涛餐厅
					{
						longitude:112.4552,
						latitude: 38.01723,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//科学楼
					{
						longitude:112.45103,
						latitude: 38.01797,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//瑾瑜国际会议中心
					{
						longitude:112.45033,
						latitude: 38.01745,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//十一号楼
					{
						longitude:112.4494,
						latitude: 38.01561,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//图书馆
					{
						longitude:112.44785,
						latitude: 38.01582,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					}
				],
				
				//景点信息
				newsList:[
					{"title":"一号楼","content":"中北大学的一号楼","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/一号楼.jpg","video":"/static/一号楼.mp4"},
					{"title":"东区篮球场","content":"中北大学最大的篮球场","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/东区篮球场.jpg","video":"/static/东区篮球场.mp4"},
					{"title":"十四号楼","content":"中北大学的十四号楼","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/十四号楼.jpg","video":"/static/十四号楼.mp4"},
					{"title":"广顺超市","content":"中北大学的广顺超市","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/广顺超市.jpg","video":"/static/广顺超市.mp4"},
					{"title":"十号楼","content":"中北大学的十号楼","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/十号楼.jpg","video":"/static/十号楼.mp4"},
					{"title":"文涛餐厅","content":"中北大学的文涛餐厅","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/文涛餐厅.jpg","video":"/static/文涛餐厅.mp4"},
					{"title":"科学楼","content":"中北大学的科学楼","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/科学楼.jpg","video":"/static/科学楼.mp4"},
					{"title":"瑾瑜国际会议中心","content":"中北大学的会议中心","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/瑾瑜国际会议中心.jpg","video":"/static/瑾瑜国际会议中心.mp4"},
					{"title":"十一号楼","content":"中北大学的十一号楼","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/十一号楼.jpg","video":"/static/十一号楼.mp4"},	
					{"title":"图书馆","content":"中北大学的图书馆","time":"1960年建成","detailContent":"啊吧啊吧","photo":"../../static/图书馆.jpg","video":"/static/图书馆.mp4"}
				],
				
			}	
		},
		
		onLoad() {
			
		},
		
		methods: {
			onClick(news){
				uni.navigateTo({
					url:"index_detail?news="+JSON.stringify(news)
				})
			}
		}
	}
</script>

<style lang="scss">
	.content{
			display: flex;
			flex-direction: column;
			//align-items: center;
			justify-content: center;
		}
.map{
	 width: 750rpx;
	 height: 750rpx;
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
