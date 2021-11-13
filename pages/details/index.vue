<!-- 岗位详情 -->
<template>
	<view class="details">
		<view class="details_container">
			<view class="details_container_top">
				<view class="details_container_information">
					<view class="details_Name">
						<view class="post_Name">
							产品经理
						</view>
						<view class="post_salary">
							10K-14K
						</view>
					</view>
					<view class="details_introduce">
						滁州 | 200人以上 | 内容
					</view>
				</view>
				<view class="details_container_recruit">
					<view class="recruit_Imgs">
						<image src="../../static/Icon/icon_xpyg/wode.png" mode=""></image>
					</view>
					<view class="recruit_information">
						<view class="recruit_Name">
							<view class="Name">
								张三
							</view>
							<view class="activeStatus">
								今天来过
							</view>
						</view>
						<view class="recruit_position">
							职位名称
						</view>
						<!-- <view class="recruit_company">
							公司名称
						</view> -->
					</view>
				</view>
			</view>
			<view class="details_container_bottom">
				<view class="details_container_details">
					<view class="details_title">
						职位详情
					</view>
					<view class="details_content">
						<text>1、负责投资理财平台的产品规划和设计及整个产品生命周期的管理工作；</text>
						<text>2、熟悉掌握基金理财第三方平台的功能需求，梳理产品需求和优先级，负责需求文档撰写、评审及产品研发虚拟项目的管理及执行，推动项目落地；</text>
						<text>3、为平台用户提供完善的体验保障流程，涉及线上理财流程、多方接口交互、智能投顾等；</text>
						<text>4、参与传统金融机构研究，了解内部流程、跟踪用户反馈，不断优化平台，提升用户使用体验；</text>
						<text>5、与市场、运营、技术等团队紧密协同，紧贴业务发展策略，把握产品重点并进行创新，迅速产品化，快速推广；</text>
						<text>6、负责开放平台和SaaS产品设计等</text>
					</view>
				</view>
				<view class="details_company">
					<view class="details_title">
						公司信息
					</view>
					<view class="company_ul">
						<view class="company_Name">
							<view class="Name">
								某某公司
							</view>
							<view class="company_information">
								滁州 | 200人以上 | 娱乐
							</view>
						</view>
						<view class="details_Imgs">
							<image src="../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode=""></image>
						</view>
					</view>
				</view>
				<view class="details_address">
					<view class="details_Name">
						<view class="address_Icon"></view>
						<view class="Name">
							滁州—某某区—某某地方
						</view>
					</view>
					<view class="details_detailed">
						某某市某某区某某地方28号3栋几单元
					</view>
				</view>
			</view>
		</view>
		<!-- 相关岗位 -->
		<view class="relevant_post">
			<view class="details_title">
				相关岗位
			</view>
			<view class="post_ul">
				<view class="post_li">
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
							<image src="../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode=""></image>
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
					<view class="post_li">
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
								<image src="../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png" mode=""></image>
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
		<!-- 联系 -->
		<view style="height: 100upx;">
			
		</view>
		<view class="contact">
			<view class="Telephone">
				<view class="Telephone_Icon">
					<image src="../../static/Icon/icon_zmcxv/dianhua.png" mode=""></image>
				</view>
				<view class="Telephone_text">
					电话联系
				</view>
			</view>
			<view class="letter" :class="[prohibit ? 'prohibits' : 'letter_te']" @click="sendOutClick">
				<view class="letter_Icon">
					<image src="../../static/Icon/icon_zmcxv/fasong.png" mode=""></image>
				</view>
				<view class="letter_text">
					立即投递
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				prohibit:false
			}
		},
		methods:{
			// 开始聊天
			// startChatting () {
			// 	uni.navigateTo({
			// 		url: '/pages/news/chat/index',
			// 	});
			// }
			sendOutClick() {
				this.prohibit = true
			}
		}
	}
</script>

