<template>
	<view class="content">
		<view class="search">
			<uni-search-bar radius="50" bgColor="#ffffff" cancelButton="none" placeholder="搜索"></uni-search-bar>
		</view>
		<view>
			<scroll-view scroll-y="true" class="scroll">
				<view class="scr-view">
					<swiper indicator-dots="true" indicator-active-color="red" circular="true">
						<swiper-item v-for="(item,index) in list" :key="index">
							<image :src="item.path" mode="" class="image"></image>
						</swiper-item>
					</swiper>
				</view>
				<view class="wrappe-box">
					<view class="item" v-for="(item,index) in nav" :key="index">
						<a>
							<view>
								<image class="image"></image>
							</view>
							<view><text class="text">{{item.name}}</text></view>
						</a>
					</view>
				</view>
				<!-- 秒杀 -->
				<view class="seckill">
					<view class="container">
						<view class="sec_kill">
							<view class="title_wrap">
								<a><text class="title">京东秒杀</text> 10点场 1:18:18</a>
								<a class="more">
									更多秒杀
									<uni-badge text=">" size="small" type="error"></uni-badge>
								</a>
							</view>
							<scroll-view class="silder" scroll-x="true">
								<view class="the-container">
									<view class="container" v-for="(item,index) in miao" :key="index">
										<image class="image" :src="item.url"></image>
										<view class="priceCon">
											<view class="xian">{{item.news}}</view>
											<view class="yuan">{{item.old}}</view>
										</view>
									</view>
								</view>
							</scroll-view>
						</view>
					</view>
				</view>
				<!-- 新人 -->
				<view class="people">
					<view class="the-container">
						<image class="img1" src="../../static/image/new1.png"></image>
						<image class="img2" src="../../static/image/new2.png"></image>
					</view>
				</view>
				<!-- 今日主推 -->
				<view class="recommend">
					<view class="the-container">
						<image src="../../static/image/tui.png" class="tui"></image>
						<image src="../../static/image/da.png" class="da"></image>
					</view>
				</view>
				<!-- 年货大街 -->
				<view class="goods">
					<view class="container">
						<image src="../../static/image/nian.png" class="nian"></image>
					</view>
				</view>
				<view class="shop">
					<view class="the-container">
						<view class="container">
							<view class="shop_list">
								<view class="list">
									<view><text class="title">曲面屏手机</text></view>
									<view>
										<image src="../../static/image/sp1.jpg" style="width: 124rpx;height: 124rpx;"></image>
									</view>
									<view> <text class="footer">热销爆款</text></view>
								</view>
							</view>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script lang="ts">
	//import {Vue,Component} from 'vue-property-decorator';
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue';
	import uniBadge from '@/components/uni-badge/uni-badge.vue'
	export default {
		components: {
			uniSearchBar,
			uniBadge
		},
		data() {
			return {
				miao: [{
						url: '../../static/image/sp1.jpg',
						old: '￥999',
						news: '￥499'
					},
					{
						url: '../../static/image/sp2.jpg',
						old: '￥999',
						news: '￥499'
					},
					{
						url: '../../static/image/sp3.jpg',
						old: '￥999',
						news: '￥499'
					},
					{
						url: '../../static/image/sp1.jpg',
						old: '￥999',
						news: '￥499'
					},
					{
						url: '../../static/image/sp2.jpg',
						old: '￥999',
						news: '￥499'
					},
					{
						url: '../../static/image/sp3.jpg',
						old: '￥999',
						news: '￥499'
					}
				],
				list: [{
						path: '../../static/image/one.jpg',
					},
					{
						path: '../../static/image/two.jpg',
					},
					{
						path: '../../static/image/three.jpg',
					},
					{
						path: '../../static/image/four.jpg',
					}
				],
				nav: [{
						name: '京东超市',
						path: '',
						href: '#'
					},
					{
						name: '京东家电',
						path: '',
						href: '#'
					},
					{
						name: '京东超市',
						path: '',
						href: '#'
					},
					{
						name: '京东超市',
						path: '',
						href: '#'
					},
					{
						name: '京东超市',
						path: '',
						href: '#'
					},
				]
			}
		}
	}
</script>

<style lang="scss">
	.content {
		.wrappe-box {
			height: 166.8rpx;
			overflow: hidden;
			padding: 10rpx;
			display: flex;

			.item {
				width: 220rpx;
				height: 113rpx;
				text-align: center;

				.image {
					width: 100rpx;
					height: 100rpx;
					background-color: red;
					border-radius: 50%;
				}

				.text {
					color: #666666
				}
			}

		}

		.search {
			width: 100%;
			background: red;
			display: flex;
			justify-content: center;
		}

		.uni-searchbar {
			background: red;
			width: 550rpx;
			border: none;
		}

		.scroll {
			height: 1420rpx;

			.shop {
				background-color: #7c0700;

				.the-container {
					.container {
						.shop_list {
							background-size: cover;
							width: 174rpx;
							height: 240rpx;
							background-image: url(../../static/image/bg2.png);

							.list {
								width: 174rpx;
								height: 240rpx;
								.title{
								
								}
							}
						}

						.image {}
					}
				}
			}

			.goods {
				background-color: #7c0700;

				.container {
					line-height: 108rpx;

					.nian {
						width: 100%;
						height: 108rpx;
					}
				}
			}

			.recommend {
				background-color: #7c0700;

				.the-container {
					.tui {
						width: 100%;
						height: 72.54rpx;
					}

					.da {
						height: 200rpx;
						width: 100%;
					}
				}
			}



			.scr-view {
				height: 333.96rpx;
				display: flex;
				justify-content: center;

				swiper {
					border-radius: 5px;
					width: 750rpx;
					height: 300rpx;
				}
			}

			.people {
				background-color: #7c0700;

				.the-container {
					display: flex;
					padding: 0rpx 24rpx 24rpx 24rpx;

					.img1 {
						width: 378rpx;
						height: 254rpx;
						border-top-left-radius: 14rpx;
						border-bottom-left-radius: 14rpx;
					}

					.img2 {
						width: 378rpx;
						height: 254rpx;
						border-top-right-radius: 14rpx;
						border-bottom-right-radius: 14rpx;
					}
				}
			}

			.seckill {
				background-color: #7c0700;

				.container {
					padding: 24rpx;
					position: relative;

					.sec_kill {
						border-radius: 12rpx;
						box-shadow: 0rpx 2rpx 2rpx #f2f2f2;
						background: #FFFFFF;

						.title_wrap {
							padding: 0rpx 20rpx 0rpx 20rpx;
							height: 72.54rpx;
							display: flex;
							line-height: 72.54rpx;
							justify-content: space-between;

							.title {
								font-size: 34rpx;
								font-weight: 600;
							}

							.more {
								display: flex;
								align-items: center;
								color: #f23030;
							}
						}

						.silder {
							.the-container {
								width: 200rpx;
								display: flex;

								.container {
									.image {
										width: 162rpx;
										height: 140rpx;
									}

									.priceCon {
										text-align: center;

										.xian {
											font-weight: 600;
											color: #f23030;
										}

										.yuan {
											font-size: 24rpx;
											color: #999999;
											text-decoration: line-through;
										}
									}
								}
							}
						}
					}
				}
			}
		}

		.image {
			width: 750rpx;
		}
	}
</style>
