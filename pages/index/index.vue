<template>
	<view class="mian">
		<view class="content">
			<view class="top">
				<view class="cityName"  >
					{{pickerText}}
				</view>
				<view class="mpvue-picker"  >
					<view class="uni-padding-wrap uni-common-mt">
						
						<view class="uni-btn-v"><image @click="showMulLinkageThreePicker" src="../../static/index/return.png" class="cityChoose" mode=""></image></view>
					</view>
					<mpvue-picker
						:themeColor="themeColor"
						ref="mpvuePicker"
						:mode="mode"
						:deepLength="deepLength"
						:pickerValueDefault="pickerValueDefault"
						@onConfirm="onConfirm"
						@onCancel="onCancel"
						:pickerValueArray="pickerValueArray"
					></mpvue-picker>
					<mpvue-city-picker
						:themeColor="themeColor"
						ref="mpvueCityPicker"
						:pickerValueDefault="cityPickerValueDefault"
						@onCancel="onCancel"
						@onConfirm="onConfirm"
					></mpvue-city-picker>
				</view>
			
			
			<view class="select" :style="{backgroundImage: 'url('+imageURL+')'}">
				<text class="cuIcon-search selectLeft"></text>
				<input type="text" placeholder="输入关键词搜索" confirm-type="search" class="selectInput" @input="searchIcon"></input>
				<text class="cuIcon-voicefill"></text>
			</view>
			
			</view>
		</view>
		
		
		
		
		<view class="indexswiper">
			<swiper class="screen-swiper "  @change="change">
				<swiper-item v-for="(item,index) in swiperList" :key="index" >
					<image :src="item.url" mode="aspectFill" class="swiper_img" v-if="item.type=='image'"></image>
					<!-- <video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video> -->
				</swiper-item>
			</swiper>
		    <swiper-dot class="dot" :current="current" :list="swiperList"></swiper-dot>
		
		</view>
		
		<view class="projectList">
		   <view class="projectItem" v-for="(item,i) in prijectList" :key="i">
				<view class="box">
					<view class="boximg">
						<image class="boximg" :src="item.imageURL"></image>
					</view>
					<view class="boxname">
						{{item.name}}
					</view>
				</view>
			</view>
		</view>
        <view class="youhui">
        	<view class="y_top">
        		<view class="ytl">
        			优惠专区
        		</view>
				<view class="ytr">
					查看全部 >
				</view>
        	</view>
       
         <view class="youhuiList">
         	<view class="yh_left">
         		<view class="youitem1" :style="{backgroundImage: 'url('+youhuiList.imageURL1+')'}"  >
         			<view class="msg1" >
         				人气推荐榜
         			</view>
					<view class="msg2" >
						附近必吃
					</view>
         		</view>
         	</view>
			<view class="yh_right">
				<view class="youitem2" :style="{backgroundImage: 'url('+youhuiList.imageURL2+')'}" >
					<view class="msg1" :class="item.sp?'sp_text':'normal_text'">
						巨额满减
					</view>
					<view class="msg2" :class="item.sp?'sp_tex2':'normal_text'">
					评价吃海鲜
					</view>
				</view>
				
				<view class="youitem2" :style="{backgroundImage: 'url('+youhuiList.imageURL3+')'}"  >
					<view class="msg1" >
						新品促销
					</view>
					<view class="msg2">
						披萨赠饮品
					</view>
				</view>
			</view>
         </view>
          
		  <view class="yhj" :style="{backgroundImage: 'url('+yhjImageURL+')'}" >
		  	
		  </view>
 </view>
 
 
 
 <view class="fjsj">
 	<view class="y_top">
 		<view class="ytl">
 			附近商家
 		</view>
 		<view class="ytr sj_r">
 			<view class="">
 				筛选
 			</view>
			<view class=" fjsj_r" :style="{backgroundImage: 'url('+jt+')'}">
				
			</view>
 		</view>
 	</view>
 	      
    <view class="sjList" >
    	<view v-for="(item,index) in sjList" :key="index">
    		<view class="sjItem" :style="{backgroundImage: 'url('+sjbgImageURL+')'}">
    			<view class="sjItem_l" :style="{backgroundImage: 'url('+item.imageURL+')'}">
    				
    			</view>
				<view class="sjItem_b">
					<view class="t">
						{{item.title}}
					</view>
					<view class="bstar">
						<view class="" v-for="(i,ind) in item.star" :key="ind">
							<view class="starBox " :style="{backgroundImage: 'url('+starBox+')'}">
								<image src="../../static/index/star.png" class="star" mode=""></image>
							</view>
						</view>
					</view>
					
					<view class="address">
						<view class="add_l" :style="{backgroundImage: 'url('+addr+')'}">
							
						</view>
						<view class="add_b">
							{{item.msg1}}
						</view>
						<view class="add_r">
							{{item.msg2}}
						</view>
					</view>
					<view class="sjmsg3">
						{{item.msg3}}
					</view>
				</view>
				<view class="sjItem_r">
					<image src="../../static/index/more.png" class="sjI_r_i" mode=""></image>
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
import mpvuePicker from '@/components/mpvue-picker/mpvuePicker.vue';
// https://github.com/zhetengbiji/mpvue-citypicker
import mpvueCityPicker from '@/components/mpvue-citypicker/mpvueCityPicker.vue';
import cityData from '@/common/city.data.js';
import swiperDot from '../../pages/swiperDot/swiperDot.vue';
export default {
	
	components: {
		mpvuePicker,
		mpvueCityPicker,
		swiperDot
	},
	data() {
		return {
			componentItem: 'index',
             starBox:'../../static/index/starBox.png',
			mulLinkageTwoPicker: cityData,
			cityPickerValueDefault: [0, 0, 1],
			themeColor: '#007AFF',
			pickerText: '北京',
			mode: '',
			deepLength: 1,
			pickerValueDefault: [0],
			pickerValueArray: [],
			imageURL:'../../static/index/selectBg.png',
			sjbgImageURL:'../../static/index/sjList_bg.png',
			addr:'../../static/index/addr.png',
			sjList:[{
				imageURL:'../../static/index/sj_1.png',
				title:'包图1号牛排',
				star:[1,1,1,1,1],
				msg1:'包图路',
				msg2:'西式餐厅',
				msg3:'听说这儿的牛排份量超大'
			}],
			current: 0,
			swiperList: [{
				id: 0,
				type: 'image',
				url: '../../static/index/swiper.png'
			}, {
				id: 1,
				type: 'image',
                url: '../../static/index/swiper.png'			,
				}, {
				id: 2,
				type: 'image',
               url: '../../static/index/swiper.png'			}],
			dotStyle: true,
			prijectList:[{
				imageURL:'../../static/index/list/zc.png',
				name:'中餐'
			},{
				name:'饮品',
				imageURL:'../../static/index/list/yp.png',
			},{
				name:'快餐',
				imageURL:'../../static/index/list/kc.png',
			},{
				name:'西餐',
				imageURL:'../../static/index/list/xc.png',
			},{
				name:'甜品',
				imageURL:'../../static/index/list/tp.png',
			},{
				name:'超市',
				imageURL:'../../static/index/list/cs.png',
			},{
				name:'生鲜',
				imageURL:'../../static/index/list/sx.png',
			},{
				name:'更多',
				imageURL:'../../static/index/list/gd.png',
			}],
			youhuiList:{
				imageURL1:'../../static/index/yh1.png',
				imageURL2:'../../static/index/yh2.png',
				imageURL3:'../../static/index/yh3.png'
			},
			yhjImageURL:'../../static/index/yhj.png',
			jt:'../../static/index/fjsj1.png'
		};
	},
	onLoad() {},
	methods: {
		NavChange: function(e) {
			this.PageCur = e.currentTarget.dataset.cur;
		},
		change(e) {
					this.current = e.detail.current;
				},
		onCancel(e) {
			console.log(e);
		},

		// 三级联动选择
		showMulLinkageThreePicker() {
			this.$refs.mpvueCityPicker.show();
		},
		onConfirm(e) {
			// console.log(e.label)
			let arr=e.label.split("-");
			// console.log(arr);
			for(let i of arr){
				if(i.charAt(i.length-1)=="市"){
					// console.log(i);
					i = i.substr(0, i.length - 1);
					this.pickerText=i;
				}
			}
		}
	},
	onBackPress() {
		if (this.$refs.mpvuePicker.showPicker) {
			this.$refs.mpvuePicker.pickerCancel();
			return true;
		}
		if (this.$refs.mpvueCityPicker.showPicker) {
			this.$refs.mpvueCityPicker.pickerCancel();
			return true;
		}
	}
};
</script>

