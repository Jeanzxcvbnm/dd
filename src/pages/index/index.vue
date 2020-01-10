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
				<view class="miao">
					<view class="title">
						<view>
							<text class="name">京东秒杀</text>
						</view>
						<view>
							<text class="qiang">更多好货限时疯抢&gt;</text>
						</view>
					</view>
					<scroll-view scroll-x="true" show-scrollbar="false">
						<view class="mlist">	
							<view class="lst" v-for="(item,index) in miao" :key="index">
								<image :src="item.url" class="mt"></image>
								<view><text class="xian">{{item.old}}</text></view>
								<view><text class="yuan">{{item.news}}</text></view>
							</view>
						</view>
					</scroll-view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script lang="ts">
	//import {Vue,Component} from 'vue-property-decorator';
	import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue'
	export default {
		components: {
			uniSearchBar
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
		.miao {
			.title {
				display: flex;
				justify-content: space-between;
				padding: 0px 10rpx 0rpx 10rpx;

				.name {
					font-size: 15px;
					font-weight: 600;
				}

				.qiang {
					font-size: 24rpx;
					color: #999999;
				}
			}

			.mlist {
				display: flex;

				.lst {
					width: 170rpx;
					text-align: center;
					padding-right: 20rpx;

					.mt {
						width: 160rpx;
						height: 160rpx;
					}

					.xian {
						color: red;

					}

					.yuan {
						font-size: 22rpx;
						color: #999999;
						text-decoration: line-through;
					}
				}

			}
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
			height: 1130rpx;

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
		}

		.image {
			width: 750rpx;
		}
	}
</style>
