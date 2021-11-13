<!-- 搜索 -->
<template>
	<view class="search">
		<!-- 搜索框 -->
		<view class="search_frame">
			<view class="search_address">
				<view class="address">
					地址
				</view>
				<view class="address_Icon">
					<image src="../../static/Icon/xia.png" mode=""></image>
				</view>
			</view>
			<view class="search_input">
				<view class="input_Icon"></view>
				<input type="text" value="" placeholder="搜索职位/公司/内容" v-model="searchContent"/>
			</view>
			<view class="search_Button" @click="searchResult()">
				搜索
			</view>

		</view>
		<!-- 搜索容器 -->
		<view class="search_container">
			<!-- 历史 -->
			<view class="search_history">
				<!-- 标签 -->
				<view class="history_label">
					<view class="label">
						历史搜索
					</view>
					<view class="delete_icon"></view>
				</view>
				<view class="history_content">
					<view class="history_Li" v-for="(item,index) in historyContent" :key="index" @click="historyClick(index)">
						{{item.name}}
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
				// 搜索信息
				searchContent: '',
				// 历史内容
				historyContent: [
					{
						id: 1,
						name: '产品'
					},{
						id: 2,
						name: '经理'
					},{
						id: 3,
						name: '产品经理'
					}
				],
			}
		},
		methods:{
			// 搜索结果
			searchResult () {
				uni.navigateTo({
					url: '/pages/search/display/index',
				});
			},
			// 搜索选择搜索
			historyClick(index) {
				this.searchContent = this.historyContent[index].name
				uni.navigateTo({
					url: '/pages/search/display/index',
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.search {
		min-height: 100%;
		background-color: #F1F1F1;
		display: flex;
		flex-direction: column;
		// 搜索框
		.search_frame {
			height: 100upx;
			display: flex;
			justify-content: space-between;
			padding: 0 8%;
			align-items: center;
			background-color: #FFFFFF;
			// 地址
			.search_address {
				display: flex;
				// width: 120upx;
				// height: 60upx;
				// border: 1upx solid #F1F1F1;
				.address{
					// flex: 1;
					font-size: 28upx;
					color: #666;
				}
				.address_Icon{
					margin-left: 10upx;
					width: 30upx;
					height: 36upx;
					image{
						width: 100%;
						height: 100%;
					}
				}
			}
			// 搜索框
			.search_input{
				width: 60%;
				display: flex;
				height: 70upx;
				background-color: #F1F1F1;
				border-radius: 35upx;
				align-items: center;
				padding: 0 25upx;
				.input_Icon{
					width: 40upx;
					height: 40upx;
					background-image: url(../../static/Icon/sousuo.png);
					background-size: 100% 100%;
				}
				input{
					flex: 1;
					font-size: 28upx;
					margin-left: 15upx;
					height: 65upx;
				}
			}
			// 搜索按钮
			.search_Button{
				font-size: 28upx;
				color: #32B89B;
			}
		}
		// 搜索——容器
		.search_container{
			flex: 1;
			margin-top: 20upx;
			display: flex;
			flex-direction: column;
			background-color: #FFFFFF;
			.search_history{
				display: flex;
				flex-direction: column;
				margin-left: 30upx;
				margin-top: 30upx;
				.history_label{
					font-size: 36upx;
					font-weight: 700;
					color: #333;
				}
					
				.history_content{
					margin-top: 30upx;
					display: flex;
					flex-wrap: wrap;
					.history_Li{
						margin: 0 40upx 30upx 10upx;
						padding: 15upx 20upx;
						// background-color: #f3f3f3;
						border: 1upx solid #e1e1e1;
						border-radius: 5upx;
						font-size: 26upx;
						color: #666;
					}
					.history_Li:active{
						background-color: #f5f5f5;
					}
				}
			}
			
			
		}
	}	
</style>
