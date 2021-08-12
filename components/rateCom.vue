<template>
	<view class="stars-list">
		<image v-for="(item,index) in lightRate" src="../static/hot/like.png" class="single-star"></image>
		<image v-for="(item,index) in greyRate" src="../static/hot/unlike.png" class="single-star"></image>
		<view class="rate">
			{{rateNum}}
		</view>
	</view>
</template>

<script>
	export default {
		name:"rateCom",
		data() {
			return {
				msg :'hello'
			};
		},
		props:{
			rate:{
				type:String,
				default:0
			}
		},
		computed:{
			rateNum(){
				return Math.floor(this.rate * 10) / 10
			},
			lightRate(){
				return Math.floor(+this.rate/2)
			},
			greyRate(){
				return 5-Math.floor(+this.rate/2)
			}
		}
	}
</script>

<style lang="scss">
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
</style>
