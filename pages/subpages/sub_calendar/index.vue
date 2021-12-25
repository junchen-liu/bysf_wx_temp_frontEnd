<template>
	<view class="u-page">
		<u-navbar
			title="日历"
			@leftClick="navigateBack"
			safeAreaInsetTop
			fixed
			placeholder
		></u-navbar>
		<u-cell-group>
			<u-cell
				@click="showCalendar"
				:title="title"
				:key="index"
				isLink
			>
			</u-cell>
		</u-cell-group>
		
		<u-calendar
			:show="ifShow"
			mode="range"
			@confirm="confirm"
			@close="close"
			:defaultDate="customTextDefaultDate"
			startText="开始"
			endText="结束"
			confirmDisabledText="请选择日期"
			:formatter="formatter"
		></u-calendar>
	</view>
</template>


<script>
export default {
		data() {
			const d = new Date()
			const year = d.getFullYear()
			let month = d.getMonth() + 1
			month = month < 10 ? `0${month}` : month
			const date = d.getDate()
			return {
				index: 0,
				ifShow: true,
				title:"显示校历",
				customThemeDefaultDate: [`${year}-${month}-${date}`, `${year}-${month}-${date + 5}`], 
				customTextDefaultDate: [`${year}-${month}-${date}`],
				maxDate: `${year}-${month}-${date + 10}`,
				defaultDateMultiple: [`${year}-${month}-${date}`, `${year}-${month}-${date + 1}`, `${year}-${month}-${date + 2}`],
			}
		},
		methods: {
			showCalendar() {
				this[`ifShow`] = true
			},
			navigateBack() {
				uni.navigateBack();
			},
			confirm(e) {
				this[`show${this.index}`] = false
			},
			close() {
				this[`ifShow`] = false
			},
			formatter(day) {
				const d = new Date()
				let month = d.getMonth() + 1
				const date = d.getDate()
				if(day.month == month && day.day == date + 3) {
					day.bottomInfo = '寒假'
					day.dot = true
				}
				return day
			}
		},
	}
</script>

<style lang="scss">
	.u-page {
		padding: 0;
	}
</style>