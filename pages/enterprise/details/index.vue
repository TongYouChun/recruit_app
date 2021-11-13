<!-- 企业详情 -->
<template>
	<view class="enterprise_details">
		<view class="enterprise_details_top">
			<image src="https://img2.baidu.com/it/u=2530977894,3310522575&fm=26&fmt=auto&gp=0.jpg" mode=""></image>
		</view>
		<view class="enterprise_details_content">
			<view class="enterprise_details_Name">
				<view class="name">
					百度贴吧企业
				</view>
				<view class="number">
					人数：20-30人
				</view>
				<view class="introduce">
					介绍：尘文化传媒拥有影视制作, 设计策划，平面设计 , 媒体运营。定制承接
				</view>
			</view>
			<view class="address">
				安徽省滁州市世纪大道950号(扬子街道滁州市经济技术开发区城东工业园世纪大道与徽州路交叉口东南角)
			</view>
			<view class="position">
				<view class="position_title">
					在招职位
				</view>
				<view class="position_li" @click="postClick()">
					<view class="name_text">
						<view class="name">
							文员
						</view>
						<view class="text">
							1-2 年 大专
						</view>
					</view>
					<view class="Price_text">
						<view class="Price">
							3k - 5k/月
						</view>
						<view class="text">
							2021-8-6
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods:{
			// 岗位详情
			postClick () {
				uni.navigateTo({
					url: '/pages/details/index',
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.enterprise_details{
		display: flex;
		flex-direction: column;
		min-height: 100%;
		background-color: #F1F1F1;
		.enterprise_details_top{
			display: flex;
			height: 350upx;
			width: 100%;
			image{
				height: 350upx;
				width: 100%;
			}
		}
		.enterprise_details_content{
			display: flex;
			flex-direction: column;
			margin-top: 5upx;
			background-color: #FFFFFF;
			.enterprise_details_Name{
				display: flex;
				flex-direction: column;
				padding: 10upx 6% 20upx 6%;
				border-bottom: 5upx solid #F1F1F1;
				.name{
					margin-top: 10upx;
					font-size: 30upx;
					font-weight: 700;
					color: #333333;
				}
				.introduce{
					margin-top: 20upx;
					font-size: 28upx;
					color: #666;
				}
				.number{
					margin-top: 10upx;
					font-size: 26upx;
					color: #666;
				}
			}
			.address{
				display: flex;
				flex-direction: column;
				padding: 20upx 6%;
				font-size: 28upx;
				color: #333333;
				border-bottom: 15upx solid #F1F1F1;
			}
			.position{
				display: flex;
				flex-direction: column;
				padding: 0 6%;
				.position_title{
					font-size: 32upx;
					font-weight: 700;
					color: #333;
					height: 65upx;
					display: flex;
					align-items: center;
					border-bottom: 2upx solid #F1F1F1;
				}
				.position_li{
					display: flex;
					justify-content: space-between;
					border-bottom: 1upx solid #F1F1F1;
					.name_text{
						height: 140upx;
						display: flex;
						flex-direction: column;
						justify-content: space-around;
						.name{
							font-size: 32upx;
							color: #333333;
							font-weight: 700;
						}
						.text{
							font-size: 24upx;
							color: #999999;
						}
					}
					.Price_text{
						height: 140upx;
						display: flex;
						flex-direction: column;
						justify-content: space-around;
						.Price{
							font-size: 34upx;
							color: #f00;
							font-weight: 700;
						}
						.text{
							font-size: 24upx;
							color: #999999;
							text-align: right;
						}
					}
				}
			}
		}
	}
</style>
