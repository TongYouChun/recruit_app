<!-- 找企业 -->
<template>
	<view class="enterprise">
		<!-- 搜索 -->
		<view class="enterprise_search">
			<view class="search_input">
				<view class="input_Icon"></view>
				<input type="text" value="" placeholder="搜索企业名称" v-model="searchContent"/>
			</view>
			<view class="search_Button" @click="searchResult()">
				搜索
			</view>
		</view>
		<view style="height: 100upx; background-color: #F1F1F1;"></view>
		<!-- 企业内容 -->
		<view class="enterprise_content">
			<!-- 内容 -->
			<view class="enterprise_Ul">
				<view class="enterprise_li" v-for="(item,index) in Enterprise" :key='index' @click="EnterpriseDetailsClick(index)">
					<view class="Imgs">
						<image :src="item.imgs" mode=""></image>
					</view>
					<view class="enterprise_Text">
						<view class="Text_name name">
							{{item.name}}
						</view>
						<view class="Text_name introduce">
							{{item.introduce}}
						</view>
						<view class="Text_name number">
							{{item.number}}
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
				searchContent: '',
				Enterprise: [
					{
						imgs: 'https://gss3.bdstatic.com/84oSdTum2Q5BphGlnYG/timg?wapp&quality=80&size=b150_150&subsize=20480&cut_x=0&cut_w=0&cut_y=0&cut_h=0&sec=1369815402&srctrace&di=3e81c84d81ac4a8cc8bd359e9fa086d4&wh_rate=null&src=http%3A%2F%2Fimgsrc.baidu.com%2Fforum%2Fpic%2Fitem%2Fdc7612738bd4b31c4866d0d586d6277f9f2ff8a6.jpg',
						name: '百度贴吧企业',
						introduce: '尘文化传媒拥有影视制作, 设计策划，平面设计 , 媒体运营。定制承接',
						number: '20-30人'
					},{
						imgs: 'https://gss3.bdstatic.com/84oSdTum2Q5BphGlnYG/timg?wapp&quality=80&size=b150_150&subsize=20480&cut_x=0&cut_w=0&cut_y=0&cut_h=0&sec=1369815402&srctrace&di=3e81c84d81ac4a8cc8bd359e9fa086d4&wh_rate=null&src=http%3A%2F%2Fimgsrc.baidu.com%2Fforum%2Fpic%2Fitem%2Fdc7612738bd4b31c4866d0d586d6277f9f2ff8a6.jpg',
						name: '百度贴吧企业',
						introduce: '尘文化传媒拥有影视制作, 设计策划，平面设计 , 媒体运营。定制承接',
						number: '20-30人'
					}
				]
			}
		},
		methods:{
			// 搜索
			searchResult () {
				
			},
			// 企业详情
			EnterpriseDetailsClick(index) {
				uni.navigateTo({
					url: '/pages/enterprise/details/index',
				});
			}
			
		}
	}
</script>

<style scoped lang="scss">
	.enterprise{
		display: flex;
		flex-direction: column;
		min-height: 100%;
		.enterprise_search{
			position: fixed;
			z-index: 3;
			top: 0;
			left: 0;
			background-color: #FFFFFF;
			width: 89%;
			display: flex;
			padding: 0 5.5%;
			justify-content: space-between;
			align-items: center;
			height: 90upx;
			// 搜索框
			.search_input{
				width: 70%;
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
				padding: 15upx 25upx;
				background-color: #32B89B;
				font-size: 28upx;
				color: #FFFFFF;
				border-radius: 10upx;
			}
			.search_Button:active{
				background-color: #2A9B82;
			}
		}
		.enterprise_content{
			margin: 0 6%;
			display: flex;
			flex-direction: column;
			.enterprise_Ul{
				display: flex;
				flex-direction: column;
				.enterprise_li{
					display: flex;
					align-items: center;
					height: 200upx;
					border-bottom: 1upx solid #F1F1F1;
					.Imgs{
						width: 120upx;
						height: 120upx;
						image{
							width: 120upx;
							height: 120upx;
						}
					}
					.enterprise_Text{
						margin-left: 24upx;
						flex: 1;
						display: flex;
						flex-direction: column;
						overflow: hidden;
						.Text_name{
							margin-top: 10upx;
						}
						.name{
							font-size: 28upx;
							font-weight: 700;
							color: #333;
						}
						.introduce{
							font-size: 26upx;
							color: #333;
							width: 100%;
							overflow: hidden;
							white-space: nowrap;
							text-overflow: ellipsis;
							
						}
						.number{
							font-size: 24upx;
							color: #333;
						}
					}
				}
			}
		}
	}
</style>
