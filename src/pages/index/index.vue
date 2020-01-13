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
							<view class="shop_list" v-for="(item,index) in dd" :key="index">
								<view class="list">
									<view class="title"><text>{{item.title}}</text></view>
									<view class="img">
										<image :src="item.url"></image>
									</view>
									<view class="footer"> <text>{{item.footer}}</text></view>
								</view>
							</view>
						</view>
					</view>
				</view>
				<view class="shop2">
					<view class="container">
						<view class="shop2_list" v-for="(item,index) in dd2" :key="index">
							<view class="image">
								<image :src="item.url"></image>
							</view>
							<view class="jian">
								<text>{{item.jian}}</text>
							</view>
							<view class="footer">
								<text>{{item.title}}</text>
							</view>
						</view>
					</view>
				</view>
				<view class="shop3">
					<view class="container">
						<view class="shop2_list" v-for="(item,index) in dd2" :key="index">
							<view class="image">
								<image :src="item.url"></image>
							</view>
							<view class="jian">
								<text>{{item.jian}}</text>
							</view>
							<view class="footer">
								<text>{{item.title}}</text>
							</view>
						</view>
					</view>
				</view>
				<!-- 东家小院 -->
				<view class="dong">
					<view class="fir_tit">
						<image src="../../static/image/dong.png"></image>
					</view>
					<view class="content">
						<view class="footer">
							<view class="the-container" v-for="(item,index) in 2" :key="index">
								<view class="first">
									<text class="j_tit">精美客厅</text>
									<text class="j_ke">打造专属的精美客厅</text>
								</view>
								<view class="second">
									<image src="../../static/image/ke1.jpg"></image>
									<image src="../../static/image/ke2.jpg"></image>
								</view>
							</view>
						</view>
						<view class="footer-98">
							<view class="fit">
								<view class="fit_item">
									<view class="cell" v-for="(item,index) in 4" :key="index">
										<view class="real_show">
											<view>
												<view><text class="title">自拍必备</text></view>
												<view><text class="con">美颜拍摄</text></view>
											</view>
											<view class="img">
												<image src="../../static/image/sp1.jpg"></image>
											</view>
										</view>
									</view>
								</view>
							</view>
						</view>
					</view>
				</view>
				<!-- 每日逛 -->
				<view class="expo">
					<view class="pic">
						<image src="../../static/image/gg.png"></image>
					</view>
					<view class="expo_footer">
						<view class="foot_margin">
							<view class="footer_bottom">
								<view class="fit">
									<view class="item">
										<view class="real-show">
											<view class="text">
												<view><text>免息星球</text></view>
												<view><text>白条免息够</text></view>
												<view>
													<image src="../../static/image/sp1.jpg" style="width: 120rpx;height: 120rpx;"></image>
												</view>
											</view>
										</view>
									</view>
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
				],
				dd: [{
						url: '../../static/image/one.jpg',
						title: '曲面屏手机',
						footer: '热销爆款'
					},
					{
						url: '../../static/image/two.jpg',
						title: '曲面屏手机',
						footer: '热销爆款'
					},
					{
						url: '../../static/image/three.jpg',
						title: '曲面屏手机',
						footer: '热销爆款'
					},
					{
						url: '../../static/image/four.jpg',
						title: '曲面屏手机',
						footer: '热销爆款'
					}
				],
				dd2: [{
						url: '../../static/image/sp1.jpg',
						jian: '满500减60',
						title: '品质爆款'
					},
					{
						url: '../../static/image/sp2.jpg',
						jian: '满500减60',
						title: '品质爆款'
					},
					{
						url: '../../static/image/sp3.jpg',
						jian: '满500减60',
						title: '品质爆款'
					}, {
						url: '../../static/image/sp1.jpg',
						jian: '满500减60',
						title: '品质爆款'
					}
				]
			}
		}
	}
</script>

