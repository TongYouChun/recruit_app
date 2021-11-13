<!-- 编辑简历 -->
<template>
	<view class="modify_Resume">
		<!-- 头像 -->
		<view class="resume_head_sculpture">
			<view class="resume_picture" @click="callPicture()">
				<view class="resume_Imgs">
					<image :src="form.Imgs" mode="" v-if="form.Imgs"></image>
					<image src="../../../static/Icon/icon_xpyg/wode.png" mode="" v-if="!form.Imgs"></image>
					
				</view>
				<view class="resume_modify">
					<view class="modify">
						修改头像
					</view>
					<view class="modify_Iico">

					</view>
				</view>
			</view>
		</view>
		<!-- 简历信息 -->
		<view class="resume_content">
			<!-- 个人信息-->
			<view class="resume_information">
				<view class="resume_information_label">
					基本信息
				</view>
				<view class="information_li">
					<view class="information_text">
						应聘岗位：
					</view>
					<view class="information_input">
						<input type="text" value="" placeholder="输入应聘岗位" v-model="form.post"/>
					</view>
				</view>
				<view class="information_li">
					<view class="information_text">
						姓名：
					</view>
					<view class="information_input">
						<input type="text" value="" placeholder="输入姓名" v-model="form.name"/>
					</view>
				</view>
				<view class="information_li">
					<view class="information_text">
						年龄：
					</view>
					<view class="information_input">
						<input type="text" value="" placeholder="输入年龄" v-model="form.Age"/>
					</view>
				</view>
				<view class="information_li">
					<view class="information_text">
						性别：
					</view>
					<view class="information_input">
						<input type="text" value="" placeholder="输入性别" v-model="form.Gender"/>
					</view>
				</view>
				<view class="information_li">
					<view class="information_text">
						手机号：
					</view>
					<view class="information_input">
						<input type="text" value="" placeholder="输入手机号" v-model="form.Telephone"/>
					</view>
				</view>
			</view>
			<!-- 自我简介 -->
			<view class="synopsis">
				<view class="resume_information_label">
					简介
				</view>
				<view class="synopsis_ul">
					<textarea class="textarea" placeholder="请输入简介内容" auto-height v-model="form.introduce"/>
				</view>
			</view>
			<!-- 经历 -->
			<view class="work_experience">
				<view class="resume_information_label">
					经历
				</view>
				<view class="resume_experience_ul">
					<view class="experience_li" v-for="(item,index) in form.experience" :key="index">
						<view class="experience_modify" @click="modifyClickExperience(index)">
							修改
						</view>
						<view class="experience_delete" @click="deleteClickExperience(index)">
							删除
						</view>
						<view class="experience_Name">
							{{item.name}}
						</view>
						<view class="experience_date">
							时间：{{item.date}}
						</view>
						<view class="experience_position">
							职位：{{item.position}}
						</view>
						<view class="experience_remarks">
							备注：{{item.remarks}}
						</view>
					</view>
					<view class="experience_li_te" @click="addeXperience()">
						<view class="experience_li_te_Icon"></view>
						<view class="experience_li_te_text">
							添加经历
						</view>
					</view>
				</view>
			</view>
			<!-- 技能/证书 -->
			<view class="skill_experience">
				<view class="resume_information_label">
					技能/证书
				</view>
				<view class="resume_experience_ul">
					<view class="experience_li" v-for="(item,index) in form.certificate" :key="index">
						{{item}}
						<view class="experience_modify" @click="modifyClickCertificate(index)">
							修改
						</view>
						<view class="experience_delete" @click="deleteClickCertificate(index)">
							删除
						</view>
					</view>
					<view class="experience_li_te" @click="addeCertificate()">
						<view class="experience_li_te_Icon"></view>
						<view class="experience_li_te_text">
							添加技能/证书
						</view>
					</view>
				</view>
			</view>
			<view style="height: 110upx;">
				
			</view>
		</view>
		<!-- 是否 保存简历 -->
		<view class="resume_operation">
			<!-- 保存 -->
			<view class="preservation" @click="clickConserve()">
				保存
			</view>
			<!-- 取消 -->
			<view class="cancel"  @click="cancelClick">
				取消
			</view>
		</view>
		
		<!-- 添加经历 -->
		<view class="add_undergo" v-if="experienceJudge">
			<view class="add_undergo_container">
				<view class="resume_information_label">
					经历
				</view>
				<view class="undergo_name undergo_li">
					<view class="undergo_text">
						经历名称：
					</view>
					<view class="undergo_input">
						<input type="text" value="" placeholder="请输入名称" v-model="experience.name"/>
					</view>
				</view>
				<view class="undergo_date undergo_li">
					<view class="undergo_text">
						经历时间：
					</view>
					<view class="undergo_input">
						<input type="text" value="" placeholder="例: 2018.8.6 - 2021.8.9" v-model="experience.date"/>
					</view>
				</view>
				<view class="undergo_li">
					<view class="undergo_text">
						职位：
					</view>
					<view class="undergo_input">
						<input type="text" value="" placeholder="请输入担任职位" v-model="experience.position"/>
					</view>
				</view>
				<view class="undergo_li">
					<view class="undergo_text">
						备注：
					</view>
					<view class="undergo_input">
						<input type="text" value="" placeholder="请输入备注内容" v-model="experience.remarks"/>
					</view>
				</view>
				<view class="add_operation">
					<!-- 保存 -->
					<view class="preservation" @click="experienceHoldClick">
						保存
					</view>
					<!-- 取消 -->
					<view class="cancel" @click="addeXperience">
						取消
					</view>
				</view>
			
			</view>
		</view>
		
		<!-- 添加证书 -->
		<view class="add_certificate" v-if="certificateJudge">
			<view class="add_certificate_container">
				<view class="resume_information_label">
					证书
				</view>
				<view class="certificate_frame">
					<textarea class="certificate_textarea" placeholder="请输入证书名称" auto-height v-model="certificate"/>
				</view>
				<view class="add_operation">
					<!-- 保存 -->
					<view class="preservation" @click="certificateClick">
						保存
					</view>
					<!-- 取消 -->
					<view class="cancel" @click="addeCertificate">
						取消
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
				index: null,
				// 经历判断
				experienceJudge: false,
				// 证书判断
				certificateJudge: false,
				// 修改判断
				Modify:false,
				// 信息
				form:{
					Imgs:'',
					experience:[],
					certificate: []
				},
				// 经历
				experience:{
					name:'',
					date:'',
					position: '',
					remarks: '',
					
				},
				// 证书
				certificate:''
			}
		},
		created () {
			let resume = uni.getStorageSync('resume');
			if(resume){
				this.form = resume
			}
			
		},
		methods:{
			// 调用相机
			callPicture () {
				uni.chooseImage({
				  	count: 1,
				    sizeType: ['original', 'compressed'],
				    sourceType: ['camera','album'], //这要注意，camera掉拍照，album是打开手机相册
				    success: (res)=> {
						console.log(res);
						const tempFilePaths = res.tempFilePaths;
						this.form.Imgs = res.tempFilePaths[0]
						this.$forceUpdate();
						console.log(this.form.Imgs)
				    }
				});
			},
			// 经历保存
			experienceHoldClick() {
				if(this.Modify){
					this.form.experience[this.index] = this.experience;
					this.Modify = false
					this.experienceJudge = false
					return
				}else{
					this.form.experience.push(this.experience)
					this.experienceJudge = false
				}
				
			},
			// 证书保存
			certificateClick() {
				if(this.Modify){
					this.form.certificate[this.index] = this.certificate;
					this.Modify = false
					this.certificateJudge = false
					return
				}else{
					this.form.certificate.push(this.certificate)
					this.certificateJudge = false
				}
			},
			// 修改经历
			modifyClickExperience (index) {
				this.index = index;
				this.experience = this.form.experience[index];
				this.Modify = true
				this.experienceJudge = true
			},
			// 删除经历
			deleteClickExperience(inde){
				this.form.experience.splice(this.form.experience.findIndex((item,index) => index === inde), 1)
			},
			// 修改证书
			modifyClickCertificate (index) {
				this.index = index;
				this.certificate = this.form.certificate[index]
				this.Modify = true
				this.certificateJudge = true
			},
			// 删除证书
			deleteClickCertificate (inde) {
				this.form.certificate.splice(this.form.certificate.findIndex((item,index) => index === inde), 1)
			},
			// 保存 
			clickConserve () {
				uni.switchTab({
					url: '/pages/my/index',
				});
				uni.setStorageSync('resume', this.form);
			},
			// 取消
			cancelClick () {
				uni.switchTab({
					url: '/pages/my/index',
				});
			},
			// 添加经历
			addeXperience() {
				if(this.experienceJudge){
					this.experienceJudge = false
					this.Modify = false
				}else{
					this.experience= {};
					this.experienceJudge = true
				}
			},
			// 添加证书
			addeCertificate() {
				if(this.certificateJudge){
					this.certificateJudge = false
					this.Modify = false
				}else{
					this.certificate = '';
					this.certificateJudge = true
				}
			}
		}
	}
