<template>
<view class="content">
    <!-- 个人信息 -->
  <view class="top">
    <view class="user-info">
        <view class="user-photo">
            <image src="../../static/anonymous.png"></image>
        </view>
        <!-- 用户名、标签 -->
        <view class="user-tag">
            <view class="user-name">
                <text>所念皆星河</text>
            </view>
            <view class="user-flag">
                <view class="identity">学生认证</view>
                <view class="level">Lv2</view>
            </view>
        </view>

        <view class="grow-up">
            <view class="process">
                <image src="../../static/Sign.png"></image>
                <view class="sign">
                    <button size="mini">签到</button>
                </view>
            </view>
            <view class="grades">
                <view class="exp">当前经验：800</view>
                <view class="exp">距离下一等级还需：100</view>
            </view>
        </view>
    </view>

    <!-- 内容分类 -->
    <view class="user-detail">
        <view class="tpye">
            <view class="type-name">收藏</view>
            <view class="type-num">0</view>
        </view>
        <view class="tpye">
            <view class="type-name">浏览历史</view>
            <view class="type-num">666</view>
        </view>
    </view>
  </view>

  <!-- 这里是两个板块 -->
  <view class="middle">
    <view class="middle-content">

        <view class="message">
            <view class="desc-text">
                <view class="title1">我的信息</view>
                <view class="detail1">详细信息，就在这里！</view>
            </view>
            <view class="desc-img1">
               <image src="../../static/message.png"></image>
            </view>
        </view>

        <view class="division">
            <view class="vertical-line">
                <image src="../../static/vertical.png"></image>
            </view>
        </view>

        <view class="about">
            <view class="desc-text">
                <view class="title2">关于平台</view>
                <view class="detail2">更多关于平台的内容！</view>
            </view>
            <view class="desc-img2 ">
               <image src="../../static/about.png"></image>
            </view>
        </view>
    </view>
  </view>
      
   <view class="bottom">
     <view class="bottom-content">
         <view class="me-about">
             <text>我的信息</text>
             <image src="../../static/next.png"></image>
         </view>
         <view class="me-about">
             <text>考试刷题</text>
             <image src="../../static/next.png"></image>
         </view>
         <view class="me-about">
             <text>中北悄话</text>
             <image src="../../static/next.png"></image>
         </view>
         <view class="me-about">
             <text>投诉建议</text>
             <image src="../../static/next.png"></image>
         </view>
         <view class="me-about">
             <text>关于平台</text>
             <image src="../../static/next.png"></image>
         </view>
     </view>
   </view>
   
</view>
</template>


<script>

</script>


<style>

.user-info{
  display: flex;
  width: 100%;
  height: 150rpx;
}

.user-photo{
  margin: 20rpx 10rpx 10rpx 20rpx;
  align-self: center;
}
.user-photo image{
  width: 120rpx;
  height: 120rpx;
}


.process image{
  width: 60rpx;
  height: 60rpx;
}

.user-tag{
  display: flex;
  width: 330rpx;
  flex-direction: column;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  z-index: 9999;

}

.user-name{
	display: flex;
	margin: auto;
	margin-left: 0;
	margin-top: 40;
}

.user-name text{
  color: rgb(244, 243, 241);
  font-size: 34rpx;
  font-weight: 800;
}


.user-flag{
  margin: auto;
  margin-left: 0;
  margin-top: 0;
  display: flex;
}
.identity{
  background-color: darkorchid;
  color: gainsboro;
  padding: 5rpx 10rpx;
  font-size: 20rpx;
  border-radius: 8rpx;
}

.level{
  background-color: cornflowerblue;
  color: rgb(117, 238, 123);
  padding: 5rpx 10rpx;
  border-radius: 8rpx;
  margin-left: 10rpx;
  font-size: 20rpx;
}

.grow-up{
  margin-top: 20rpx;
  display: flex;
  flex-direction: column;

  margin-left: 0rpx;
}

.sign{
  display: inline;
}

.process{
  display: flex;
  align-self: center;
}

.grades{

  text-align: center;
  position: relative;
  margin: auto;
  margin-top: 0;
  top: -8rpx;
  font-size: 20rpx;
}

.exp{
  color: rgb(239, 209, 248);
  text-shadow: 2rpx 2rpx 2rpx #726d6d;
  letter-spacing: 1rpx;
}

.user-detail{
  display: flex;
  flex-wrap: wrap;
  margin: auto;
  margin-top: 10rpx;
  padding-top: 10rpx;
  align-items: center;
  justify-content: space-around;
  border-top: 1px solid rgb(214, 203, 203);
}

.type-name{
  color: rgb(244, 243, 241);
  text-align: center;
  font-size: 23rpx;

}

.type-num{
  color: rgb(244, 243, 241);
  text-align: center;
  font-size: 30rpx;
  font-weight: 600;
  position: relative;
  top: -5rpx;
}

.top{
  padding-top: 20rpx;
  box-shadow: 10rpx 10rpx 15rpx 10rpx #e1e1e1;
  background-color: rgb(180, 127, 196);
  border-radius: 20rpx;
}

/* 中间 */
.desc-img1 image{
  width: 70rpx;
  height: 70rpx;
}

.desc-img2 image{
  width: 100rpx;
  height: 100rpx;
}

.middle{
  display: flex;
  margin-top: 8rpx;
  height: 160rpx;
  box-shadow: 5rpx 5rpx 10rpx 5rpx #e1e1e1;
}

.middle-content{
  height: 120;
  width: 100%;
  padding-left: 20rpx;
  margin: auto;
  align-items: center;
  justify-content: space-around;
  display: flex;
}

.message{
  align-items: center;
  display: flex;
}

.division{
  display: flex;
  align-items: center;
}

.vertical-line image{
  width: 50rpx;
  height: 80rpx;
  z-index: 9999;
  vertical-align: middle;
}

.about{
  align-items: center;
  display: flex;
}

.title1{
  font-size: 30rpx;
  font-weight: 800;
  color: rgb(243, 197, 228);
}

.detail1{
  font-size: 20rpx;
  font-weight: 500;
  color: rgb(243, 197, 228);
}

.title2{
  font-size: 30rpx;
  font-weight: 800;
  color: rgb(188, 209, 138);
}

.detail2{
  font-size: 20rpx;
  font-weight: 500;
  color: rgb(188, 209, 138);
}


/* 下面 */
.bottom{
  margin-top: 50rpx;

}
.bottom-content{
  width: 95%;
  border-radius: 5%;
  margin: auto;
  background-color: rgb(253, 253, 253);
  padding-bottom: 35rpx;
  box-shadow: 5rpx 5rpx 10rpx 5rpx #e1e1e1;
}
.me-about{
  display: flex;
  margin: 20rpx 40rpx;
  padding: 30rpx 0rpx;
  justify-content: space-between;
  border-bottom: 2rpx solid rgb(238, 238, 238);
}
.me-about image{
  align-self: center;
  width: 35rpx;
  height: 35rpx;
}
</style>
