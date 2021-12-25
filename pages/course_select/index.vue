<template>
	<view class="u-page">
		<!-- 搜索框 -->
		<view class="u-demo-block">
			<text class="u-demo-block__title">课程搜索</text>
			<view class="u-demo-block__content">
				<view class="u-page__tag-item">
					<u-search
						v-model="keyword"
						:show-action="false"
						@change="change"
					></u-search>
				</view>
			</view>
		</view>
		<!-- 课程推荐 -->
		<view class="u-demo-block">
			<text class="u-demo-block__title">为你推荐：</text>
			<view class="u-demo-block__content">
					<u-grid :border="true">
						<u-grid-item
							v-for="(listItem,listIndex) in list"
							:key="listIndex"
							customStyle="padding-top: 10px; padding-bottom: 10px" 
						>
							<u-icon
								:customStyle="{paddingTop:20+'rpx'}"
								:name="listItem.name"
								:size="22"
							></u-icon>
							<text class="grid-text">{{listItem.title}}</text>
						</u-grid-item>
					</u-grid>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				keyword: '',
				list: [{
						name: 'photo',
						title: '课程1'
					},
					{
						name: 'lock',
						title: '课程2'
					},
					{
						name: 'star',
						title: '课程3'
					},
					{
						name: 'hourglass',
						title: '课程4'
					},
					{
						name: 'home',
						title: '课程5'
					},
					{
						name: 'volume',
						title: '课程6'
					},
					{
							name: 'photo',
							title: '课程7'
						},
						{
							name: 'lock',
							title: '课程8'
						},
						{
							name: 'star',
							title: '课程9'
						},
				],
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.grid-text {
		font-size: 14px;
		color: #909399;
		padding: 10rpx 0 20rpx 0rpx;
		/* #ifndef APP-PLUS */
		box-sizing: border-box;
		/* #endif */
	}
</style>