<style lang="scss">
	.content {
		.text {
			background: linear-gradient(90deg, #45CAFF, #1471FB);
			color: transparent;
			-webkit-background-clip: text;
		}

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

			.expo {
				background-color: #7c0700;

				.pic {
					image {
						width: 100%;
						height: 70rpx;
					}
				}

				.expo_footer {
					background-color: #7c0700;

					.foot_margin {
						margin: 0rpx 20rpx 20rpx 20rpx;

						.footer_bottom {
							border-bottom: 1px solid #7c0700;

							.fit {
								height: 240rpx;
								.item{
									background: #fff;
								}
							}
						}
					}
				}
			}

			.dong {
				background-color: #7c0700;

				.content {
					margin: 20rpx;
					border-radius: 10rpx;
					background: #fff;

					.footer-98 {
						background-color: #7c0700;

						.fit {
							height: 240rpx;

							.fit_item {
								width: 100%;
								background-color: #fff;
								font-size: 100%;
								display: flex;

								.cell {
									width: 178rpx;
									border-right: 2rpx solid #7c0700;


									.real_show {
										padding: 13rpx 0rpx 10rpx 20rpx;

										.title {
											color: black;
											font-size: 32rpx;
											font-weight: 700;
										}

										.con {
											font-size: 24rpx;
											color: #666771;
										}

										.img {
											image {
												width: 120rpx;
												height: 120rpx;
											}
										}
									}
								}

								.cell:last-child {
									border-right: none;
								}

							}
						}
					}

					.footer {
						border-bottom: 1px solid #7c0700;
						display: flex;
						padding: 13rpx 0rpx 10rpx 0rpx;

						.the-container {
							width: 352rpx;
							height: 216rpx;
							border-right: 1px solid #7c0700;

							.first {

								padding-left: 18rpx;

								.j_tit {
									font-size: 32rpx;
									color: transparent;
									background: linear-gradient(90deg, #45CAFF, #1471FB);
									display: inline-block;
									-webkit-background-clip: text;
								}

								.j_ke {
									color: #666771;
									font-size: 24rpx;
									display: block;
								}
							}

							.second {
								padding: 0rpx 14rpx 0rpx 14rpx;

								image {
									margin: 11rpx 14rpx 0rpx 14rpx;
									width: 120rpx;
									height: 120rpx;
								}
							}
						}

						.the-container:last-child {
							border-right: none;
						}
					}
				}

				.fir_tit {
					image {
						width: 100%;
						height: 70rpx;
					}
				}
			}

			.shop3 {
				background-color: #7c0700;
				padding-bottom: 20rpx;

				.container {
					display: flex;
					padding-top: 2rpx;

					.shop2_list {
						margin-left: 10rpx;
						background-image: url(../../static/image/bg3.png);
						background-repeat: no-repeat;
						background-size: cover;
						width: 176rpx;
						height: 240rpx;

						.jian {
							display: flex;
							justify-content: center;

							text {
								color: #fff;
								font-size: 24rpx;
							}
						}

						.footer {
							text-align: center;

							text {
								color: #fff;
							}
						}

						.image {
							display: flex;
							justify-content: center;
							align-items: center;
							width: 174rpx;
							height: 146rpx;

							image {
								padding-top: 10rpx;
								width: 120rpx;
								height: 124rpx;
							}
						}
					}
				}

			}

			.shop2 {
				background-color: #7c0700;

				.container {
					display: flex;
					padding-top: 24rpx;

					.shop2_list {
						margin-left: 10rpx;
						background-image: url(../../static/image/bg3.png);
						background-repeat: no-repeat;
						background-size: cover;
						width: 176rpx;
						height: 240rpx;

						.jian {
							display: flex;
							justify-content: center;

							text {
								color: #fff;
								font-size: 24rpx;
							}
						}

						.footer {
							text-align: center;

							text {
								color: #fff;
							}
						}

						.image {
							display: flex;
							justify-content: center;
							align-items: center;
							width: 174rpx;
							height: 146rpx;

							image {
								padding-top: 10rpx;
								width: 120rpx;
								height: 124rpx;
							}
						}
					}
				}

			}

			.shop {
				background-color: #7c0700;

				.the-container {
					.container {
						display: flex;

						.shop_list {
							margin-left: 10rpx;
							background-size: cover;
							width: 176rpx;
							height: 240rpx;
							background-image: url(../../static/image/bg2.png);

							.list {
								width: 174rpx;
								height: 240rpx;

								.img {
									text-align: center;

									image {
										width: 120rpx;
										height: 116rpx;
									}
								}

								.title {
									text-align: center;
									height: 56rpx;

									text {
										color: #fff;
									}
								}

								.footer {
									text-align: center;
									color: #fff;
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
