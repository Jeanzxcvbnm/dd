<template>
	<view class="mian">
		<uni-swiper-dot :info="swipers" :current="current" :dotsStyles="dotsStyle">
			<swiper @change="change">
				<swiper-item v-for="(item,index) in swipers">
					<view class="swiper-item">
						<image class="image" :src="item.url"></image>
					</view>
				</swiper-item>
			</swiper>
		</uni-swiper-dot>
		<view class="price_wrap">
			<text class="pr">￥<text>2990</text>.00</text>
			<view class="pic">
				<view class="jiang">
					<image src="../../static/image/recharge.png"></image>
					<text>降价提醒</text>
				</view>
				<view class="jiang">
					<image src="../../static/image/favor.png" mode=""></image>
					<text>收藏</text>
				</view>
			</view>
		</view>
		<view class="title_wrap">
			<image class="image" src="../../static/image/ziying.png"></image>
			<text> 戴森(Dyson) 新一代吹风机 Dyson Supersonic 电吹风 进口家用 年货礼物推荐 HD03 紫红色</text>
		</view>
		<view class="desc">
			<view class="info">
				【1.15-1.30年货节来袭】赠造型梳套装x1 【享3期免息】紫红色经典款，快速干发不伤发 【闪电发货，现货急速达】立即抢购》》
			</view>
			<!-- <view class="more">v</view> -->
		</view>
		<!-- 放心购 -->
		<view class="buy" @click="open">
			<view class="">
				<text>放心购</text>
			</view>
			<view>
				<text>30-30-180</text>
				<text> · 上门换新</text>
				<text> · 家电小秘书</text>
			</view>
			<view class="footer">
				<image src="../../static/image/more_light.png"></image>
			</view>
		</view>
		<view class="gap"></view>
		<view class="discount">
			<view class="content">
				<text class="dis">优惠</text>
				<text class="tag">赠送</text>
				<text class="info">【赠品】戴森(Dyson) 造型套装（宽齿梳X1+气囊板梳X1） X1</text>
			</view>
		</view>

























		<!-- 放心购弹窗 -->
		<uni-popup ref="popup" type="bottom">
			<view class="heart">
				<view class="header">
					<text>放心购</text>
				</view>
				<view class="body">
					<view class="one">
						本页面服务内容，与客户会员等级、信用等级等多维度因素相关，具体可享受的服务以客户申请售后时页面展示的信息为准。
					</view>
					<view class="two">
						<view class="text">
							30-30-180
						</view>
						<view class="content">
							30天价保；30天质量问题包退；180天质量问题包换
						</view>
					</view>
					<view class="two">
						<view class="text">
							上门换新
						</view>
						<view class="content">
							签收15天内因商品性能故障换货的，上门取件时直接换新。
						</view>
					</view>
					<view class="two">
						<view class="text">
							家电小秘书
						</view>
						<view class="content">
							享受京东家电专属客服团队为您提供的专业贴心服务。
						</view>
					</view>
				</view>
				<view class="button">
					<button type="warn" @click="comfirm">确定</button>
				</view>
			</view>
		</uni-popup>
	</view>
</template>

<script lang="ts">
	import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue"
	import uniPopup from "@/components/uni-popup/uni-popup.vue"
	export default {
		components: {
			uniSwiperDot,
			uniPopup
		},
		data() {
			return {
				current: 0,
				dotsStyle: {
					selectedBackgroundColor: "#ff0000"
				},
				swipers: [{
						url: '../../static/image/c1.jpg'
					},
					{
						url: '../../static/image/c2.jpg'
					},
					{
						url: '../../static/image/c3.jpg'
					},
					{
						url: '../../static/image/c4.jpg'
					},
					{
						url: '../../static/image/c5.jpg'
					}
				]
			}
		},
		methods: {
			change(e) {
				this.current = e.detail.current;
			},
			open() {
				this.$refs.popup.open();
			},
			comfirm() {
				this.$refs.popup.close();
			}
		}
	}
</script>

<style lang="scss">
	.mian {
		.discount {
			padding: 24rpx 20rpx 0 20rpx;

			.content {
				display: flex;
				.dis {
					color: #999;
					font-size: 24rpx;
					margin-right: 20rpx;
				}

				.tag {
					color: #e93b3d;
					border-radius: 10rpx;
					border: 2rpx solid #e93b3d;
					font-size: 20rpx;
					padding: 0 6rpx;
					background-color: #fbf0fd;
				}
			}

			.info {
				font-size: 24rpx;
				width: 540rpx;
				overflow: hidden;
				text-overflow: ellipsis;
				display: -webkit-box;
				-webkit-line-clamp: 1;
				-webkit-box-orient: vertical;
			}
			.info:after{
				content: "";
				position: absolute;
				background-image: url(../../static/image/more.png);
			}
		}

		.gap {
			padding-top: 20rpx;
			background: #e8e8ed;
			z-index: 2;
		}

		// 放心购
		.heart {
			background: #fff;

			.header {
				background: #f7f7f7;
				height: 92rpx;
				line-height: 92rpx;
				font-size: 32rpx;
				padding-left: 20rpx;
			}

			.body {
				font-size: 24rpx;
				color: #666;
				padding: 24rpx 20rpx 0 20rpx;
				margin-bottom: 100rpx;

				.two {
					padding: 24rpx 20rpx 24rpx 0;

					.text {
						color: #e93b3d;
						font-size: 24rpx;
						line-height: 42rpx;
					}
				}
			}
		}

		.buy {
			color: #e93b3d;
			display: flex;
			line-height: 70rpx;
			background-color: #fbf0fd;
			padding: 0 60rpx 0 20rpx;
			justify-content: space-between;

			.footer {
				display: flex;
				align-items: center;

				image {
					width: 40rpx;
					height: 40rpx;
				}
			}
		}

		swiper {
			width: 750rpx;
			height: 750rpx;

			swiper-item {
				.swiper-item {
					.image {
						width: 750rpx;
						height: 750rpx;
					}
				}
			}
		}

		.desc {
			.info {
				// height: 60rpx;
				overflow: hidden;
				text-overflow: clip;
				color: #999;
				font-size: 24rpx;
				padding: 10rpx 40rpx 0 20rpx;
				-webkit-line-clamp: 2;
				-webkit-box-orient: vertical;
			}

			.more {
				position: absolute;
				color: #999;
			}
		}

		.price_wrap {
			padding: 32rpx 20rpx 0rpx 20rpx;
			margin-bottom: 10rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;

			.pr {
				display: inline-block;
				font-size: 32rpx;
				color: #f2270c;
				line-height: 60rpx;
				font-weight: 700;

				text {
					font-size: 52rpx;
				}
			}

			.pic {
				display: flex;

				.jiang {
					width: 120rpx;
					text-align: center;

					image {
						width: 40rpx;
						height: 40rpx;
					}

					text {
						display: block;
						color: #666;
						font-size: 20rpx;
					}
				}
			}
		}

		.title_wrap {
			font-weight: 700;
			line-height: 48rpx;
			font-size: 32rpx;
			padding: 0rpx 20rpx;

			.image {
				width: 51rpx;
				height: 30rpx;
			}
		}
	}
</style>
