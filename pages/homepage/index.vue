<!-- 首页 -->
<template>
	<view class="homepage">
		<!-- 搜索 -->
		<view class="search">
			<view class="search_Button" @click="searchClick()">
				<view class="search_Icon">
					
				</view>
				<view class="search_input">
					请输入搜索内容
				</view>
			</view>
			<view class="search_scanning">
				
			</view>
		</view>
		<!-- 轮播图 开始-->
		<view class="Carousel">
			<swiper indicator-dots circular autoplay interval=3000 indicator-active-color="#32B89B"
				indicator-color="rgba(191, 191, 191, 0.5)">
				<swiper-item v-for="(item,index) in swipers" :key="index">
					<image :src="item.imgs"></image>
				</swiper-item>
			</swiper>
		</view>
		<!-- 轮播图 结束 -->
		<!-- 公告 -->
		<view class="Notice">
			<view class="Notice_left">
				头条
			</view>
			<view class="Notice_right">
				<view class="news_li">
					<view class="news_li_Icon"></view>
					<view class="news_li_text">
						公告，某某企业急招
					</view>
				</view>
				<view class="news_li">
					<view class="news_li_Icon"></view>
					<view class="news_li_text">
						公告，某某企业急招
					</view>
				</view>
			</view>
		</view>
		<!-- 内容容器 -->
		<view class="Content_container">
			<!-- 选项 -->
			<!-- <view class="option">
				<view class="option_li" v-for="(item,index) in option" :key="index">
					<view class="option_li_img">
						<image :src="item.imgsIcon" mode=""></image>
					</view>
					<view class="option_li_text">
						{{item.name}}
					</view>
				</view>
			</view> -->
			<!-- 推荐 -->
			<!-- <view class="recommend">
				<view class="recommend_left">
					<image src="../../static/logo.png" mode=""></image>
				</view>
				<view class="recommend_right">
					<view class="recommend_imgs_li">
						<image src="../../static/logo.png" mode=""></image>
					</view>
					<view class="recommend_imgs_li">
						<image src="../../static/logo.png" mode=""></image>
					</view>
				</view>
			</view> -->
			<!-- 选项 -->
			<view class="options_ul">
				<view class="options_li" @click="enterpriseClick()">
					<view class="options_li_Icon">
						<image src="../../static/Icon/icon_lfzscot9us/qiye.png" mode=""></image>
					</view>
					<view class="options_li_Name">
						企业列表
					</view>
				</view>
				<view class="options_li">
					<view class="options_li_Icon">
						<image src="../../static/Icon/icon_lfzscot9us/gongzuo.png" mode=""></image>
					</view>
					<view class="options_li_Name">
						找工作
					</view>
				</view>
				<view class="options_li">
					<view class="options_li_Icon">
						<image src="../../static/Icon/icon_lfzscot9us/rencai.png" mode=""></image>
					</view>
					<view class="options_li_Name">
						招人才
					</view>
				</view>
				<view class="options_li">
					<view class="options_li_Icon">
						<image src="../../static/Icon/icon_lfzscot9us/yemian-copy-copy1.png" mode=""></image>
					</view>
					<view class="options_li_Name">
						优军首页
					</view>
				</view>
			</view>
			<!-- 工作信息 -->
			<view class="work_content">
				<!-- 岗位名称 + 选项 -->
				<view class="work_Top">
					<!-- 岗位名称 -->
					<view class="work_Name">
						<view class="work_Text">
							产品经理
						</view>
						<view class="work_Icon"></view>
					</view>
					<!-- 岗位选项 -->
					<view class="work_option">
						<view class="work_option_li" :class="[item.judge ? 'work_option_li_te' : '']" v-for="(item,index) in workOption" :key="index" @click="workOptionClick(index)">
							{{item.name}}
						</view>
					</view>
				</view>
				
				<view class="work_bottom">
					<view class="post_ul">
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
						<view class="post_li" @click="postDetailsClick()">
							<view class="post_Name">
								<text>产品y</text>
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
						<view class="post_li" @click="postDetailsClick()">
							<view class="post_Name">
								<text>产品y</text>
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
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers: [{
					imgs: '../../static/imgs1.jpg'
				}, {
					imgs: '../../static/imgs2.jpg'
				}, {
					imgs: '../../static/imgs3.jpg'
				}],
				
				option:[
					{
						imgsIcon:'../../static/Icon/icon_2iyfu/gerenzhongxin_linshigongzhaopin.png',
						name:'快速直招'
					},
					{
						imgsIcon:'../../static/Icon/icon_2iyfu/jisu.png',
						name:'极速反馈'
					},
					{
						imgsIcon:'../../static/Icon/icon_2iyfu/tubiaozhizuomoban1.png',
						name:'地图找工作'
					}
				],
				// 岗位选项
				
				workOption:[
					{
						name:'推荐',
						judge: true
					},{
						name:'最新',
						judge: false
					}
				]
				
			}
		},
		methods:{
			// 企业列表
			enterpriseClick() {
				uni.switchTab({
				    url: '/pages/enterprise/index'
				});
			},
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
			// 岗位选项
			workOptionClick(index){
				this.workOption.map(ser => ser.judge=false);
				this.workOption[index].judge = true;
			}
		}
	}
</script>

