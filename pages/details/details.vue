<template>
	<view class="details">
		<view class="searchTop">
			<image src="../../static/pay/ret.png" class="ret" mode=""></image>
			<view class="select" :style="{backgroundImage: 'url('+imageURL+')'}">
				<text class="cuIcon-search selectLeft"></text>
				<input type="text" placeholder="输入关键词搜索" confirm-type="search" class="selectInput" @input="searchIcon"></input>
				<!-- <text class="cuIcon-voicefill"></text> -->
			</view>
			<image src="../../static/details/detailsmore.png" class="lss" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imageURL:'../../static/index/selectBg.png'
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.ret{
		width: 19rpx;
		height: 35rpx;
	}
	.lss{
		width: 56rpx;
		height: 40rpx;
	}
	.details{
		width: 100vw;
		height: 100vh;
		overflow-y: scroll;
		overflow-x: hidden;
		background: #fff;
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
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
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
