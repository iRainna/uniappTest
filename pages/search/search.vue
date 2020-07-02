<template>
	<view class="search">
		<view class="searchTop">
			<view class="select" :style="{backgroundImage: 'url('+imageURL+')'}">
				<text class="cuIcon-search selectLeft"></text>
				<input type="text" placeholder="输入关键词搜索" confirm-type="search" class="selectInput" @input="searchIcon"></input>
				<text class="cuIcon-voicefill"></text>
			</view>
			<image src="../../static/frist/ls.png" class="ls" mode=""></image>
		</view>
		<view class="hotSearch">
			<view class="hotSearchTitle">
				热门搜索
			</view>
			<view class="hotSearchList">
				<view v-for="(item,index) in hotSearchList" :key="index">
					<view class="hs_box" :style="{backgroundImage: 'url('+hs_box+')'}">
						<view class="hs_left">
							<view class="hsname">
								{{item.name}}
							</view>
							<view class="hsnumber">
								{{item.number+'道'}}
							</view>
						</view>
						<view class="hs_right">
							<image :src="item.imageURL" class="hs_img" mode=""></image>
						</view>
					</view>
				</view>
			</view>
		</view>
		
		<view class="searchHistory">
			<view class="sh_top">
				<view class="hotSearchTitlesp">
					搜索历史
				</view>
				<view class="clear" @tap="clearHistory">
					清空
				</view>
			</view>
			<view class="dataList">
				<view  v-if="dataList.length==0">
					暂无搜索历史
				</view>
				<view v-for="(item,index) in dataList" :key="index" v-if="dataList.length!=0">
					<view class="BoxData  ">
						{{item}}
					</view>
				</view>
			</view>
		</view>
		
		
		<view class="vip">
			<view class="sh_top">
				<view class="hotSearchTitlesp">
					大人推荐
				</view>
				
			</view>
			<view class="dataList">
				
				<view v-for="(item,index) in vipList" :key="index" v-if="dataList.length!=0">
					<view class="vipbox " :style="{backgroundImage: 'url('+vipBox+')'}">
						<view class="img">
							<image :src="item.imageURL" class="vimg" mode=""></image>
						</view>
						<view class="name">
							{{item.name}}
						</view>
						<view class="star">
							<view v-for="(item,index) in item.star" :key="index">
								<image class="vstar" src="../../static/frist/star.png" mode=""></image>
							</view>
						</view>
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
				imageURL:'../../static/index/selectBg.png',
				hs_box:'../../static/search/box.png',
				hotSearchList:[{
					name:"早餐",
					number:2222,
					imageURL:'../../static/search/zc.png'
				},{
					name:"午餐",
					number:2222,
					imageURL:'../../static/search/wc.png'
				},{
					name:"晚餐",
					number:2222,
					imageURL:'../../static/search/wc2.png'
				},{
					name:"面食",
					number:2222,
					imageURL:'../../static/search/ms.png'
				}],
				dataList:["早餐","川菜","鸡蛋","烘培","煲汤","腊肉","香肠"],
				vipBox:'../../static/search/vipBox.png',
				vipList:[{
					imageURL:'../../static/search/vip1.png',
					name:'包大厨子',
					star:[1,1,1,1,1]
				},{
					imageURL:'../../static/search/vip2.png',
					name:'包图大厨',
					star:[1,1,1,1,1]
				},{
					imageURL:'../../static/search/vip3.png',
					name:'包大厨',
					star:[1,1,1,1,1]
				},]
			}
		},
		methods: {
			clearHistory(){
				this.dataList=[]
			}
		}
	}
</script>

<style>
	.name{
		margin-top: 36rpx;
	}
	.star{
		display: flex;
		flex-direction: row;
		margin-top: 18rpx;
	}
	.vipbox{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.vstar{
		width: 14rpx;
		height: 14rpx;
	}
	.vimg{
		width: 112rpx;
		height: 112rpx;
	}
	.vipbox{
		width: 234rpx;
		height: 294rpx;
		background-size:100% ;
		background-repeat:no-repeat ;
	}
	.vip{
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
		margin-top: 40rpx;
		padding-bottom: 40rpx;
	}
	.dataList{
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
	}
	.BoxData{
		width: 130rpx;
		font-size: 30rpx;
		text-align: center;
		height: 60rpx;
		line-height: 60rpx;
		box-shadow: 3px 3px 4px rgba(26, 26, 26, 0.2);
		border: solid 1rpx #e7e7e7;
		margin:20rpx 40rpx 20rpx 0 ;
	}
	.clear{
		font-size: 25rpx;
	}
	.sh_top{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		}
	.searchHistory{
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
		margin-top: 40rpx;
	}
	.hsname{
		font-size: 30rpx;
	}
	.hsnumber{
		font-size:22rpx ;
		color: #d6d8dc;
		margin-top: 10rpx;
	}
	.hotSearchList{
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-around;
	}
	.hs_right{
		margin-top: -25rpx;
	}
	.hs_img{
		width: 120rpx;
		height: 120rpx;
	}
	.hs_box{
		width:344rpx ;
		height: 130rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
		margin-bottom: 20rpx;
		margin-top: 10rpx;
	}
	.hotSearchTitle{
		color:#f54c4a;
		font-size: 28rpx;
		font-weight: bold;
padding-bottom: 30rpx;
	}
	.hotSearchTitlesp{
			/* color:#f54c4a; */
			font-size: 28rpx;
			font-weight: bold;
	padding-bottom: 30rpx;
		}
	.hotSearch{
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
		margin-top: 40rpx;
	}
	.search{
		background-color: #fff;
	}
	.searchTop{
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
		padding-top: 100rpx;
	}
	.ls{
		width: 38rpx;
		height: 42rpx;
	}
	[class*="cuIcon-"] {
	font-family: "cuIcon";
	font-size: 45rpx;
	font-style: normal;
	
	}
.select{
	   width: 580rpx;
	  height: 118rpx;
	  border-radius: 118rpx;

	   background-repeat:no-repeat ;
	   background-size: 100%;
	   display: flex;
	   flex-direction: row;
	   align-items: center;
	   justify-content:flex-start;
	   padding: 0 55rpx;
	}
	.selectLeft{
		margin-right: 48rpx;
	}
</style>
