<template>
	<view class="index-content">
		<map class="map" :longitude="longitude" :latitude="latitude"
		      :markers="markers" :scale="scale"></map>
		
		<view class="top-bar">
			<text class="top-title">请选择起点</text>
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
		data() {
			return {
				//地图的数据
				longitude:112.453582,
				latitude: 38.02132,
				scale:13,
				markers:[
					//一号楼
					{
						longitude:112.45088,
						latitude: 38.0155,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//东区篮球场
					{
						longitude:112.45247,
						latitude: 38.01628,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//十四号楼
					{
						longitude:112.45281,
						latitude: 38.01537,
						iconPath:'../../static/landmark.png',
						width:30,
						height:30
					},
					//广顺超市
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
					{"id":1,"title":"一号楼","content":"平平无奇教学楼，新旧更替可自习","time":"慧学楼","detailContent":"修建最早的教学楼，位于十一号楼东侧，十四号楼北侧，九号楼南侧，东区最西面的教学楼，建筑具有年代感，但周围环境清净，也是一处自习的好地方","photo":"../../static/一号楼.jpg","video":"/static/一号楼.mp4"},
					{"id":2,"title":"东区篮球场","content":"篮球爱好者的天堂，还想长高多来这里","time":"篮球场","detailContent":"篮球场地宽阔，正对于十四号楼，夏天会有很多体育性的活动，比如啦啦操大赛，雪花啤酒赞助的篮球赛事等在这里举办","photo":"../../static/东区篮球场.jpg","video":"/static/东区篮球场.mp4"},
					{"id":3,"title":"十四号楼","content":"历史悠久教学楼，夏日悠凉好去处","time":"十四号楼","detailContent":"环境略偏幽静，教室宽广，正对东区篮球场旁边有一个具有很多小吃美食的小卖铺","photo":"../../static/十四号楼.jpg","video":"/static/十四号楼.mp4"},
					{"id":4,"title":"广顺超市","content":"东区复合型超市","time":"广顺","detailContent":"里面除了具有一般性超市规模，还有奶茶店，咖啡店和各种小吃店，但座椅稀少，食品一般打包带回，周围有浴室，炸鸡店，炒饭等，正对于宿舍楼，便利学生","photo":"../../static/广顺超市.jpg","video":"/static/广顺超市.mp4"},
					{"id":5,"title":"十号楼","content":"一个多功能的教学楼，校社联便在此工作","time":"敏学楼","detailContent":"具有民防科技学院、继续教育学院、信息商务学院、校园绿化中心之称，与宿舍楼相邻，便于自习和上课","photo":"../../static/十号楼.jpg","video":"/static/十号楼.mp4"},
					{"id":6,"title":"文涛餐厅","content":"东区的著名餐厅","time":"龙山食堂","detailContent":"东区最大的食堂，共三层，每层都具有特色美食，更有自助火锅等，还有清源书吧里面有麻辣烫，蜜雪冰城可以在里面学习，饮食","photo":"../../static/文涛餐厅.jpg","video":"/static/文涛餐厅.mp4"},
					{"id":7,"title":"科学楼","content":"众多学生在里面做实验，学校高科技大楼之一","time":"科学楼","detailContent":"分A、B、C三座，研究生的实验室基地","photo":"../../static/科学楼.jpg","video":"/static/科学楼.mp4"},
					{"id":8,"title":"瑾瑜国际会议中心","content":"中北大学高端会议场所","time":"瑾瑜","detailContent":"大型学术的活动以及讲座都在这里举办","photo":"../../static/瑾瑜国际会议中心.jpg","video":"/static/瑾瑜国际会议中心.mp4"},
					{"id":9,"title":"十一号楼","content":"与主楼相邻，可谓是建筑最漂亮的教学楼","time":"主楼相邻","detailContent":"十一号楼偏高，环境优美，一般的大型公共课、选修课和活动会在这里进行，一楼旁边还有打印店、文具店、超市和食堂 ","photo":"../../static/十一号楼.jpg","video":"/static/十一号楼.mp4"},	
					{"id":10,"title":"图书馆","content":"学生借阅书籍或自习的地方","time":"图书馆","detailContent":"自习和展览的地方，需要刷一卡通才能进入，馆内有阅读厅，电影院和展览厅，研习会和一些文学社在这里举办活动，整个图书馆分为东西两个部分，内有电梯，自习室众多，学生一般在-1，5，6，7楼自习","photo":"../../static/图书馆.jpg","video":"/static/图书馆.mp4"}
				],
				
			}	
		},
		
		onLoad() {
			
		},
		
		methods: {
			onClick(news){
				uni.navigateTo({
					url:"index_detail?news="+JSON.stringify(news)+"&newsList="+ JSON.stringify(this.newsList)
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
