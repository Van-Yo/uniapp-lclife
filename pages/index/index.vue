<template>
	<view class="page">
		<!-- 轮播图 start -->
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="carousel">
			<swiper-item v-for="item in swiperList">
				<view class="swiper-item">
					<image :src="item" class="carousel"></image>
				</view>
			</swiper-item>
		</swiper>
		<!-- 轮播图 end -->
		
		<!-- 热门 -->
		<view class="page-block">
			<view class="title">
				<image src="../../static/icons/hot.png" class="ico"></image>
				<view class="content">
					火热
				</view>
			</view>
			<scroll-view scroll-x="true" class="scroll-hot">
				<view class="single-panel" v-for="item in hotFilmLiST">
					<image src="../../static/hot/hot1.jpg" class="panel-image"></image>
					<view class="panel-content">美国队长3</view>
					<rateCom rate="9.248"></rateCom>

				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	import rateCom from '../../components/rateCom.vue'
	export default {
		data() {
			return {
				title: 'Hello',
				swiperList :[],
				hotFilmLiST : []
			}
		},
		components:{
			rateCom
		},
		onLoad() {
			this.swiperList = [
				'../../static/swiper/swiper-1.jpg',
				'../../static/swiper/swiper-2.jpg',
				'../../static/swiper/swiper-3.jpg'
			];
			this.hotFilmLiST = [1,1,1,1,1,1]
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.carousel{
		width: 100%;
		height: 400upx;
	}
	.page-block{
		background-color: #fff;
		margin-top: 12upx;
		padding: 20upx 20upx 5upx;
	}
	.title{
		display: flex;
		flex-direction: row;
		align-items: center;
		.ico{
			width: 40upx;
			height: 40upx;
			margin-right: 10upx;
		}
		
	}
	.scroll-hot{
		width: 100%;
		white-space: nowrap;
		margin-top: 20upx;
	}
	.single-panel{
		display: inline-block;
		margin-right: 20upx;
		width: 200upx;
		.stars-list{
			display: flex;
			align-items: center;
			// justify-content: space-between;
			.single-star{
				width: 28upx;
				height: 28upx;
			}
			.rate{
				margin-left: 10upx;
				font-size: 14px;
			}
		}
		
	}
	.single-panel:last-child{
		margin-right: 0;
	}
	.panel-image{
		width: 100%;
		height: 250upx;
	}
	.panel-content{
		width: 200upx;
		margin-top: 5upx;
		font-size: 14px;
		font-weight: bold;
		text-align: center;
/* 		display: flex;
		justify-content: center; */
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
</style>
