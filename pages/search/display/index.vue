<!-- 搜索显示结果 -->
<template>
	<view class="search_display">
		<!-- <view class="display_container"> -->
			<!-- 搜索 -->
			<view class="isplay_top">
				<view class="search_input" @click="searchClick">
					<view class="input_Icon"></view>
					<view class="input_txet">
						搜索职位/公司/内容
					</view>
				</view>
			</view>
			<!-- 显示内容 -->
			<view class="display_content">
				<view class="display_Ul" v-if="estimate">
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
				
				<view class="noResult" v-else>
					<image src="../../../static/noResult.png" mode=""></image>
				</view>
			</view>
		<!-- </view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				estimate:true
			}
		},
		methods:{
			// 点击进入详情
			postDetailsClick() {
				uni.navigateTo({
					url: '/pages/details/index',
				});
			},
			// 搜索
			searchClick () {
				uni.navigateTo({
					url: '/pages/search/index',
				});
			},
		}
	}
</script>

<style scoped lang="scss">
	.search_display{
		height: 100%;
		display: flex;
		flex-direction: column;
		background-color: #F1F1F1;
		.isplay_top{
			height: 100upx;
			display: flex;
			justify-content: space-between;
			padding: 0 8%;
			align-items: center;
			background-color: #FFFFFF;
			// 搜索框
			.search_input{
				width: 100%;
				display: flex;
				height: 70upx;
				background-color: #F1F1F1;
				border-radius: 35upx;
				align-items: center;
				padding: 0 25upx;
				.input_Icon{
					width: 40upx;
					height: 40upx;
					background-image: url(../../../static/Icon/sousuo.png);
					background-size: 100% 100%;
				}
				.input_txet{
					flex: 1;
					font-size: 28upx;
					display: flex;
					align-items: center;
					color: #999;
					margin-left: 15upx;
					height: 65upx;
				}
			}
		}
		.display_content{
			flex: 1;
			overflow-y: auto;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
			.noResult{
				border-top: 1upx solid #e1e1e1;
				flex: 1;
				display: flex;
				flex-direction: column;
				align-items: center;
				justify-content: center;
				image{
					height: 300upx;
					width: 300upx;
				}
			}
			.display_Ul{
				border-top: 1upx solid #e1e1e1;
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
