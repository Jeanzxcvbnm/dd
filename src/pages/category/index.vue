<template>
	<view class="cate">
		<view class="search">
			<view class="search_margin">
				<text class="text" @click="goback">
					< </text> <uni-search-bar class="bar" radius="50" bgColor="#ffffff" cancelButton="none" placeholder="搜索">
						</uni-search-bar>
						<image src="../../static/image/more.png"></image>
			</view>
		</view>
		<view class="cate_body">
			<scroll-view scroll-y="true" class="scroll">
				<view class="root_list">
					<view class="item" v-for="(item,index) in 20" :key="index">
						<view class="real_show">
							<text>热门推荐</text>
						</view>
					</view>
				</view>
			</scroll-view>
			<scroll-view scroll-y="true" class="scroll2">
				<view class="scroll_margin">
					<view class="title">
						<text class="a">浏览足迹</text>
						<text class="b">清空</text>
					</view>
					<view class="row">
						<view class="item" v-for="(item,index) in 20" @click="goDetails">
							<image src="../../static/image/chui.png"></image>
							<text>吹风机</text>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>

	</view>
</template>

<script lang="ts">
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue';
	export default {
		components: {
			uniSearchBar
		},
		data() {
			return {

			}
		},
		methods: {
			goback() {
				
			},
			goDetails() {
				uni.navigateTo({
					url:"../details/index"
				})
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

	.cate {

		.cate_body {
			height: auto;
			min-height: 100%;
			display: flex;

			.scroll {
				height: calc(100vh - 102px); //135px  
				overflow: hidden;
				width: 172rpx;

				.root_list {
					.item {
						background: #f8f8f8;
						width: inherit;

						.real_show {
							width: inherit;
							height: 92rpx;
							line-height: 82rpx;
							text-align: center;
						}

					}
				}
			}

			.scroll2 {
				height: calc(100vh - 102px); //135px
				overflow: hidden;
				width: calc(100vw - 86px);

				.scroll_margin {
					margin: 38rpx 14rpx 0 14rpx;

					.title {
						display: flex;
						justify-content: space-between;

						.a {
							font-weight: 700;
						}

						.b {
							color: #999;
						}
					}

					.row {
						display: flex;
						margin-top: 18rpx;
						padding: 14rpx 20rpx 0;
						flex-wrap: wrap;

						.item {
							width: 167rpx;
							height: 214rpx;
							text-align: center;

							image {
								width: 140rpx;
								height: 140rpx;
							}

							text {
								display: block;
							}
						}


					}
				}
			}
		}

		.search {
			width: 100%;
			overflow: hidden;
			border-bottom: 1px solid #e5e5e5;

			.search_margin {
				margin: 0 20rpx;
				display: flex;
				align-items: center;
				justify-content: space-between;

				.text {
					display: inline-block;
					color: #666;
					font-size: 40rpx;
				}

				image {
					width: 40rpx;
					height: 40rpx;
				}

				.bar {
					width: 550rpx;
					border: none;
				}
			}

		}


	}
</style>
