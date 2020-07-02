<template>
	<view class="frist">
		
		<view class="top" :style="{backgroundImage: 'url('+bg+')'}">
			<image src="../../static/frist/bg2.png" class="bg2" mode=""></image>
			<view class="iconP" @tap="goSearch">
					<text class="cuIcon-search"></text>
			</view>
		<view class="text">
			<view class="text1">
				美食汇
			</view>
			<view class="text2">
				发现美食·分享生活
			</view>
		</view>
		</view>
		
		<view class="banner" :style="{backgroundImage: 'url('+banner+')'}" @tap="goIndex">
			
		</view>
		<view class="List">
			<view v-for="(item,index) in List" :key="index">
				<view class="boxList">
					<view class="imgBox">
						<image :src="item.imageUrl" class="img" mode=""></image>
					</view>
					
					<view class="msg">
						{{item.name}}
					</view>
				</view>
				
			</view>
		</view>
		
		<view class="breakfast">
			<view class="breakfastText">
				营养早餐
			</view>
			
			<view class="breakfastList">
				<view v-for="(item,index) in breakfastList" :key="index">
					<view class="item">
						<view class="itemImgBox">
							<image :src="item.imageUrl" class="itemImg" mode=""></image>
						</view>
						<view class="b_name">
							{{item.name}}
						</view>
						<view class="item_b">
							<view class="item_bmsg">
								{{item.msg}}:
							</view>
							<view class="item_b_star">
								<view v-for="(item,index) in item.star" :key="index">
									<image src="../../static/frist/star.png" class="b_star" mode=""></image>
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		
		
		
		
		
		
		<view class="cu-bar tabbar bg-white shadow foot">
			<view class="action" @click="NavChange" data-cur="basics">
				<view class="cuIcon-cu-image"><image :src="'/static/index/index' + [componentItem == 'index' ? '_on' : '_out'] + '.png'"></image></view>
				<view :class="PageCur == 'basics' ? 'text-green' : 'text-gray'">首页</view>
			</view>
			<view class="action" @click="NavChange" data-cur="component">
				<view class="cuIcon-cu-image"><image :src="'/static/index/find' + [componentItem == 'find' ? '_on' : '_out'] + '.png'"></image></view>
				<view :class="PageCur == 'component' ? 'text-green' : 'text-gray'">发现</view>
			</view>
			<view class="action" @click="NavChange" data-cur="plugin">
				<view class="cuIcon-cu-image"><image :src="'/static/index/service' + [componentItem == 'service' ? '_on' : '_out'] + '.png'"></image></view>
				<view :class="PageCur == 'plugin' ? 'text-green' : 'text-gray'">服务</view>
			</view>
			<view class="action" @click="NavChange" data-cur="plugin">
				<view class="cuIcon-cu-image"><image :src="'/static/index/mine' + [componentItem == 'mine' ? '_on' : '_out'] + '.png'"></image></view>
				<view :class="PageCur == 'plugin' ? 'text-green' : 'text-gray'">我</view>
			</view>
		
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				componentItem:'index',
				bg:'../../static/frist/bg1.png',
				banner:'../../static/frist/banner.png',
				breakfastList:[{
					imageUrl:'../../static/frist/zc1.png',
					name:'水饺蘸酱料',
					msg:'营养指数',
					star:[1,1,1,1,1]
				},{
					imageUrl:'../../static/frist/zc2.png',
					name:'西红柿鸡蛋面',
					msg:'营养指数',
					star:[1,1,1,1,1]
				}],
				List:[{
					name:'家常菜',
					imageUrl:'../../static/frist/jcc.png'
				},{
					name:'烘培',
					imageUrl:'../../static/frist/hb.png'
				},{
					name:'健康养生',
					imageUrl:'../../static/frist/jkys.png'
				},{
					name:'赚积分',
					imageUrl:'../../static/frist/zjf.png'
				},{
					name:'活动',
					imageUrl:'../../static/frist/hd.png'
				}]
			}
		},
		methods: {
			goIndex(){
				uni.navigateTo({
				    url: '../../pages/index/index'
				});
			},goSearch(){
				uni.navigateTo({
				    url: '../../pages/search/search'
				});
			}
		}
	}
</script>

<style>
	.item_bmsg{
		font-size: 24rpx;color: #b8b8b8;
	}
	.b_name{
		font-size: 30rpx;margin-top: 25rpx;
		margin-bottom: 15rpx;
	}
	.item_b{
		display: flex;
		flex-direction:row ;
	align-items: center;
	margin-bottom: 20rpx;
	}
	.item_b_star{
		display: flex;
		flex-direction: row;
	}
	.breakfastList{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	.item{
		display: flex;
		flex-direction: column;
	}
	.itemImg{
		width: 336rpx;
		height: 260rpx;
	}
	.b_star{
		width: 14rpx;
		height: 14rpx;
		/* margin-bottom: 20rpx; */
	}
	.breakfast{
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
		
		margin-top: 38rpx;
		
	}
	.breakfastText{
		font-size: 34rpx;
		font-weight: bold;
		padding-bottom: 30rpx;
		}
	.List{
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		margin-top: 30rpx;
	}
	.boxList{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.img{
		width: 42rpx;
		height: 42rpx;
	}
	.iconP{
		position:absolute;
		right: 33rpx;
		top: 38rpx;
	}
	[class*="cuIcon-"] {
	font-family: "cuIcon";
	font-size: 40rpx;
	font-style: normal;
	}
.text1{
	font-size: 60rpx;
	color: #fff;
	margin-bottom: 10rpx;
	}
	.text2{
		font-size: 26rpx;color: #fff;
	}
	.text{
		margin-left: 25rpx;
	}
	.frist{
		overflow-x: hidden;
overflow-y: scroll;
		background: #fff;
		width: 100%;
		height: auto;
		margin-bottom: 100rpx;
		padding-top: 40rpx;

	}
	.banner{
		width: calc(100% - 50rpx);
		height: 370rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
		
		margin: 0 25rpx;
		margin-top: 20rpx;
	}
.top{
	width: 100%;
	height: 300rpx;
	background-size: 632rpx 293rpx;
	background-repeat:no-repeat ;
	position: relative;
}
.bg2{
	position: relative;
	top: 0;
	left: 50%;
	width: 297rpx;
	height: 79rpx;
	margin-left: -130rpx;
}
</style>
