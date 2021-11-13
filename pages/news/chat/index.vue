<!-- 聊天页面 -->
<template>
	<view class="chat">
		<view class="chat_container">
			<view class="chat_top">
					<view class="chat_ul">
						<view class="chat_container_li m-item" v-for="(item,index) in wholeNews" :key="index">
							<view class="chat_he_li chat_li" v-if="item.type === 1">
								<view class="Imgs">
									<image src="../../../static/Icon/icon_itxa/wode.png" mode=""></image>
								</view>
								<view class="chat_news">
									<view class="chat_news_Icin"></view>
									<view class="Text">
										{{item.news}}
									</view>
								</view>
							</view>
							<view class="chat_own_li chat_li" v-if="item.type === 2">
								<view class="Imgs">
									<image src="../../../static/Icon/icon_itxa/wode.png" mode=""></image>
								</view>
								<view class="chat_news">
									<view class="Text">
										{{item.news}}
									</view>
									<view class="chat_news_Icin"></view>
								</view>
							</view>
						</view>
					</view>
			</view>
			<view class="chat_bottom">
				<view class="chat_input">
					<input class="input" type="text" v-model="tidings" @confirm="transmissionClick" />
				</view>
				<view class="chat_Button">
					<view class="Button" @click="transmissionClick">发送</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				childrenId: "",
				// 发送消息
				tidings: '',
				// 全部消息
				wholeNews: [{
					type: 1,
					news: '你好'
				}, {
					type: 1,
					news: '你好holl'
				}, {
					type: 2,
					news: '你好222'
				}, {
					type: 1,
					news: '你好holl'
				}, {
					type: 2,
					news: '聊天结束'
				}],
				style: {
					pageHeight: 0,
					contentViewHeight: 0,
					footViewHeight: 90,
					mitemHeight: 0
				},

			}
		},
		created() {
				// 每五秒发送一条消息
				// setInterval( () =>{
				// 	this.wholeNews.push(
				// 		{
				// 			type: 1,
				// 			news: '五秒一条消息'
				// 		}
				// 	)
				// },5000)
				this.fixedAreaHeight()
				this.obtainAreaHeight()
				
		},
		methods: {
			transmissionClick() {
				if (this.tidings) {
					this.wholeNews.push({
						type: 2,
						news: this.tidings
					})
					this.tidings = null;
					this.obtainAreaHeight()
				}
			},
			fixedAreaHeight() {
				let view = uni.createSelectorQuery().select(".chat_top");
				
				view.boundingClientRect(function(data) {
				
				console.log(data.height);
				
				}).exec();
			},
			obtainAreaHeight() {
				let view = uni.createSelectorQuery().select(".chat_ul");
				
				view.boundingClientRect(function(data) {
				
				console.log(data.height);
				
				}).exec();
			}
		}
	}
</script>

<style scoped lang="scss">
	.chat {
		display: flex;
		flex-direction: column;
		height: 100%;
		// overflow: hidden;
		.chat_container {
			height: 100%;
			display: flex;
			flex-direction: column;
			overflow: hidden;
			background-color: #F1F1F1;

			.chat_top {
				flex: 1;
				overflow-y: auto;
				display: flex;
				flex-direction: column;

				.chat_ul {
					margin: 0 2%;
					display: flex;
					flex-direction: column;

					.chat_li {
						display: flex;
						align-items: center;
						min-height: 120upx;

						.Imgs {
							height: 80upx;
							width: 80upx;

							image {
								height: 80upx;
								width: 80upx;
								border-radius: 50%;
								border: 1upx solid #ddd;
							}
						}

						.chat_news {
							font-size: 26upx;
							color: #666;
							min-height: 80upx;
							display: flex;
							align-items: center;

							.chat_news_Icin {
								height: 30upx;
								width: 30upx;
								background-image: url(../../../static/Icon/sanjiaoxingLeft.png);
								background-size: 100% 100%;
							}

							.Text {
								display: flex;
								min-height: 40upx;
								min-width: 40upx;
								align-items: center;
								word-wrap: break-word;
								word-break: normal;
								word-break: break-all;
								border-radius: 8upx;
								padding: 18upx 20upx;
								background-color: #FFFFFF;
							}
						}
					}

					.chat_own_li {
						display: flex;
						flex-direction: row-reverse;
						align-items: center;
						min-height: 140upx;

						.chat_news {
							.chat_news_Icin {
								background-image: url(../../../static/Icon/sanjiaoxing.png);
								background-size: 100% 100%;
							}

							.Text {
								color: #FFFFFF;
								background-color: #32B89B;
							}
						}
					}
				}
			}

			.chat_bottom {
				height: 120upx;
				border-top: 2upx solid #ddd;
				display: flex;
				justify-content: center;
				align-items: center;
				background-color: #FFFFFF;

				.chat_input {
					width: 75%;
					display: flex;
					height: 72upx;

					.input {
						margin: 0 5%;
						width: 90%;
						height: 72upx;
						padding: 0 30upx;
						background-color: #F6F6F6;
						border-radius: 40upx;
						font-size: 26upx;
						color: #666;
					}
				}

				.chat_Button {
					width: 20%;
					height: 72upx;
					display: flex;
					align-items: center;
					justify-content: center;

					.Button {
						height: 68upx;
						width: 120upx;
						text-align: center;
						line-height: 68upx;
						background-color: #27C29F;
						color: #FFFFFF;
						font-size: 28upx;
						border-radius: 10upx;
					}

					.Button:active {
						background-color: #149A7B;
					}
				}
			}
		}

	}
</style>