<style scoped lang="scss">
	// 搜索图标
	.search_Icon{
		margin-left: 30upx;
		width: 40upx;
		height: 40upx;
		background-image: url(../../static/Icon/sousuo.png);
		background-size: 100% 100%;
	}
	// 消息提示图标
	.search_scanning{
		margin-right: 5%;
		width: 50upx;
		height: 50upx;
		background-image: url(../../static/Icon/lingdang-1.png);
		background-size: 100% 100%;
	}
	.homepage{
		min-height: 100%;
		background-color: #F1F1F1;
		overflow: hidden;
	}
	.Carousel{
		position: relative;
	}
	// 搜索
	.search{
		// position: absolute;
		// z-index: 2;
		margin-bottom: 10upx;
		height: 115upx;
		display: flex;
		background-color: #FFFFFF;
		justify-content: space-between;
		align-items: center;
		.search_Button{
			margin-left: 5%;
			width: 75%;
			height: 65upx;
			background-color: #F1F1F1;
			border-radius: 35upx;
			display: flex;
			align-items: center;
			.search_input{
				flex: 1;
				margin-left: 8upx;
				margin-right: 30upx;
				font-size: 28upx;
				color: #888;
			}
			
		}
	}
	
	// 新闻公告
	.Notice{
		display: flex;
		height: 90upx;
		background-color: #FFFFFF;
		.Notice_left{
			display: flex;
			justify-content: center;
			align-items: center;
			width: 20%;
			font-size: 36upx;
			font-weight: 700;
			color: #333;
		}
		.Notice_right{
			width: 80%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			.news_li{
				display: flex;
				.news_li_Icon{
					width: 30upx;
					height: 30upx;
					background-image: url(../../static/Icon/icon_2iyfu/huo.png);
					background-size: 100% 100%;
				}
				.news_li_text{
					font-size: 24upx;
					line-height: 34upx;
					color: #333;
				}
			}
		}
	}
	
	// 内容容器
	.Content_container{
		margin-top: 20upx;
		background-color: #FFFFFF;
		.options_ul{
			display: flex;
			padding: 0 5%;
			justify-content: space-between;
			border-bottom: 15upx solid #F1F1F1;
			.options_li{
				margin: 20upx 0;
				display: flex;
				flex-direction: column;
				align-items: center;
				.options_li_Icon{
					height: 100upx;
					width: 100upx;
					background-color: #32B89B;
					display: flex;
					align-items: center;
					justify-content: center;
					border-radius: 50%;
					image{
						height: 60upx;
						width: 60upx;
					}
				}
				.options_li_Name{
					margin-top: 15upx;
					font-size: 26upx;
					color: #999999;
				}
			}
		}
		.option{
			display: flex;
			height: 80upx;
			justify-content: space-between;
			margin: 0 5%;
			border-bottom: 1upx solid #F1F1F1;
			align-items: center;
			.option_li{
				display: flex;
				.option_li_img{
					width: 40upx;
					height: 40upx;
					image{
						height: 40upx;
						width: 40upx;
					}
				}
				.option_li_text{
					margin-left: 6upx;
					font-size: 28upx;
					font-weight: 600;
					color: #444;
				}
			}
		}
		// 推荐
		.recommend{
			border-bottom: 20upx solid #F1F1F1;
			height: 300upx;
			display: flex;
			overflow: hidden;
			padding: 20upx 3%;
			.recommend_left{
				width: 50%;
				height: 300upx;
				display: flex;
				justify-content: center;
				align-items: center;
				image{
					width: 95%;
					height: 280upx;
				}
			}
			.recommend_right{
				width: 50%;
				height: 300upx;
				display: flex;
				flex-direction: column;
				// justify-content: center;
				align-items: center;
				.recommend_imgs_li{
					height: 135upx;
					margin-top: 10upx;
					width: 95%;
					image{
						height: 100%;
						width: 100%;
					}
				}
			}
		}
		// 招聘信息
		.work_content{
			display: flex;
			flex-direction: column;
			.work_Top{
				display: flex;
				align-items: center;
				justify-content: space-between;
				margin: 0 5%;
				border-bottom: 1upx solid #F1F1F1;
				
			}
			// 招聘名称
			.work_Name{
				display: flex;
				font-size: 32upx;
				height: 100upx;
				line-height: 80upx;
				color: #333;
				font-weight: 600;
				align-items: center;
				.work_Icon{
					margin-left: 10upx;
					width: 32upx;
					height: 32upx;
					background-image: url(../../static/Icon/icon-test.png);
					background-size: 100% 100%;
				}
			}
			// 招聘选项
			.work_option{
				display: flex;
				.work_option_li{
					margin-left: 50upx;
					width: 80upx;
					padding-bottom: 10upx;
					text-align: center;
					font-size: 28upx;
					color: #999;
					border-bottom: 4upx solid #FFFFFF;
					
				}
				.work_option_li_te{
					color: #32B89B;
					font-weight: 600;
					border-bottom: 7upx solid #32B89B;
				}
			}
			// 岗位列表
			.work_bottom{
				display: flex;
				flex-direction: column;
				.post_ul{
					display: flex;
					flex-direction: column;
					.post_li{
						margin: 20upx 0;
						padding: 0 5%;
						display: flex;
						flex-direction: column;
						padding-bottom: 20upx;
						border-bottom: 20upx solid #F1F1F1;
						// 岗位名称
						.post_Name{
							display: flex;
							justify-content: space-between;
							height: 45upx;
							line-height: 45upx;
							text:nth-child(1){
								font-size: 34upx;
								font-weight: 700;
								color: #333;
							}
							text:nth-child(2){
								font-size: 34upx;
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
		}
	}
</style>

<style>
	.Carousel swiper {
		width: 100%;
		height: 340upx;
	}

	.Carousel image {
		width: 100%;
		height: 340upx;
	}
</style>

