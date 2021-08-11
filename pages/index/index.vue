<template>
	<view class="page">
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="carousel">
			<swiper-item v-for="item in swiperList">
				<view class="swiper-item">
					<image :src="item" class="carousel"></image>
				</view>
			</swiper-item>
		</swiper>
		
		<!-- 热门 -->
		<view class="page-block">
			<view class="">
				<!-- <image src="" mode=""></image> -->
				<view class="">
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				swiperList :[]
			}
		},
		onLoad() {
			this.swiperList = [
				'../../static/swiper/swiper-1.jpg',
				'../../static/swiper/swiper-2.jpg',
				'../../static/swiper/swiper-3.jpg'
			]
		},
		methods: {

		}
	}
</script>

<style>
	.carousel{
		width: 100%;
		height: 400upx;
	}
</style>
