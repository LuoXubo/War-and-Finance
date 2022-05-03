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
		
		<!-- 百科 -->
		<view class="intro">
			<image class="introimg" src="../../media/about/about_1.png"></image>
			<view class="words">
				<view class="wordtitle">
					农业
				</view>
				<view class="wordcontent">
					农业属初级生产，为人类最大和最重要之经济活动之一。
					简单地说是人类运用其智慧去改变自然环境，利用驯养动植物的生长繁殖来获得产品，
					更进一步换取经济收益的一种系统。
					农业史可以追溯到数千年前，不同地区的农业的发展随着气候、文化及技术有很大的不同。
					各种农业的出现是人类定居社会兴起的关键因素，种植或养育驯化后的物种，有助于后来文明的发展。
					农业开始了人类从部落到国家持续千年的文化传承，料理发展与发达的年历系统也是早期农作文明最关键的知识，
					不过所有的农业都需要技术可以扩展及维持可以种植作物或养殖动物的土地，
					为了争夺土地的资源而爆发战争等，可以说农业也与所有传统文化息息相关。
				</view>
			</view>
		</view>
		
		<!-- 现有数据 -->
		<view class="datas">
			<view class="charts">
				<view style="text-align: center; font-size: 40upx;">Russian Datas</view>
				<echarts :option="option" style="height: 500upx;"></echarts>
			</view>
			
			<view class="texts">
				<view style="text-align: center; font-size: 40upx;">News</view>
				
				<view class="textitem">
					123456
				</view>
				
				<view class="textitem">
					ABCDEF
				</view>
				
				<view class="textitem">
					!@#$%^
				</view>
			</view>
		</view>
		
		<!-- 预测数据 -->
		<view class="datas">
			<view class="charts">
				<view style="text-align: center; font-size: 40upx; margin-top: 40upx;">Chinese Datas</view>
				<echarts :option="option1" style="height: 500upx;"></echarts>
			</view>
			
			<view class="texts">
				<view style="text-align: center; font-size: 40upx; margin-top: 50upx;">Predictions</view>
				
				<view class="textitem">
					123456
				</view>
				
				<view class="textitem">
					ABCDEF
				</view>
				
				<view class="textitem">
					!@#$%^
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	import echarts from '@/components/echarts/echarts.vue'
	export default {
		data() {
			return {
				option : {
					notMerge: true, // 自定义变量：true代表不合并数据，比如从折线图变为柱形图则需设置为true；false或不写代表合并
					tooltip: {
						trigger: 'axis',
						positionStatus: true,
						formatterStatus: false, // 自定义变量：是否格式化tooltip，设置为false时下面三项均不起作用
						formatterUnit: '元', // 自定义变量：数值后面的单位
						formatFloat2: true, // 自定义变量：是否格式化为两位小数
						formatThousands: true // 自定义变量：是否添加千分位
					},
					legend: {
						data: ['', '']
					},
					grid: {
						left: '8%',
						right: '8%',
						bottom: '8%',
						containLabel: true
					},
					xAxis: [{
						name: '年份',
						nameLocation: 'middle', //轴位置
						nameGap: 26, //name名字与轴线间距
						type: 'value',
						axisLine: {
							onZero: false
						}
					}],
					yAxis: [{
						name: '出口额',
						nameLocation: 'middle', //轴位置
						nameGap: 26, //name名字与轴线间距
						type: 'value',
						axisLine: {
							onZero: false
						}
					}],
					series: [{
						id: 'a',
						type: 'line',
						smooth: true,
						symbolSize: 0,
						data: [
							[11.26, 44.8],
							[11.94, 44.52],
							[12.64, 44.31],
							[13.34, 44.26],
							[14.04, 44.36],
							[14.76, 44.51],
							[15.46, 44.71],
							[16.2, 44.84],
							[16.92, 44.92],
							[17.64, 44.85],
							[18.38, 44.69],
							[19.1, 44.46],
							[19.84, 44.21],
							[20.56, 44.06],
							[21.28, 43.99],
							[22, 44.03],
							[22.72, 44.14],
							[23.46, 44.27],
							[24.16, 44.36],
							[24.88, 44.38],
							[25.58, 44.31],
							[26.28, 44.2],
							[26.98, 44.07],
							[27.68, 43.97],
							[28.36, 43.91],
							[29.04, 43.89],
							[29.72, 43.94],
							[30.38, 44.02],
							[31.04, 44.13],
							[31.68, 44.22],
							[32.34, 44.26],
							[32.98, 44.28],
							[33.6, 44.26],
							[34.22, 44.24],
							[34.84, 44.19],
							[35.44, 44.19],
							[36.04, 44.18],
						]
					}]
				},
				option1 : {
					notMerge: true, // 自定义变量：true代表不合并数据，比如从折线图变为柱形图则需设置为true；false或不写代表合并
					tooltip: {
						trigger: 'axis',
						positionStatus: true,
						formatterStatus: false, // 自定义变量：是否格式化tooltip，设置为false时下面三项均不起作用
						formatterUnit: '元', // 自定义变量：数值后面的单位
						formatFloat2: true, // 自定义变量：是否格式化为两位小数
						formatThousands: true // 自定义变量：是否添加千分位
					},
					legend: {
						data: ['', '']
					},
					grid: {
						left: '8%',
						right: '8%',
						bottom: '8%',
						containLabel: true
					},
					xAxis: [{
						name: '年份',
						nameLocation: 'middle', //轴位置
						nameGap: 26, //name名字与轴线间距
						type: 'value',
						axisLine: {
							onZero: false
						}
					}],
					yAxis: [{
						name: '出口额',
						nameLocation: 'middle', //轴位置
						nameGap: 26, //name名字与轴线间距
						type: 'value',
						axisLine: {
							onZero: false
						}
					}],
					series: [{
						id: 'a',
						type: 'line',
						smooth: true,
						symbolSize: 0,
						data: [
							[11.26, 44.8],
							[11.94, 44.52],
							[12.64, 44.31],
							[13.34, 44.26],
							[14.04, 44.36],
							[14.76, 44.51],
							[15.46, 44.71],
							[16.2, 44.84],
							[16.92, 44.92],
							[17.64, 44.85],
							[18.38, 44.69],
							[19.1, 44.46],
							[19.84, 44.21],
							[20.56, 44.06],
							[21.28, 43.99],
							[22, 44.03],
							[22.72, 44.14],
							[23.46, 44.27],
							[24.16, 44.36],
							[24.88, 44.38],
							[25.58, 44.31],
							[26.28, 44.2],
							[26.98, 44.07],
							[27.68, 43.97],
							[28.36, 43.91],
							[29.04, 43.89],
							[29.72, 43.94],
							[30.38, 44.02],
							[31.04, 44.13],
							[31.68, 44.22],
							[32.34, 44.26],
							[32.98, 44.28],
							[33.6, 44.26],
							[34.22, 44.24],
							[34.84, 44.19],
							[35.44, 44.19],
							[36.04, 44.18],
						]
					}]
				},
			}
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
	.intro{
		margin-top: 75upx;
		width: 90%;
		display: flex;
		flex-direction: row;
	}
	.introimg{
		height: 1000upx;
		width: 50%;
	}
	.words{
		margin-left: 100upx;
		width: 40%;
		align-items: center;
		justify-content: center;
	}
	.wordtitle{
		text-align: center;
		font-size: 60upx;
	}
	.wordcontent{
		margin-top: 50upx;
		font-size: 40upx;
		font-family: 'kaiti';
		text-align: center;
	}
	.datas {
		margin-top: 50upx;
		height: 700upx;
		width: 90%;
		display: flex;
		flex-direction: row;
	}
	.charts {
		height: 600upx;
		width: 60%;
	}
	
	.texts {
		width: 40%;
		align-items: center;
		justify-content: center;
	}
	
	.textitem{
		border: 2px solid blue;
		margin: 40upx;
		align-items: center;
		justify-content: center;
		text-align: center;
	}
</style>
