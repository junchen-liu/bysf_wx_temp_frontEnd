<template>
	<view class="u-content">
		<u-parse container-style="padding: 20px" :content="content" domain="https://6874-html-foe72-1259071903.tcb.qcloud.la/demo" lazy-load scroll-table selectable use-anchor :tag-style="tagStyle" @load="load" @ready="ready" @imgTap="imgTap" @linkTap="linkTap" />
	</view>
</template>

<script>
	const content = `<table width="500px" cellspacing="0" cellpadding="5">
      <thead>
        <tr>
          <th>标题 1</th>
          <th>标题 2</th>
          <th>标题 3</th>
          <th>标题 4</th>
          <th>标题 5</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td align="center">内容 1</td>
          <td align="center">内容 2</td>
          <td align="center">内容 3</td>
          <td align="center">内容 4</td>
          <td align="center">内容 5</td>
        </tr>
        <tr style="background-color: #f6f8fa;">
          <td align="center"><a>链接</a></td>
          <td align="center">内容 7</td>
          <td align="center">内容 8</td>
          <td align="center">内容 9</td>
          <td align="center">内容 10</td>
        </tr>
        <tr>
          <td align="center">内容 11</td>
          <td align="center">内容 12</td>
          <td align="center">内容 13</td>
          <td align="center">内容 14</td>
          <td align="center">内容 15</td>
        </tr>
      </tbody>
    </table>
    <div style="font-size: 12px; color: gray; text-align: center; margin-top: 5px;">！仅参考！</div>`//require('./content')
	export default {
		data() {
			return {
				content: '',
				tagStyle: {
					table: 'box-sizing: border-box; border-top: 1px solid #dfe2e5; border-left: 1px solid #dfe2e5;',
					th: 'border-right: 1px solid #dfe2e5; border-bottom: 1px solid #dfe2e5;',
					td: 'border-right: 1px solid #dfe2e5; border-bottom: 1px solid #dfe2e5;',
					li: 'margin: 5px 0;'
				}
			}
		},
		onLoad() {
			// 模拟网络请求
			setTimeout(() => {
				this.content = content
			}, 200)
		},
		methods: {
			load() {
				// dom 结构加载完毕时触发
			},
			ready() {
				// 渲染完毕时触发
			},
			imgTap() {
				// 图片被点击时触发
			},
			linkTap() {
				// 链接被点击时触发
			}
		}
	}
</script>

<style lang="scss">
	.u-content {
		padding: 24rpx;
		font-size: 32rpx;
		color: $u-content-color;
		line-height: 1.6;
	}
</style>
