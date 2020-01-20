<template>
	<view class="content">
		<view class="search">
			<image class="menu" src="../../static/image/can.png"></image>
			<uni-search-bar class="bar" radius="50" bgColor="#ffffff" cancelButton="none" placeholder="搜索"></uni-search-bar>
			<text class="deng">登陆</text>
		</view>
		<view>
			<scroll-view scroll-y="true" class="scroll">
				<view class="scr-view">
					<swiper indicator-dots="true" indicator-active-color="red" circular="true" autoplay="true">
						<swiper-item v-for="(item,index) in list" :key="index">
							<image :src="item.path" mode="" class="image"></image>
						</swiper-item>
					</swiper>
				</view>
				<view class="nav_bar">
					<view class="nav_margin">
						<view class="row">
							<view class="cell" v-for="(item,index) in 5" :key="index">
								<image src="../../static/image/sp1.jpg"></image>
								<text>京东超市</text>
							</view>
						</view>
					</view>
				</view>
				<!-- 秒杀 -->
				<view class="seckill">
					<view class="container">
						<view class="sec_kill">
							<view class="title_wrap">
								<a><text class="title">京东秒杀</text> <text class="chang">10点场</text> <text class="time">1:18:18</text> </a>
								<a class="more">
									更多秒杀>
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
						<image src="../../static/image/jian1.png" class="tui"></image>
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
					<view class="ex2">
						<view class="content">
							<view class="export_footer">
								<view class="ex_margin">
									<view class="ex_height">
										<view class="ex_row">
											<view class="el_item" v-for="(item,index) in 4" :key="index">
												<view class="real_show">
													<view class="title">
														<text class="text">免息星球</text>
														<text class="bt">白条免息购</text>
													</view>
													<view class="image">
														<image src="../../static/image/sp1.jpg"></image>
													</view>
												</view>
											</view>
										</view>
									</view>
								</view>
							</view>
							<view class="ex_footer2">
								<view class="ex2_margin">
									<view class="ex2_height">
										<view class="ex2_row">
											<view class="ex2_item" v-for="(item,index) in 4" :key="index">
												<view class="real_show">
													<view class="tit">
														<text class="text">排行榜</text>
														<text class="re">热销推荐</text>
													</view>
													<view class="image">
														<image src="../../static/image/sp2.jpg" style="width: 120rpx;height: 120rpx;"></image>
													</view>
												</view>
											</view>
										</view>
									</view>
								</view>
							</view>
						</view>
					</view>
				</view>
				<!-- 为你推荐 -->
				<view class="live_footer">
					<view class="li_margin">
						<view class="li_padding">
							<image src="../../static/image/tui.png"></image>
						</view>
					</view>
					<view class="live">
						<view class="row">
							<view class="cell" v-for="(item,index) in 10" :key="index">
								<view class="similar-product">
									<image class="pic" src="../../static/image/cp1.jpg"></image>
									<view class="text">
										<image src="../../static/image/huo.png"></image>
										<text>海尔（Haier）全自动波轮洗衣机家用洗衣机租房宿舍专用 安心童锁强劲动力超净洗 8公斤新品上市</text>
									</view>
									<view class="info">
										<text class="price">$ <text class="num">799</text></text>
										<text class="button">看相似</text>
									</view>
									<view class="footer"></view>
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
						path: '../../static/image/lun1.jpg',
					},
					{
						path: '../../static/image/lun2.jpg',
					},
					{
						path: '../../static/image/lun3.jpg',
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
	/deep/.uni-scroll-view {
		background-color: #fff;

	}

	/deep/.uni-scroll-view::-webkit-scrollbar {
		/* 隐藏滚动条，但依旧具备可以滚动的功能 */
		display: none
	}

	.content {

		.nav_bar {
			width: 100%;
			overflow: hidden;
			background: #7c0700;

			.nav_margin {
				.row {
					display: flex;

					.cell {
						margin-top: 10rpx;
						text-align: center;
						width: 150rpx;
						height: 148rpx;

						image {
							margin-top: 10rpx;
							border-radius: 50%;
							width: 80rpx;
							height: 80rpx;
						}

						text {
							color: #fff;
							display: block;
						}
					}
				}
			}

		}

		.search {
			width: 100%;
			background: #7c0700;
			display: flex;
			align-items: center;

			.menu {
				margin-left: 20rpx;
				width: 60rpx;
				height: 60rpx;
				color: #fff;
			}

			.deng {
				color: #fff;
			}

			.bar {
				background: #7c0700;
				width: 550rpx;
				border: none;
			}
		}


		.scroll {
			height: calc(100vh - 102px); //135px

			.live_footer {
				background-color: #f0f2f5;
				overflow: hidden;

				.live {
					margin: 0rpx 20rpx 20rpx 20rpx;

					.row {
						width: 100%;
						display: flex;
						overflow: hidden;
						flex-wrap: wrap;
						position: relative;

						.cell {
							width: 351rpx;
							padding-right: 4rpx;
							padding-bottom: 8rpx;

							.similar-product {
								background-color: #fff;
								font-size: 0;
								padding-bottom: 0;

								.pic {
									display: inline-block;
									width: 352rpx;
									height: 352rpx;
								}

								.text {
									height: 62rpx;
									margin-top: 10rpx;
									margin-bottom: 6rpx;
									padding: 0 8rpx;
									font-size: 26rpx;
									word-break: break-all;
									text-overflow: ellipsis;
									overflow: hidden;
									color: #232326;
									display: -webkit-box;
									-webkit-line-clamp: 2;
									-webkit-box-orient: vertical;
									line-height: 32rpx;

									image {
										margin-right: 8rpx;
										width: 63.12rpx;
										height: 26rpx;
									}
								}

								.info {
									height: 52rpx;
									font-size: 26rpx;
									display: flex;
									justify-content: space-between;

									.price {
										position: relative;
										top: 2rpx;
										color: #f23030;
										display: inline-block;
										padding: 0 10rpx 0 8rpx;
										height: 50rpx;
										line-height: 50rpx;

										.num {
											font-size: 32rpx;
										}
									}

									.button {
										margin-right: 20rpx;
										display: flex;
										width: 98rpx;
										height: 48rpx;
										font-size: 24rpx;
										color: #686868;
										justify-content: center;
										align-items: center;
										border: 1px solid #bfbfbf;
										border-radius: 8rpx;
									}
								}

								.footer {
									height: 52rpx;
								}
							}
						}
					}
				}

				.li_margin {
					margin-top: 20rpx;

					.li_padding {
						height: 70rpx;
						margin: 0rpx 20rpx;

						image {
							width: 710rpx;
							height: inherit;
						}
					}


				}
			}

			.expo {
				background-color: #7c0700;

				.pic {
					height: 70rpx;

					image {
						width: 100%;
						height: inherit;
					}
				}

				.ex2 {
					background-color: #7c0700;
					overflow: hidden;

					.content {
						margin: 0rpx 20rpx 20rpx 20rpx;

						.ex_footer2 {
							background-color: #7c0700;

							.ex2_margin {
								.ex2_height {
									height: 224rpx;

									.ex2_row {
										background: #fff;
										font-size: 100%;
										width: 100%;
										display: flex;
										border-bottom-left-radius: 10rpx;
										border-bottom-right-radius: 10rpx;

										.ex2_item {
											width: 177rpx;
											border-right: 1px solid #7c0700;

											.real_show {
												padding: 13rpx 0rpx 10rpx 20rpx;

												.tit {
													.text {
														background: linear-gradient(90deg, #FF2A2A, #F139D2);
														color: transparent;
														-webkit-background-clip: text;
														font-size: 32rpx;
													}

													.re {
														font-size: 24rpx;
														color: #222222;
														display: block;
													}
												}
											}
										}
									}
								}

							}
						}

						.export_footer {
							background-color: #7c0700;
							border-bottom: 2rpx solid #7c0700;

							.ex_margin {
								.ex_height {
									height: 224rpx;

									.ex_row {
										font-size: 100%;
										width: 100%;
										background-color: #fff;
										border-top-left-radius: 10rpx;
										border-top-right-radius: 10rpx;
										display: flex;

										.el_item {
											border-right: 1px solid #7c0700;
											width: 177rpx;

											.real_show {
												padding: 13rpx 0rpx 10rpx 20rpx;

												.title {
													.text {
														background: linear-gradient(90deg, #FF2A2A, #F139D2);
														color: transparent;
														-webkit-background-clip: text;
														font-size: 32rpx;
													}

													.bt {
														font-size: 24rpx;
														color: #222222;
														display: block;
													}
												}

												.image {
													image {
														width: 120rpx;
														height: 120rpx;
													}
												}
											}
										}
									}
								}
							}
						}
					}
				}



			}

			.dong {
				background-color: #7c0700;

				.content {
					margin: 0rpx 20rpx 0rpx 20rpx;
					border-radius: 10rpx;
					background: #fff;
					box-sizing: border-box;

					.footer-98 {
						background-color: #7c0700;

						.fit {
							height: 240rpx;

							.fit_item {
								width: 100%;
								background-color: #fff;
								font-size: 100%;
								display: flex;
								border-bottom-left-radius: 10rpx;
								border-bottom-right-radius: 10rpx;

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
					height: 70rpx;

					image {
						width: 100%;
						height: inherit;
					}
				}
			}

			.shop3 {
				background-color: #7c0700;

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
				height: 300rpx;
				display: flex;
				justify-content: center;
				overflow: hidden;
				background-image: url(../../static/image/bg2.jpg);
				background-size: cover;
				background-repeat: no-repeat;
				background-position: center center;

				swiper {
					margin-top: 10rpx;
					width: 700rpx;
					height: 278rpx;

					swiper-item {
						border-radius: 10rpx;
						.image {
							width: 700rpx;
							height: 278rpx;
						}
					}
				}
			}

			.people {
				background-color: #7c0700;
				overflow: hidden;

				.the-container {
					display: flex;
					margin: 0px 20rpx;

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
				overflow: hidden;
				background-color: #7c0700;

				.container {
					margin: 0 24rpx 24rpx 24rpx;
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

							.chang {
								margin: 0 10rpx 0 10rpx;
								font-weight: 700;
								font-size: 24rpx;
								display: inline-block;
							}

							.time {
								font-size: 24rpx;
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
