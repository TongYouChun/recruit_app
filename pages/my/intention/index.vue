<!-- 求职意向 -->
<template>
	<view class="intention">
		<view class="intention_ul">
			<view class="intention_li" v-for="(item,index) in workIntention" :key="index">
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
				workIntention: [{
					label: '期望职位类别',
					name: '产品经理'
				}, {
					label: '工作性质',
					name: '全职'
				}, {
					label: '期望薪资',
					name: '10K-20K'
				}, {
					label: '期望城市',
					name: '北京'
				}, {
					label: '当前状态',
					name: '积极找工作'
				}, {
					label: '到岗时间',
					name: '随时'
				}, ]
			}
		}
	}
</script>

<style scoped lang="scss">
	.intention {
		min-height: 100%;
		background-color: #FFFFFF;

		.intention_ul {
			border-top: 1upx solid #F1F1F1;
			display: flex;
			flex-direction: column;

			.intention_li {
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
