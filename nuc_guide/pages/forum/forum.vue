<template>
	<view>
		
		<!-- 分类具体的内容 -->
		<view class="sort-content">
		    <block v-for="(item,index) in 5" :key="index"> 
		        <view class="sort-content-item">
		            <view class="sort-content-top" >
		                <!-- 用户信息（头像、用户名等） -->
		                <view class="user-info">
		                    <view class="user-photo">
		                        <image src="../../static/anonymous.png" mode="widthFix"></image>
		                    </view>
		                    <view class="user-detail">
		                        <view class="user-name">
		                            <text>匿名用户</text>
		                        </view>
		                        <view class="user-flag">
		                            <view class="article-sort">闲置交易</view>
		                            <view class="user-sex">小姐姐</view>
		                            <view class="user-level">Lv20</view>
		                        </view>
		                    </view>
		                    <view class="post-detail">
		                        <view class="handle">
		                            <image src="../../static/more.png"></image>
		                        </view>
		                        <view class="post-time">
		                            <text>2021-08-28 08:30</text>
		                        </view>
		                        
		                    </view>
		                </view>
		            </view>
		            <!-- 帖子内容 -->
		            <view class="sort-content-middle">
		                <view class="acticle-text">
		                    <text>点点繁星挂在苍穹之上，星光泻下落在了人们头上，他们带着星光在太行山上勇敢投身，危难过后这个民族浴火重生。</text>
		                </view>
		                <view class="acticle-image">
		                    <block v-for="(item,index) in testImage" :key="index">
		                        <view class="show-image">
		                            <image :src="item" mode="aspectfill"></image>
		                        </view>
		                    </block>
		                </view>
		            </view>
		            <view class="sort-content-bottom">
		                <view class="like">
		                    <image src="../../static/like.png" class="bottom-img"></image>
		                    <text class="num">99</text>
		                </view>
		                <view class="comment">
		                    <image src="../../static/comment.png" class="bottom-img"></image>
		                    <text class="num">99</text>
		                </view>
		               
		            </view>
		        </view>
		    </block>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				testImage:[
				  '../../static/iocn/news-detail1.jpg',
				  '../../static/iocn/news-detail2.jpg',
				  '../../static/iocn/news-detail3.jpg',
				  '../../static/iocn/news-detail4.jpg',
				  '../../static/iocn/news-detail5.jpg',
				  '../../static/iocn/news-detail6.jpg',
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	/* 分类具体内容 */
	.sort-content{
	  
	  justify-content: center;
	  margin: auto;
	  margin-top: 10rpx;
	  
	
	}
	.sort-content-item{
	  
	  padding-bottom: 20rpx;
	  border-bottom: 5rpx rgb(240, 242, 243) solid ;
	}
	.user-info{
	  width: 88%;
	  margin: auto;
	  margin-top: 10rpx;
	  display: flex;
	  flex-direction: row;
	  justify-content: space-between;
	  padding: 10rpx;
	}
	
	.user-photo{
	  display: flex;
	  flex-direction: row;
	  justify-content: center;
	}
	
	.user-info image{
	  width: 100rpx;
	  border-radius: 50%;
	}
	
	.user-detail{
	  display: flex;
	  flex-direction: column;
	  flex-grow: 2;
	  justify-content: space-between;
	  margin-left: 10rpx;
	}
	
	.user-name{
	  font-weight: 800;
	  color: cadetblue;
	}
	
	.user-flag{
	  display: flex;
	  flex-direction: row;
	}
	
	.user-flag view{
	  font-weight: 100;
	  color: white;
	  font-size: 20rpx;
	  margin-right: 10rpx;
	  padding: 5rpx;
	  border-radius: 4rpx;
	}
	
	.article-sort{
	  background-color: burlywood;
	}
	
	.user-sex{
	  background-color: chocolate;
	}
	
	.user-level{
	  background-color: cornflowerblue;
	}
	
	.sort-content-middle{
	  width: 88%;
	  margin: auto;
	  padding: 10rpx;
	  text-align: center;
	}
	
	.acticle-text{
	  word-wrap: break-word;
	  font-size: 30rpx;
	  display: -webkit-box;
	  text-align: left;
	  overflow: hidden;
	  margin-left: 7rpx;
	   text-align: center; 
	  -webkit-line-clamp: 6;
	  -webkit-box-orient: vertical;
	  letter-spacing: 5rpx;
	}
	
	.acticle-image{
	  display: flex;
	  flex-direction: row;
	  flex-wrap: wrap;
	  align-items: center;
	}
	
	.show-image{
	  width: 28vw;
	  height: 28vw;
	  margin: 7rpx 8rpx 7rpx 2rpx;
	}
	
	.show-image image{
	  display: inline-block;
	  width: 100%;
	  height: 100%;
	  margin: 5rpx;
	  border-radius: 10rpx;
	}
	
	/* 更多 */
	.post-detail{
	  display: block;
	  width: 200rpx;
	}
	.handle{
	  padding-left: 170rpx;
	}
	.handle image{
	  
	  width: 35rpx;
	  height: 35rpx;
	  text-align: right;
	}
	.post-time{
	  display: block;
	  float: right;
	}
	
	.post-time text{
	  font-size: 22rpx;
	  color: #a09c9c;
	}
	
	
	/* 底部评论等 */
	.bottom-img{
	  width: 35rpx;
	  height: 35rpx;
	  vertical-align: middle;
	}
	
	.sort-content-bottom{
	  height: 52rpx;
	  width: 90%;
	  display: flex;
	  align-content: center;
	  margin: auto;
	  justify-content: flex-end;
	}
	
	.comment{
	  margin-left: 20rpx;
	  line-height: 52rpx;
	}
	
	.like{
	  line-height: 52rpx;
	}
	
	
	.num{
	  padding-left: 6rpx;
	  font-size: 25rpx;
	}
</style>