</script>

<style scoped lang="scss">
	.resume_information_label {
		margin-left: 30upx;
		height: 86upx;
		line-height: 86upx;
		font-size: 34upx;
		font-weight: 650;
		color: #333;
	}
	// 编辑简历
	.modify_Resume {
		min-height: 100%;
		background-color: #F1F1F1;
		display: flex;
		flex-direction: column;

		// 头像
		.resume_head_sculpture {
			border-top: 1upx solid #F1F1F1;
			height: 260upx;
			background-color: #FFFFFF;
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;

			.resume_picture {
				width: 200upx;
				display: flex;
				flex-direction: column;
				align-items: center;

				.resume_Imgs {
					height: 140upx;
					width: 140upx;

					image {
						height: 100%;
						width: 100%;
						border: 1upx solid #F8F8F8;
						border-radius: 50%;
					}
				}

				.resume_modify {
					height: 45upx;
					margin-top: 20upx;
					display: flex;
					align-items: center;
					font-size: 28upx;
					color: #999;
					font-weight: 620;

					.modify_Iico {
						margin-left: 20upx;
						height: 30upx;
						width: 30upx;
						background-image: url(../../../static/Icon/xingzhuang.png);
						background-size: 100% 100%;
					}
				}
			}
		}
		// 基本信息
		.resume_information {
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;

			.information_li {
				margin: 0 24upx;
				height: 76upx;
				line-height: 76upx;
				display: flex;
				border-bottom: 1upx solid #F1F1F1;

				.information_text {
					// text-align: right;
					width: 24%;
					text-align: center;
					font-size: 28upx;
					color: #000;
				}

				.information_input {
					flex: 1;
					input {
						height: 76upx;
						width: 100%;
						font-size: 28upx;
					}
				}
			}
		}
		// 自我简介
		.synopsis{
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
			.synopsis_ul{
				display: flex;
				flex-direction: column;
				align-items: center;
				margin-bottom: 30upx;
				.textarea{
					z-index: 1;
					width: 85%;
					min-height: 70upx;
					padding: 15upx 20upx;
					font-size: 28upx;
					color: #666;
					border: 1upx solid #e1e1e1;
					border-radius: 10upx;
				}
			}
		}
		// 工作经历
		.work_experience{
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
		}
		// 教育经历
		.education_experience{
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
		}
		// 项目经历
		.project{
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
		}
		//项目
		.skill_experience{
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
		}
		.resume_experience_ul{
			display: flex;
			flex-direction: column;
			.experience_li{
				margin: 5upx 32upx 10upx 32upx;
				padding: 15upx;
				min-height: 100upx;
				border: 1upx solid #ddd;
				border-radius: 5upx;
				font-size: 28upx;
				color: #999;
				position: relative;
				// 修改按钮
				.experience_modify{
					position: absolute;
					top: 10upx;
					right: 24upx;
					font-size: 28upx;
					color: #32B89B;
				}
				.experience_delete{
					position: absolute;
					top: 10upx;
					right: 114upx;
					font-size: 28upx;
					color: #f00;
				}
				.experience_Name{
					font-size: 34upx;
					height: 50upx;
					line-height: 50upx;
					color: #333333;
				}
				.experience_date{
					font-size: 26upx;
					color: #333333;
				}
				.experience_position{
					margin-top: 15upx;
					color: #666;
				}
				.experience_remarks{
					margin-top: 5upx;
					font-size: 26upx;
				}
			}
			// 添加按钮
			.experience_li_te{
				margin: 0 32upx;
				margin-bottom: 30upx;
				height: 200upx;
				background-color: #e1e1e1;
				display: flex;
				justify-content: center;
				align-items: center;
				.experience_li_te_Icon{
					height: 40upx;
					width: 40upx;
					background-image: url(../../../static/Icon/jia.png);
					background-size: 100% 100%;
				}
				.experience_li_te_text{
					margin-left: 20upx;
					font-size: 28upx;
					color: #32B89B;
				}
			}
		}
		// 保存
		.resume_operation{
			position: fixed;
			bottom: 0;
			left: 0;
			height: 120upx;
			width: 100%;
			background-color: #FFFFFF;
			display: flex;
			align-items: center;
			justify-content: space-around;
			.preservation{
				height: 80upx;
				width: 40%;
				background-color: #32B89B;
				border-radius: 8upx;
				font-size: 28upx;
				color: #FFFFFF;
				display: flex;
				align-items: center;
				justify-content: center;
			}
			.preservation:active{
				background-color: #229F84;
			}
			.cancel{
				height: 80upx;
				width: 40%;
				border: 1upx solid #e1e1e1;
				border-radius: 8upx;
				font-size: 28upx;
				color: #000;
				display: flex;
				align-items: center;
				justify-content: center;
			}
			.cancel:active{
				background-color: #F6F6F6;
			}
		}
		
		// 添加经历
		.add_undergo{
			z-index: 10;
			position: fixed;
			bottom: 0;
			left: 0;
			height: 100%;
			width: 100%;
			background-color: rgba(0,0,0,0.4);
			.add_undergo_container{
				position: absolute;
				bottom: 0;
				top: 0;
				left: 0;
				right: 0;
				margin: auto;
				width: 80%;
				height: 500upx;
				background-color: #FFFFFF;
				border-radius: 10upx;
				display: flex;
				flex-direction: column;
				padding-top: 20upx;
				.undergo_li{
					display: flex;
					align-items: center;
					justify-content: center;
					margin: 0 5%;
					height: 70upx;
					border-bottom: 1upx solid #e1e1e1;
					font-size: 24upx;
					.undergo_text{
						text-align: center;
						width: 25%;
						color: #333;
					}
					.undergo_input{
						flex: 1;
						display: flex;
						input{
							flex: 1;
							color: #666;
						}
					}
				}
				.add_operation{
					margin: 30upx 10%;
					display: flex;
					justify-content: space-between;
					.preservation{
						height: 80upx;
						width: 40%;
						background-color: #32B89B;
						border-radius: 8upx;
						font-size: 28upx;
						color: #FFFFFF;
						display: flex;
						align-items: center;
						justify-content: center;
					}
					.preservation:active{
						background-color: #229F84;
					}
					.cancel{
						height: 80upx;
						width: 40%;
						border: 1upx solid #e1e1e1;
						border-radius: 8upx;
						font-size: 28upx;
						color: #000;
						display: flex;
						align-items: center;
						justify-content: center;
					}
					.cancel:active{
						background-color: #F6F6F6;
					}
				}
			
			}
		}
		
		// 添加证书
		.add_certificate{
			z-index: 10;
			position: fixed;
			bottom: 0;
			left: 0;
			height: 100%;
			width: 100%;
			background-color: rgba(0,0,0,0.4);
			.add_certificate_container{
				position: absolute;
				bottom: 0;
				top: 0;
				left: 0;
				right: 0;
				margin: auto;
				width: 80%;
				height: 500upx;
				background-color: #FFFFFF;
				border-radius: 10upx;
				display: flex;
				flex-direction: column;
				padding-top: 20upx;
				.certificate_frame{
					display: flex;
					.certificate_textarea{
						margin: 0 5%;
						width: 90%;
						padding: 5px 10px;
						border: 2upx solid #aaa;
						min-height: 260upx;
						font-size: 26upx;
						color: #666;
						border-radius: 8upx;
					}
				}
				.add_operation{
					margin: 30upx 10%;
					display: flex;
					justify-content: space-between;
					.preservation{
						height: 80upx;
						width: 40%;
						background-color: #32B89B;
						border-radius: 8upx;
						font-size: 28upx;
						color: #FFFFFF;
						display: flex;
						align-items: center;
						justify-content: center;
					}
					.preservation:active{
						background-color: #229F84;
					}
					.cancel{
						height: 80upx;
						width: 40%;
						border: 1upx solid #e1e1e1;
						border-radius: 8upx;
						font-size: 28upx;
						color: #000;
						display: flex;
						align-items: center;
						justify-content: center;
					}
					.cancel:active{
						background-color: #F6F6F6;
					}
				}
							
			}
		}
	}
</style>
