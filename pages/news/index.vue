<!-- 消息页面 -->
<template>
	<view class="news">
		<view class="news_top">
			<view class="news_see">
				<view class="news_top_li" @click="DeliveryClick()">
					<view class="news_Imgs">
						<image src="../../static/Icon/icon_1vi6b/toudixiang.png" mode=""></image>
					</view>
					<view class="news_Name" >
						我的投递
					</view>
				</view>
				<view class="news_top_li" @click="historyClick()">
					<view class="news_Imgs_see">
						<image src="../../static/Icon/icon_1vi6b/202-copy.png" mode=""></image>
					</view>
					<view class="news_Name">
						谁看过我
					</view>
				</view>
			</view>
		</view>
		<view class="news_bottom">
			<view class="news_label">
				聊天
			</view>
			<view class="news_bottom_ul">
				<view class="news_bottom_li" @click="startChatting">
					<view class="news_li_left">
						<view class="news_li_Imgs">
							<image src="../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode=""></image>
						</view>
						<view class="news_li_Name">
							<view class="Name">
								喀喀喀
							</view>
							<view class="news_li_news">
								hi,hhhhhhhhhhhhhhhh
							</view>
						</view>
					</view>
					<view class="news_li_right">
						<view class="news_li_date">
							2021/8/9
						</view>
					</view>
				</view>
				<view class="news_bottom_li" @click="startChatting">
					<view class="news_li_left">
						<view class="news_li_Imgs">
							<image src="../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode=""></image>
						</view>
						<view class="news_li_Name">
							<view class="Name">
								喀喀喀
							</view>
							<view class="news_li_news">
								hi,hhhhhhhhhhhhhhhh
							</view>
						</view>
					</view>
					<view class="news_li_right">
						<view class="news_li_date">
							2021/8/9
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
			// 投递
			DeliveryClick () {
				uni.navigateTo({
					url: '/pages/news/Delivery/index',
				});
			},
			// 谁看过我
			historyClick () {
				uni.navigateTo({
					url: '/pages/news/history/index',
				});
			},
			// 开始聊天
			startChatting () {
				uni.navigateTo({
					url: '/pages/news/chat/index',
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.news{
		min-height: 100%;
		background-color: #F1F1F1;
		.news_top{
			width: 100%;
			height: 160upx;
			background-color: #32B89B;
			position: relative;
			.news_see{
				position: absolute;
				bottom: -70upx;
				left: 0;
				right: 0;
				margin: auto;
				width: 80%;
				height: 150upx;
				background-color: #FFFFFF;
				box-shadow: 0upx 10upx 10upx rgba(230,230,230,0.5);
				border-radius: 15upx;
				display: flex;
				justify-content: space-around;
				align-items: center;
				.news_top_li{
					display: flex;
					flex-direction: column;
					align-items: center;
					.news_Imgs{
						height: 80upx;
						width: 80upx;
						background-color: #007AFF;
						display: flex;
						justify-content: center;
						align-items: center;
						border-radius: 50%;
						image{
							height: 40upx;
							width: 40upx;
						}
					}
					.news_Imgs_see{
						height: 80upx;
						width: 80upx;
						background-color: #E9B449;
						display: flex;
						justify-content: center;
						align-items: center;
						border-radius: 50%;
						image{
							height: 40upx;
							width: 40upx;
						}
					}
					.news_Name{
						margin-top: 10upx;
						font-size: 26upx;
						color: #666;
					}
				}
			}
		}
		.news_bottom{
			margin-top: 20upx;
			background-color: #Fefefe;
			display: flex;
			flex-direction: column;
			.news_label{
				padding: 45upx 5% 5upx 5%;
				height: 86upx;
				line-height: 86upx;
				font-size: 32upx;
				font-weight: 700;
			}
			.news_bottom_ul{
				border-top: 1upx solid #f6f6f6;
				display: flex;
				flex-direction: column;
				.news_bottom_li{
					height: 120upx;
					padding: 0 24upx;
					border-top: 1upx solid #f1f1f1;
					display: flex;
					justify-content: space-between;
					align-items: center;
					.news_li_left{
						display: flex;
						.news_li_Imgs{
							height: 80upx;
							width: 80upx;
							image{
								height: 80upx;
								width: 80upx;
								border-radius: 50%;
							}
						}
						.news_li_Name{
							margin-left: 20upx;
							display: flex;
							flex-direction: column;
							justify-content: space-around;
							height: 80upx;
							.Name{
								font-size: 28upx;
								color: #333;
								font-weight: 700;
							}
							.news_li_news{
								font-size: 24upx;
								color: #999;
							}
							
						}
					}
					.news_li_right{
						height: 100upx;
						font-size: 26upx;
						color: #999999;
					}
				}
				.news_bottom_li:active{
					background-color: #f6f6f6;
				}
				.news_bottom_li:nth-child(1){
					border: none;
				}
			}
		}
	}
</style>
