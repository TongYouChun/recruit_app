<!-- 谁看过我 -->
<template>
	<view class="history">
		<view class="history_container">
			<!-- <view class="history_label">
				谁看过我
			</view> -->
			<view class="history_Ul">
				<view class="post_li" @click="postDetailsClick()">
					<view class="post_Name">
						<text>产品经理</text>
						<text>10-20K</text>
					</view>
					<view class="post_address">
						<text>北京</text>
						<text>甜水园</text>
						<text>1-3年</text>
						<text>本科</text>
					</view>
					<view class="post_demand">
						<text>企业服务</text>
						<text>广告营销</text>
						<text>需求分析</text>
					</view>
					<view class="recruit_information">
						<view class="recruit_Imgs">
							<image src="../../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode="">
							</image>
						</view>
						<view class="recruit_introduce">
							<view class="name">
								某某在线
							</view>
							<view class="company">
								<text>A轮</text>
								<text>50-150人</text>
								<text>移动互联网</text>
							</view>

						</view>
					</view>
				</view>
				<view class="post_li" @click="postDetailsClick()">
					<view class="post_Name">
						<text>产品经理</text>
						<text>10-20K</text>
					</view>
					<view class="post_address">
						<text>北京</text>
						<text>甜水园</text>
						<text>1-3年</text>
						<text>本科</text>
					</view>
					<view class="post_demand">
						<text>企业服务</text>
						<text>广告营销</text>
						<text>需求分析</text>
					</view>
					<view class="recruit_information">
						<view class="recruit_Imgs">
							<image src="../../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode="">
							</image>
						</view>
						<view class="recruit_introduce">
							<view class="name">
								某某在线
							</view>
							<view class="company">
								<text>A轮</text>
								<text>50-150人</text>
								<text>移动互联网</text>
							</view>

						</view>
					</view>
				</view>
				<view class="post_li" @click="postDetailsClick()">
					<view class="post_Name">
						<text>产品经理</text>
						<text>10-20K</text>
					</view>
					<view class="post_address">
						<text>北京</text>
						<text>甜水园</text>
						<text>1-3年</text>
						<text>本科</text>
					</view>
					<view class="post_demand">
						<text>企业服务</text>
						<text>广告营销</text>
						<text>需求分析</text>
					</view>
					<view class="recruit_information">
						<view class="recruit_Imgs">
							<image src="../../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode="">
							</image>
						</view>
						<view class="recruit_introduce">
							<view class="name">
								某某在线
							</view>
							<view class="company">
								<text>A轮</text>
								<text>50-150人</text>
								<text>移动互联网</text>
							</view>

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
			// 点击进入详情
			postDetailsClick() {
				uni.navigateTo({
					url: '/pages/details/index',
				});
			},
		}
	}
</script>

<style scoped lang="scss">
	.history {
		display: flex;
		flex-direction: column;
		min-height: 100%;

		.history_container {

			// .history_label{
			// 	padding: 0 24upx;
			// 	font-size: 34upx;
			// 	font-weight: 700;
			// 	height: 86upx;
			// 	line-height: 86upx;
			// 	border-bottom: 1upx solid #F1F1F1;
			// }
			.history_Ul {
				display: flex;
				flex-direction: column;

				.post_li {
					margin: 20upx 0;
					padding: 0 5%;
					display: flex;
					flex-direction: column;
					padding-bottom: 20upx;
					border-bottom: 20upx solid #F1F1F1;

					// 岗位名称
					.post_Name {
						display: flex;
						justify-content: space-between;
						height: 45upx;
						line-height: 45upx;

						text:nth-child(1) {
							font-size: 34upx;
							font-weight: 700;
							color: #333;
						}

						text:nth-child(2) {
							font-size: 34upx;
							font-weight: 700;
							color: #FF5733;
						}

					}

					// 地址
					.post_address {
						margin: 10upx 0;
						display: flex;
						align-items: center;
						height: 80upx;

						text {
							padding: 0 10upx;
							font-size: 24upx;
							color: #888;
							height: 26upx;
							line-height: 26upx;
							border-left: 3upx solid #888;
						}

						text:nth-child(1) {
							padding-left: 0;
							border: none;
						}
					}

					// 介绍
					.post_demand {
						display: flex;

						text {
							margin: 10upx 5upx;
							padding: 10upx;
							font-size: 24upx;
							color: #666;
							background-color: #eee;
							border-radius: 5upx;
						}
					}

					// 招聘人 信息
					.recruit_information {
						margin-top: 30upx;
						display: flex;

						.recruit_Imgs {
							width: 100upx;
							height: 100upx;

							image {
								height: 100%;
								width: 100%;
							}
						}

						.recruit_introduce {
							margin-left: 24upx;
							display: flex;
							flex-direction: column;

							.name {
								font-size: 30upx;
								color: #333;
							}

							.company {
								margin: 10upx 0;
								display: flex;
								align-items: center;

								text {
									padding: 0 10upx;
									font-size: 24upx;
									color: #888;
									height: 35upx;
									line-height: 35upx;
									border-left: 3upx solid #888;
								}

								text:nth-child(1) {
									padding-left: 0;
									border: none;
								}
							}
						}
					}
				}

			}
		}
	}
</style>
