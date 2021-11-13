<!-- 查看简历 -->
<template>
	<view class="resume">
		<!-- 头像+ 基本信息 -->
		<view class="resume_top">
			<view class="head_portrait">
				<image :src="resumeForm.Imgs" mode=""></image>
			</view>
			<view class="personal_message">
				<view class="Name">
					{{resumeForm.name}}
				</view>
				<view class="Age_message">
					{{resumeForm.Age}}岁 | {{resumeForm.Gender}}
				</view>
				<view class="Telephone">
					手机号：{{resumeForm.Telephone}}
				</view>
				<view class="mailbox">
					岗位：{{resumeForm.post}}
				</view>
			</view>
			<!-- 修改 -->
			<view class="resume_modify" @click="modifyClick()">
				修改
			</view>
		</view>
		<!-- 个人 信息 -->
		<view class="resume_bottom">
			<!-- 经历 -->
			<view class="education">
				<view class="resume_tag">
					<view class="resume_tag_text">
						经历
					</view>
				</view>
				<view class="education_ul">
					<view class="education_li" v-for="(item,index) in resumeForm.experience" :key="index">
						<view class="education_li_name">
							{{item.name}}
						</view>
						<view class="education_li_time">
							{{item.date}}
						</view>
						<view class="education_li_position">
							职务：{{item.position}}
						</view>
						<view class="education_li_major">
							备注：{{item.remarks}}
						</view>
					</view>
				</view>
			</view>
			<!-- 技能证书 -->
			<view class="certificate">
				<view class="resume_tag">
					<view class="resume_tag_text">
						证书
					</view>
				</view>
				<view class="certificate_ul">
					<view class="certificate_li" v-for="(item,index) in resumeForm.certificate" :key="index">
						{{item}}
					</view>
					
				</view>
			</view>
			<!-- 自我评价 -->
			<view class="evaluate">
				<view class="resume_tag">
					<view class="resume_tag_text">
						简介
					</view>
				</view>
				<view class="evaluate_ul">
					{{resumeForm.introduce}}
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				resumeForm: {}
			}
		},
		created () {
			let resume = uni.getStorageSync('resume');
			this.resumeForm = resume
			
		},
		methods:{
			// 修改
			modifyClick() {
				uni.navigateTo({
					url: '/pages/my/modifyResume/index',
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	// 标签
	.resume_tag{
		margin: 0 28upx;
		height: 86upx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		border-bottom: 2upx solid #e1e1e1;
		.resume_tag_text{
			padding-left: 15upx;
			border-left: 10upx solid #32B89B;
			height: 40upx;
			line-height: 40upx;
			font-size: 32upx;
			font-weight: 650;
		}
	}
	
	.resume {
		min-height: 100%;
		background-color: #F1F1F1;
		overflow: hidden;

		.resume_top {
			margin: 20upx 3%;
			display: flex;
			flex-direction: column;
			align-items: center;
			height: 450upx;
			justify-content: center;
			background-color: #FFFFFF;
			border-radius: 20upx;
			position: relative;
			// 修改
			.resume_modify{
				position: absolute;
				width: 100upx;
				height: 70upx;
				line-height: 70upx;
				text-align: center;
				// background-color: #F0AD4E;
				right: 10upx;
				top: 5upx;
				color: #32B89B;
			}
			.head_portrait {
				height: 120upx;
				width: 120upx;

				image {
					height: 120upx;
					width: 120upx;
					border-radius: 50%;
				}
			}

			.personal_message {
				margin-top: 20upx;
				display: flex;
				flex-direction: column;
				align-items: center;

				.Name {
					margin: 15upx 0;
					font-size: 32upx;
					color: #333;
					font-weight: 650;
				}

				.Age_message {
					margin: 5upx 0;
					font-size: 26upx;
					color: #666;
				}

				.Telephone {
					margin: 20upx 0 10upx 0;
					font-size: 26upx;
					color: #666;
				}

				.mailbox {
					margin: 10upx 0;
					font-size: 26upx;
					color: #666;
				}

			}
		}
		
		.resume_bottom{
			margin: 0 3%;
			background-color: #FFFFFF;
			flex-direction: column;
			align-items: center;
			border-radius: 20upx;
			// 经历
			.education{
				display: flex;
				flex-direction: column;
				.education_ul{
					margin: 15upx 0;
					display: flex;
					flex-direction: column;
					.education_li{
						margin: 15upx 30upx;
						border-radius: 8upx;
						border: 3upx solid #f9f9f9;
						box-shadow: 10upx 10upx 5upx #f1f1f1;
						padding: 20upx;
						display: flex;
						flex-direction: column;
						.education_li_time{
							margin-top: 6upx;
							font-size: 28upx;
							color: #000;
						}
						.education_li_name{
							margin-top: 6upx;
							font-size: 28upx;
							color: #444;
						}
						.education_li_major{
							margin-top: 15upx;
							font-size: 28upx;
							color: #999;
						}
						.education_li_position{
							margin-top: 15upx;
							font-size: 28upx;
							color: #999;
						}
					}
				}
			}
			// 证书
			.certificate{
				display: flex;
				flex-direction: column;
				.certificate_ul{
					margin: 15upx 0;
					.certificate_li{
						margin: 15upx 40upx;
						font-size: 26upx;
						color: #888;
					}
				}
			}
			// 评论
			.evaluate{
				display: flex;
				flex-direction: column;
				.evaluate_ul{
					width: 100%;
					margin: 40upx;
					font-size: 28upx;
					color: #333;
				}
			}
		}
	}
</style>
