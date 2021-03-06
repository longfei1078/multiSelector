# 微信小程序多选组件
类似与小程序`picker`组件的多项选择组件
## 效果
![](https://github.com/fchengjin/multiSelector/blob/master/images/showvalue-true.gif)
![](https://github.com/fchengjin/multiSelector/blob/master/images/showvalue-false.gif)
## How to use
example.json
```json
{
  "usingComponents": {
    "multi-selector": "/components/multiSelector/multiSelector"
  }
}
```
example.wxml
```html
<multi-selector class='selector' value='{{value}}' bindchange='bindSelectorChange' bindmodalopen='onModalOpen' placeholder='请选择你喜欢的水果' items='{{items}}' bindmodalclose='onModalClose' show-value='{{false}}'></multi-selector>
```
example.js
```js
Page({
  data: {
    value: ['A','B','D','F','G'],
    items: [{name: 'A',value: '苹果'},{name: 'B',value: '橘子'},{name: 'C',value: '香蕉'},{name: 'D',value: '西瓜'},{name: 'E',value: '梨子'},{name: 'F',value:'火龙果'},{name: 'G',value: '车厘子'}]
  },
  //事件处理函数

  onLoad: function () {

  },
  onModalOpen(){

  },
  onModalClose(){

  },
  bindSelectorChange(e){
	this.setData({
		value: e.detail.value
	})
  }
})
```

## 属性说明
| 属性名 | 类型 | 默认值 | 说明 |
|-----| ----- | ----- | ----- |
| value | Array | `[]` | 默认选择的值 |
| items | Array | `[]` | 数组每一项包含{name: '',value: ''} |
| placeholder | String | `''`| 输入框为空时占位符	|
| placeholder-class	| String |  `"input-placeholder"` |	指定 placeholder 的样式类 |
|placeholder-style | String | |指定 placeholder 的样式 |
| disabled | Boolean | false | 是否被禁用 |
| show-value | Boolean | `true` | 结果显示的是选择的值，还是已选中的每一项（有点绕，请看上面的图）|
| close-on-click-modal | Boolean| `true`  | 点击遮罩层是否关闭选择区 |
| cancel-button-text | String | `'取消'` | 取消键文字 |
| confirm-button-text | String | `'确定'` | 确定键文字 |

## 事件说明

| 事件名  |  说明 |
|-----| ----- |
| change | 点击确定时触发，通过e.detail.value获得组件的值 |
| modalopen | 选择区打开时触发 |
| modalclose | 选择区关闭时触发| 


## 一些tips
- 滑动的时候禁止页面跟随滑动，通过`modalopen`和`modalclose`动态修改页面的overflow
## todos
- [ ] 优化动画效果 

