<template>
	<view class="pay">
		<view class="top">
			<view class="text">
				支付订单
			</view>
			<view class="ret">
				<image src="../../static/pay/ret.png" class="retImg" mode=""></image>
			</view>
		</view>
		<view class="content" :style="{backgroundImage: 'url('+bg+')'}">
			<view class="p1">
				<view class="p1imgbox">
					<image src="../../static/pay/bt1.png" class="p1img2" mode=""></image>
				</view>
				<view class="p1imgbox2">
					<image src="../../static/pay/Baotu1.png" class="p1img" mode=""></image>
				</view>
			</view>
			<view class=" p2">
				<view class="t">
					<view class="l">
						<image src="../../static/pay/NIiupi.png" class="img_l" mode=""></image>
					</view>
					<view class="r">
						￥398
					</view>
				</view>
				<view class="b">
					<view class="l">
						赠送：水果沙拉一份，意面一份
					</view>
					<view class="r">
						x1
					</view>
				</view>
			</view>
			
			
			<view class=" p2">
				<view class="t">
					<view class="l">
						<image src="../../static/pay/Liaobude.png" class="img_l" mode=""></image>
					</view>
					<view class="r">
						￥298
					</view>
				</view>
				<view class="b">
					<view class="l">
						赠送：水果沙拉一份，意面一份
					</view>
					<view class="r">
						x1
					</view>
				</view>
			</view>
			
			<view class="p2 give">
				<view class="mon">
					￥703.00
				</view>
				<view class="gps">
					<view class="gtxt">
						（由距离自动计算）
					</view>
					<view class="gtext2">
						配送费￥10
					</view>
				</view>
			</view>
			
			
		</view>
		
		
		
		
		<view class="beizu" :style="{backgroundImage: 'url('+bzbg+')'}">
			<view class="beizuBox">
				<image src="../../static/pay/xg.png" class="xg" mode=""></image>
				<input type="text" class="inp" v-model="conetnt" placeholder="添加备注 (50字内):" />
			</view>
		</view>
		
		
		<view class="btn"  :style="{backgroundImage: 'url('+btn+')'}" @tap="dig=!dig">
			确认订单
		</view>
		
		
		
		
		
		<view class="dig" v-if="dig" >
			<view class="otherdig" @tap="dig=!dig">
				
			</view>
			<view class="digbg" :style="{backgroundImage: 'url('+digbg+')'}">
				
				<view class="box1">
					为了确保用餐体验，请确认信息无误
				</view>
				<view class="box1 box2">
					<view class="">
						<image class="addr" src="../../static/index/addr.png" mode=""></image>
					</view>
					<view class="boxTop">
						
						<view class="btl">
							包图小区05号楼201室
						</view>
						<view class="">
							包图（先生）130****5555
						</view>
					</view>
					
				</view>
				
				
				<view class="box1 box3">
					<view class="">
						<image src="../../static/pay/time.png" class="time" mode=""></image>
					</view>
					<view class="box3C">
						立即送达
					</view>
					<view class="box3T">
						（预计10:11）
					</view>
				</view>
				
				<view class="box1 box3 box4">
					<view class="box3Csp">
						卡券
					</view>
					<view class="box3T">
						（新人分享红包）
					</view>
				</view>
				
				<view class="box1 box3 box5">
					<view class="box3Csp">
						备注
					</view>
					<view class="box3T">
						（无）
					</view>
				</view>
				
				
				<view class="box1 box6">
					
					<view class="box6f">
						<view class="">
							餐品总价格
						</view>
						<view class="">
							￥696.00
						</view>
					</view>
					
					
					<view class="box6f">
						<view class="">
							配送费（由距离自动计算）
						</view>
						<view class="">
							￥10.00
						</view>
					</view>
					
					<view class="box6f">
						<view class="">
							优惠金额
						</view>
						<view class="">
							-￥10.00
						</view>
					</view>
					
					
					<view class="box6f">
						<view class="">
							实付
						</view>
						<view class="textsp">
							￥703.00
						</view>
					</view>
				</view>
				
				
				
				<view class="btnsp"  :style="{backgroundImage: 'url('+btn+')'}" @tap="dig=!dig">
					确认支付
				</view>
				
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				bg:'../../static/pay/bg.png',
				bzbg:'../../static/pay/bzBox.png',
				content:'',
				btn:'../../static/pay/btn.png',
				dig:true,
				digbg:'../../static/pay/digbg.png'
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.textsp{
	color: #000000;
	font-weight: bold;
	font-size: 40rpx;
}
	.box6f{
		display: flex;
		flex-direction: row;
		margin: 15rpx 0;
		justify-content: space-between;
	}
	.box3C{
		color: #000000;
		margin-left: 20rpx;
		font-size: 30rpx;
		font-weight: bold;
	}
	.box3Csp{
		color: #000000;
		/* margin-left: 20rpx; */
		font-size: 30rpx;
		font-weight: bold;
	}
	.box3{
		display: flex;
		align-items: baseline;
		flex-direction: row;
	}
	.time{
		width: 24rpx;
		height: 24rpx;
	}
	.box2{
		display: flex;
		flex-direction: row;
	}
	.btl{
		color: #000000;
		margin-bottom: 10rpx;
		font-size: 30rpx;font-weight: bold;
	}
	.boxTop{
		margin-left: 20rpx;
		display: flex;
		flex-direction: column;
	}
	.box1{
		width: 596rpx;
		margin: 0 auto;
		padding-top: 32rpx;
		padding-bottom: 32rpx;
		color: #c9c9c9;
		border-bottom: solid 4rpx #f9f9f9;
	}
	.addr{
		width: 22rpx;
		height: 22rpx;
	}
	.otherdig{
		width: 100vw;
		height: calc(100% - 970rpx);
		background: rgba(0,0,0,0);
		position: fixed;
		top: 0;
		left: 0;
	}
	.digbg{
		width: 100vw;
		height: 970rpx;
		position: fixed;
		bottom: 0;
		left: 0;
		z-index: 3;
		background-size:100% ;
		background-repeat:no-repeat ;
	}
	.dig{
		width: 100vw;
		height: 100vh;
		background: rgba(0,0,0,0.5);
		position: fixed;
		top: 0;
		left: 0;
		z-index: 2;
	}
	.btn{
		width: 674rpx;
		height: 90rpx;
		background-size:100% ;
		margin: 0 auto;
		line-height: 90rpx;
		text-align: center;
		color: #000000;
		font-size: 30rpx;font-weight: bold;
		margin-top: 100rpx;
	}
	.btnsp{
		width: 674rpx;
		height: 90rpx;
		background-size:100% ;
		margin: 0 auto;
		line-height: 90rpx;
		text-align: center;
		color: #000000;
		font-size: 30rpx;font-weight: bold;
	}
	.inp{
		padding-left: 15rpx;
	}
	.beizuBox{
		display: flex;
		flex-direction: row;
		align-items: center;
		width: 584rpx;
		margin: 0 auto;
		padding-top: 50rpx;
		padding-bottom: 25rpx;
		border-bottom: solid 4rpx #f9f9f9;
	}
	.xg{
		width: 24rpx;
		height: 24rpx;
	}
	.p1imgbox{
		margin-right: 20rpx;
	}
	.beizu{
		width: 726rpx;
		height: 278rpx;
		background-size:100% ;
		background-repeat:no-repeat ;
		margin: 0 auto;
	}
	.gtext2{
		font-size: 24rpx;
	}
	.gtxt{
		font-size: 20rpx;
		color: #cdcdcd;
	}
	.mon{
		font-size: 40rpx;
		font-weight: bold;
	}
	.gps{
		display: flex;
		flex-direction: row;
		justify-content: baseline;
	}
	.give{
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		align-items: flex-end;
	}
	.b{
		margin-top: 12rpx;
		font-size: 24rpx;
		color:#cacaca;
	}
	.img_l{
		width: 190rpx;
		height: 35rpx;
	}
	.p1{
		display: flex;
		flex-direction: row;
		align-items: center;
		/* background: #007AFF; */
		width: 584rpx;
		margin: 0 auto;
		padding-top: 50rpx;
		padding-bottom: 25rpx;
		border-bottom: solid 4rpx #f9f9f9;
	}
	
	.p2{
		width: 584rpx;
		margin: 0 auto;
		padding-top: 50rpx;
		padding-bottom: 25rpx;
		display: flex;
		flex-direction: column;
			border-bottom: solid 4rpx #f9f9f9;
	}
	.t,.b{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: space-between;
	}
	.p1img2{
		width: 60rpx;
		height: 60rpx;
	}
	.p1img{
		width: 299rpx;
		height: 38rpx;
	}
	.content{
		width: 726rpx;
		height: 648rpx;
		background-size:100% ;
		background-repeat:no-repeat ;
		
		margin: 0 auto;
		margin-top: 30rpx;
	}
.pay{
	width: 100%;
	height: 100vh;
	overflow-y: scroll;
	background: #fff;
	padding-top: 100rpx;
	padding-bottom: 30rpx;
}
.text{
	font-size: 40rpx;height: 40rpx;
	width: 100%;
	line-height: 40rpx;
	text-align: center;
}
.retImg{
	width: 19rpx;
	height: 35rpx;
	float: left;
	margin-top: -35rpx;
	margin-left: 65rpx;
	}
</style>