<style>
	.sjmsg3{
		width: 233rpx;
		height: 34rpx;
		background-color: #ffeae5;
		color: #ffa990;
		font-size: 18rpx;
		text-align: center;
		line-height: 34rpx;
	}
	.address{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: baseline;
	}
	.bstar{
		display: flex;
		width: 26rpx;
		flex-direction: row;
		/* justify-content: space-around; */
	}
	.sjItem_b{
		display: flex;
		flex-direction: column;
		justify-content: space-around;
	}
	.sjItem{
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		align-items: center;
	}
	.star{
		position: absolute;
		left: 0;
		top: 0;
		bottom: 0;
		right: 0;
		margin: auto;
		width: 17rpx;
		height: 16rpx;
	}
	.add_l{
		width: 21rpx;
		height: 20rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
		
	}
	.starBox{
		width: 26rpx;
		height: 26rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
		position: relative;
		margin-right: 8rpx;
	}
	.sjI_r_i{
		width: 36rpx;
		height: 8rpx;
	}
	.sjItem_l{
		width: 158rpx;
		height: 158rpx;background-size: 100%;
		background-repeat:no-repeat ;
	}
	.sjItem{
		width: 730rpx;
		height: 260rpx;background-size: 100%;
		background-repeat:no-repeat ;
		margin: 30rpx 0;
	}
	.sj_r view{
		height: 34rpx;
	}
	
	.fjsj{
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
	}
	.fjsj_r{
		
		width: 21rpx;
		height: 17rpx;
		justify-content: space-between;
		margin-top: 16rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
	}
	.yhj{
		width: 749rpx;
		height: 216rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
		margin-top: 20rpx;
	}
	.youhuiList{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		margin-top: 48rpx;
	}
	.yh_right{
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.youitem1{
		width: 330rpx;
		height: 330rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
	}
	.youitem2{
		width: 350rpx;
		height: 155rpx;
		background-size: 100%;
		background-repeat:no-repeat ;
	}
	.youhui{
		display: flex;
		flex-direction: column;
		width: calc(100% - 50rpx);
		margin: 0 25rpx;
		margin-top: 50rpx;
	}
	.y_top{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: baseline;
	}
	.ytl{
		font-size: 38rpx;
		font-weight: bold;
	}
	.ytr{
		color: #b8b8b8;
		font-size: 22rpx;
	}
	.boxname{
		margin-top: 20rpx;
		font-size: 30rpx;
	}
	.projectList{
		width: calc( 100% - 50rpx);
		margin: 0 25rpx;
  flex-wrap: wrap;
  flex-direction: row;
  display: flex;
  justify-content: space-around;
	}
	.projectItem{
		 width: 110rpx;
	margin: 0 30rpx;
	margin-top: 40rpx;
		 flex-direction: row;
	}
	.boximg{
		width: 100rpx;
		height: 100rpx;
	}
	.box{
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
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
	.swiper_img{
		width: 700rpx;
		height: 370rpx;
	}
.indexswiper{
	width: calc( 100% - 50rpx);
	margin: 0 25rpx;
	border-radius:10rpx ;
}
	[class*="cuIcon-"] {
	font-family: "cuIcon";
	font-size: 45rpx;
	font-style: normal;
	
	}

	.cityName{
		margin-right: 10rpx;
	}
	.top{
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}
	.mpvue-picker{
		margin-right: 20rpx;
	}
	.cu-bar {
     height: ;
}
	
	.content{
		width: calc( 100% - 50rpx);
		margin:0 25rpx ;
		/* background: #000000; */
		/* margin-bottom: 200rpx; */
		overflow-y: scroll;
	}
.mian {
	width: 100vw;
	background-color: #fff;
	height: 100vh;
	overflow-y: scroll;
	margin-bottom: 100rpx;
	padding-top: 40rpx;
overflow-x: hidden;

}
.text-gray,
.line-gray,
.lines-gray {
	color: #000;
	margin-top: 10rpx;
}
.cityChoose{
	width: 25rpx;
	height: 14rpx;
}
.sj_r{
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		font-size: 24rpx;
	}
</style>
