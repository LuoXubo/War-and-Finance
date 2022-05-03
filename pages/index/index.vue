<template>
	<view class="content">
		
		<!-- 导航栏 -->
		<view class="NagivationBars">
			<view class="NagivationBar">
				<button @tap="ToIndex">首页</button>
			</view>
			<view class="NagivationBar">
				<button @tap="ToDetail1">比较1</button>
			</view>
			<view class="NagivationBar">
				<button @tap="ToDetail2">比较2</button>
			</view>
			<view class="NagivationBar">
				<button @tap="ToDetail3">比较3</button>
			</view>
		</view>
		
		<!-- 导航栏下面的新闻视图 -->
		<view class="news">
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image class="newsimg" src="../../media/about/about_1.png"></image>
						<view class="newsword"> 
							<view class="newstitle">
								北京疫情发布会汇总
							</view>
							<view class="newscontent">
								5月1日15时至2日15时，北京市新增本土新冠肺炎病毒感染者50例，
								其中确诊病例41例，无症状感染者9例。房山区17例、朝阳区13例、海淀区7例、丰台区6例、通州区4例、石景山区3例。
								管控人员45例、社区筛查5例。
							</view>
						</view>
					</view>
				</swiper-item>
				
				<swiper-item>
					<view class="swiper-item">
						<image class="newsimg" src="../../media/about/about_2.png"></image>
						<view class="newsword">
							<view class="newstitle">
								奋斗者逐梦前行
							</view>
							<view class="newscontent">
								谷雨过后，广袤的黑土地上呈现一片“黑油油”的生机。在位于黑龙江虎林市的北大荒集团八五〇农场有限公司第一管理区三作业站，
								天刚蒙蒙亮，种粮大户袁志欣便驾驶着播种机来到自家耕地。
							</view>
						</view>
					</view>
				</swiper-item>
				
				<swiper-item>
					<view class="swiper-item">
						<image class="newsimg" src="../../media/banner/banner_user.jpg"></image>
						<view class="newsword">
							<view class="newstitle">
								百姓谁不爱好官？
							</view>
							<view class="newscontent">
								2014年3月17日至18日，习近平总书记赴河南兰考调研指导党的群众路线教育实践活动。刚一到兰考，他就来到焦裕禄同志纪念馆参观，边看边问，认真听取讲解。
								这是时隔五年，他第二次在兰考县考察调研期间专程瞻仰焦裕禄同志先进事迹。
							</view>
						</view>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500
			}
		},
		onLoad() {

		},
		methods: {
			ToIndex:function(){
				uni.navigateTo({
					url : "/pages/index/index"
				})
			},
			ToDetail1:function(){
				uni.navigateTo({
					url : "/pages/detail1/detail1"
				})
			},
			ToDetail2:function(){
				uni.navigateTo({
					url : "/pages/detail2/detail2"
				})
			},
			ToDetail3:function(){
				uni.navigateTo({
					url : "/pages/detail3/detail3"
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	
	.NagivationBars {
		display: flex;
		flex-direction: row;
		margin-top: 30upx;
		margin-left: 300upx;
		margin-right: 300upx;
		
	}
	
	.NagivationBar {
		justify-content: center;
		align-items: center;
		margin-right: 100upx;
		border: 5upx solid red;
		border-radius: 10upx;
	}
	
	.news {
		margin-top: 50upx;
		height: 700upx;
		width: 100%;
	}
	
	.swiper {
		width: 100%;
		height: 1200upx;
		justify-content: center;
		align-items: center;
		/* background-color: blueviolet; */
	}
	.swiper-item {
		display: flex;
		flex-direction: row;
	}
	
	.newsimg {
		height: 1200upx;
		width: 70%;
	}
	.newsword {
		justify-content: center;
		align-items: center;
		width: 30%;
	}
	.newstitle {
		text-align: center;
		border: 2px solid #55557f;
		border-radius: 25upx;
		margin: 100upx;
		font-size: 60upx;
	}
	.newscontent {
		text-align: center;
		border: 2px solid #aa5500;
		border-radius: 30upx;
		margin: 20upx;
		font-family: 'Kaiti';
	}
</style>
