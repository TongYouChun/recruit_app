<template>
	<view class="My">
		<!-- 用户信息 -->
		<view class="My_top">
			<view class="My_imgs">
				<image src="../../static/Icon/icon_itxa/wode.png" mode=""></image>
			</view>
			<view class="My_name">
				<text>林大伟</text>
				<text>3年工作经验/本科/27岁</text>
			</view>
			<view class="resume" @click="seeClick()">
				<text>查看简历</text>
			</view>
		</view>
		<!-- 用户功能 -->
		<view class="My_bottom">
			<!-- 重要的 -->
			<view class="important_option">
				<view class="option_li" v-for="(item,index) in importantOption" :key="index" @click="importantOptionClick(index)">
					<view class="option_Imgs">
						<image :src="item.imgs" mode=""></image>
					</view>
					<view class="option_text">
						{{item.name}}
					</view>
				</view>
			</view>
			<!-- 用户管理 -->
			<view class="Administration">
				<view class="Administration_li" v-for="(item,index) in Administration" :key="index" @click="administrationClick(item.nameText)">
					<view class="Administration_Imgs">
						<image :src="item.imgesIcon" mode=""></image>
					</view>
					<view class="Administration_name">
						{{item.nameText}}
					</view>
					<view class="Administration_arrow"></view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// 选项
				importantOption:[
					{
						imgs:'../../static/Icon/icon_dknj/jianli.png',
						name:'附件简历'
					},{
						imgs:'../../static/Icon/icon_dknj/fill_folder.png',
						name:'我的投递'
					},{
						imgs:'../../static/Icon/icon_dknj/gongsi.png',
						name:'关注公司'
					},{
						imgs:'../../static/Icon/icon_dknj/nav--defaut.png',
						name:'职位收藏'
					}
				],
				Administration:[
					{
						imgesIcon: '../../static/Icon/icon_cjhb/gerenzhongxin.png',
						nameText: '个人服务'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/qiuzhiyixiang-.png',
						nameText: '求职意向'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/xiugai.png',
						nameText: '人信息修改'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/shouji.png',
						nameText: '绑定手机'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/qiye.png',
						nameText: '企业入驻'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/pinglun.png',
						nameText: '我的评论'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/fuwupingjia-kefu-select-copy.png',
						nameText: '联系客服'
					},{
						imgesIcon: '../../static/Icon/icon_cjhb/shezhi.png',
						nameText: '设置'
					}
				]
			}
		},
		methods:{
			// 只要菜单
			importantOptionClick (index) {
				let urls = ''
				if(this.importantOption[index].name === '我的投递'){
					urls = '/pages/news/Delivery/index'
				}
				uni.navigateTo({
					url: urls,
				});
			},
			// 简历
			seeClick() {
				let resume = uni.getStorageSync('resume');
				if(resume){
					uni.navigateTo({
						url: '/pages/my/resume/index',
					});
				}else{
					uni.navigateTo({
						url: '/pages/my/modifyResume/index',
					});
				}
				
			},
			// 管理
			administrationClick(name) {
				let urls = ''
				if(name == '求职意向'){
					urls = '/pages/my/intention/index'
				}else if(name == '个人服务'){
					urls = '/pages/my/personal/index'
				}
				uni.navigateTo({
					url: urls,
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.My{
		min-height: 100%;
		background-color: #F1F1F1;
		// 用户信息
		.My_top{
			display: flex;
			height: 340upx;
			background-color: #32B89B;
			align-items: center;
			.My_imgs{
				margin-left: 24upx;
				width: 120upx;
				height: 120upx;
				overflow: hidden;
				border-radius: 50%;
				image{
					width: 120upx;
					height: 120upx;
				}
			}
			.My_name{
				margin: 0 24upx;
				height: 100upx;
				display: flex;
				flex-direction: column;
				justify-content: space-between;
				text:nth-child(1){
					font-size: 32upx;
					font-weight: 650;
					color: #FFFFFF;
				}
				text:nth-child(2){
					font-size: 24upx;
					color: #FFFFFF;
				}
			}
			.resume{
				width: 20%;
				margin-left: auto;
				height: 90upx;
				background-color: #F2BA30;
				border-radius: 40upx 0 0 40upx;
				display: flex;
				align-items: center;
				justify-content: center;
				text{
					border-radius: 50%;
					width: 50%;
					font-size: 28upx;
					color: #907125;
				}
			}
		}
		// 用户管理
		.My_bottom{
			display: flex;
			flex-direction: column;
			.important_option{
				position: relative;
				top: -70upx;
				left: 0;
				right: 0;
				margin: auto;
				background-color: #fff;
				border-radius: 25upx;
				width: 90%;
				height: 180upx;
				display: flex;
				.option_li{
					width: 25%;
					display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					.option_Imgs{
						height: 60upx;
						width: 60upx;
						image{
							width: 100%;
							height: 100%;
						}
					}
					.option_text{
						font-size: 26upx;
						margin: 10upx 0;
						color: #666;
					}
				}
			}
			// 管理
			.Administration{
				margin: 0 5%;
				margin-top: -40upx;
				display: flex;
				flex-direction: column;
				width: 90%;
				background-color: #FFFFFF;
				border-radius: 8upx;
				.Administration_li{
					margin: 0 20upx;
					height: 86upx;
					display: flex;
					align-items: center;
					border-top: 1upx solid #F1F1F1;
					.Administration_Imgs{
						margin-left: 10upx;
						width: 40upx;
						height: 40upx;
						image{
							height: 100%;
							width: 100%;
						}
					}
					.Administration_name{
						margin-left: 15upx;
						font-size: 28upx;
						font-weight: 650;
					}
					.Administration_arrow{
						margin-left: auto;
						width: 20upx;
						height: 20upx;
						background-image: url(../../static/Icon/icon-test.png);
						background-size: 100% 100%;
					}
				}
				.Administration_li:nth-child(1){
					border: none;
				}
			}
		}
	}
</style>
