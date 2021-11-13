<!-- 个人服务 -->
<template>
	<view class="personal">
		<view class="personal_ul">
			<view class="personal_li" v-for="(item,index) in workpersonal" :key="index" @click="clickDetails(item.label)">
				<view class="label">
					{{item.label}}
				</view>
				<view class="Name">
					<text>{{item.name}}</text>
					<view class="resume_Icon"></view>
				</view>
			</view>
		</view>
		<!-- 修改信息 -->
		<!-- <view class="modify_information">
			
			<view class="modify_form">
				<view class="modify_input">
					<input type="text" value="" placeholder="请输入信息"/>
				</view>
				<view class="modify_operation">
					<view class="determine">
						确定
					</view>
					<view class="cancel">
						取消
					</view>
				</view>
			</view>
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				workpersonal: [{
					label: '我的简历',
					name: ''
				}, {
					label: '我的申请',
					name: ''
				}, {
					label: '关注公司',
					name: ''
				}, {
					label: '职位收藏',
					name: ''
				}]
			}
		},
		methods:{
			clickDetails(name){
				if(name == '我的简历'){
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
				}
			}
		}
	}
</script>

<style scoped lang="scss">
	.personal {
		min-height: 100%;
		background-color: #FFFFFF;

		.personal_ul {
			border-top: 1upx solid #F1F1F1;
			display: flex;
			flex-direction: column;

			.personal_li {
				border-bottom: 1upx solid #F1F1F1;
				padding: 0 24upx;
				height: 100upx;
				display: flex;
				align-items: center;
				justify-content: space-between;

				.label {
					font-size: 27upx;
					color: #333;
				}

				.Name {
					height: 35upx;
					display: flex;
					align-items: center;
					font-size: 24upx;
					color: #999;
					display: flex;
					.resume_Icon {
						margin-left: 15upx;
						width: 28upx;
						height: 28upx;
						background-image: url(../../../static/Icon/icon-test.png);
						background-size: 100% 100%;
					}
				}
			}
		}
	}
</style>