<style scoped lang="scss">
	.details_title{
		height: 86upx;
		color: #333;
		font-size: 34upx;
		font-weight: 700;
		display: flex;
		align-items: center;
	}
	.details{
		display: flex;
		flex-direction: column;
		min-height: 100%;
		background-color: #FFFFFF;
		.details_container{
			display: flex;
			flex-direction: column;
			border-bottom: 15upx solid #F1F1F1;
			.details_container_top{
				margin: 0 5%;
				display: flex;
				flex-direction: column;
				box-shadow: 0upx 8upx 8upx rgba(230,230,230,0.5);
				// 岗位 薪资待遇
				.details_container_information{
					padding: 0 24upx;
					display: flex;
					flex-direction: column;
					justify-content: center;
					height: 150upx;
					border-bottom: 2upx solid #F1F1F1;
					.details_Name{
						display: flex;
						justify-content: space-between;
						.post_Name{
							font-size: 30upx;
							font-weight: 700;
							color: #333;
						}
						.post_salary{
							font-size: 34upx;
							font-weight: 700;
							color: #EA6D0C;
						}
					}
					.details_introduce{
						margin: 10upx 0;
						font-size: 24upx;
						color: #999999;
					}
				}
				// 招聘人信息
				.details_container_recruit{
					display: flex;
					align-items: center;
					height: 180upx;
					border-bottom: 2upx solid #F1F1F1;
					.recruit_Imgs{
						width: 120upx;
						height: 120upx;
						image{
							width: 120upx;
							height: 120upx;
							border-radius: 50%;
						}
					}
					.recruit_information{
						margin-left: 24upx;
						display: flex;
						flex-direction: column;
						font-size: 26upx;
						.recruit_Name{
							display: flex;
							align-items: center;
							height: 45upx;
							.Name{
								font-size: 28upx;
								font-weight: 700;
								color: #333333;
							}
							.activeStatus{
								margin-left: 24upx;
								font-size: 24upx;
								color: #999999;
								padding: 6upx 10upx;
								background-color: #F1F1F1;
								border-radius: 8upx;
							}
						}
						.recruit_position{
							margin-top: 10upx;
							color: #999;
						}
						.recruit_company{
							margin-top: 6upx;
							font-size: 28upx;
							color: #666;
						}
					}
				}
			}
			// 岗位介绍及公司信息
			.details_container_bottom{
				margin: 0 5%;
				padding-bottom: 30upx;
				display: flex;
				flex-direction: column;
				// 岗位信息
				.details_container_details{
					margin-top: 20upx;
					display: flex;
					flex-direction: column;
					.details_content{
						font-size: 26upx;
						color: #333;
						display: flex;
						flex-direction: column;
					}
				}
				// 公司信息
				.details_company{
					margin-top: 20upx;
					display: flex;
					flex-direction: column;
					.company_ul{
						display: flex;
						align-items: center;
						justify-content: space-between;
						height: 150upx;
						border-top: 1upx solid #F1F1F1;
						border-bottom: 1upx solid #F1F1F1;
						padding: 0 34upx;
						.details_Imgs{
							height: 100upx;
							width: 100upx;
							image{
								height: 100upx;
								width: 100upx;
								border-radius: 15upx;
							}
						}
						.company_Name{
							display: flex;
							flex-direction: column;
							.Name{
								font-size: 30upx;
								font-weight: 700;
								 color: #333;
							}
							.company_information{
								margin-top: 10upx;
								font-size: 24upx;
								 color: #999;
							}
						}
					}
				}
				// 公司地址
				.details_address{
					display: flex;
					flex-direction: column;
					height: 110upx;
					border-bottom: 1upx solid #F1F1F1;
					padding: 0 34upx;
					justify-content: center;
					.details_Name{
						display: flex;
						height: 35upx;
						align-items: center;
						.address_Icon{
							width: 26upx;
							height: 26upx;
							background-image: url(../../static/Icon/dizhi.png);
							background-size: 100% 100%;
						}
						.Name{
							margin-left: 8upx;
							font-size: 30upx;
							color: #333;
						}
					}
					.details_detailed{
						margin-top: 10upx;
						font-size: 24upx;
						color: #999;
					}
				}
			}
		}
		// 相关岗位
		.relevant_post{
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
			padding: 0 5%;
			.post_ul{
				display: flex;
				flex-direction: column;
				.post_li{
					border-top: 1upx solid #F1F1F1;
					margin: 20upx 0;
					padding: 20upx 5%;
					display: flex;
					flex-direction: column;
					// 岗位名称
					.post_Name{
						display: flex;
						justify-content: space-between;
						height: 45upx;
						line-height: 45upx;
						text:nth-child(1){
							font-size: 30upx;
							font-weight: 700;
							color: #333;
						}
						text:nth-child(2){
							font-size: 30upx;
							font-weight: 700;
							color: #FF5733 ;
						}
						
					}
					// 地址
					.post_address{
						margin: 10upx 0;
						display: flex;
						align-items: center;
						height: 80upx;
						text{
							padding: 0 10upx;
							font-size: 24upx;
							color: #888;
							height: 26upx;
							line-height: 26upx;
							border-left: 3upx solid #888;
						}
						text:nth-child(1){
							padding-left: 0;
							border: none;
						}
					}
					// 介绍
					.post_demand{
						display: flex;
						text{
							margin: 10upx 5upx;
							padding: 10upx;
							font-size: 24upx;
							color: #666;
							background-color: #eee;
							border-radius: 5upx;
						}
					}
					// 招聘人 信息
					.recruit_information{
						margin-top: 30upx;
						display: flex;
						.recruit_Imgs{
							width: 100upx;
							height: 100upx;
							image{
								height: 100%;
								width: 100%;
							}
						}
						.recruit_introduce{
							margin-left: 24upx;
							display: flex;
							flex-direction: column;
							.name{
								font-size: 30upx;
								color: #333;
							}
							.company{
								margin: 10upx 0;
								display: flex;
								align-items: center;
								text{
									padding: 0 10upx;
									font-size: 24upx;
									color: #888;
									height: 35upx;
									line-height: 35upx;
									border-left: 3upx solid #888;
								}
								text:nth-child(1){
									padding-left: 0;
									border: none;
								}
							}
						}
					}
				}
								
			}
		}
		// 联系
		.contact{
			border-top: 1upx solid #F1F1F1;
			position: fixed;
			bottom: 0;
			left: 0;
			width: 100%;
			display: flex;
			align-items: center;
			justify-content: space-around;
			height: 100upx;
			background-color: #FFFFFF;
			.Telephone{
				display: flex;
				align-items: center;
				justify-content: center;
				height: 80upx;
				width: 40%;
				background-color: #EA6D0C;
				border-radius: 10upx;
				.Telephone_Icon{
					width: 50upx;
					height: 50upx;
					image{
						width: 50upx;
						height: 50upx;
					}
				}
				.Telephone_text{
					margin-left: 20upx;
					font-size: 26upx;
					color: #FFFFFF;
				}
			}
			.Telephone:active{
				background-color: #C35704;
			}
			.letter{
				display: flex;
				align-items: center;
				justify-content: center;
				height: 80upx;
				width: 40%;
				background-color: #32B89B;
				border-radius: 10upx;
				.letter_Icon{
					width: 50upx;
					height: 50upx;
					image{
						width: 50upx;
						height: 50upx;
					}
				}
				.letter_text{
					margin-left: 20upx;
					font-size: 26upx;
					color: #FFFFFF;
				}
			}
			.letter_te:active{
				background-color: #289E84;
			}
			.prohibits{
				background-color: #999;
			}
		}
	}
</style>
