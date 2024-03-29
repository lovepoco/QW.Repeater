# QW.Repeater
* 基于Jquery(>1.7)结合模板引擎的重复数据展示组件
* 默认使用arttemplate.js
* Author：[戴子意 DZY](http://www.daiziyi.com/)
* 感谢我的妻子前前，还有调皮的儿子琮琮和璋璋
* 代码维护地址已迁移至：https://gitee.com/u5web/QW.Repeater

# Usage
## writing
```javascript
$("选择器").QWRepeater({参数});
```
## examples
```javascript
$("#box").QWRepeater({
        tmplId: "#datatmpl",
        data: data
    });
```
	
# Property
| 名称 | 说明  | 提示 |
| ------------ | ------------ | ------------ |
| container| 容器 | 回调事件中可以访问 |
| options| 参数 | 见下表 |

# Parameter
| 名称 | 说明  | 默认值  | 示例  | 提示 |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| tmplId| 模板DOM | "#datatmpl" | - | jquery选择器 |
| tmplContent| 模板内容 | "" | - | tmpId优先级更高 |
| url| url地址 | null | - | 返回值为json |
| urlParameter| url参数 | null | - | - |
| urlMethod| 请求方式 | "get" | - | - |
| urlDataType| 数据格式 | "json" | - | - |
| data| 静态数据 | null | - | url优先级更高 | 
| needEmpty| 是否清空容器 | true | - | 为false适用于下拉加载 |
| external| 外部参数 | null | - | 组件本身不使用此参数 |
| isNullData| 空值判定方法 | function (d) {return !d;} |  | 回调参数为静态数据data |
| onBeforeLoadData| 数据加载前 | null | function (o) {} | 回调参数为实例的options |
| onLoadDataed| 数据加载后 | null | function (o) {} | 回调参数为实例的options |
| onBeforeDraw| 界面绘制前事件 | null | function (t) {} | 回调参数为实例容器 |
| onRender| 模板渲染过程 | null | function (o) {} | 回调参数为options |
| onDrawed| 界面绘制后事件 | null | function (t) {}  | 回调参数为实例容器 |

# Method
## option 设置获取选项
* options 选填 参数
```javascript
var opts=databox.QWRepeater("option", { tmplId: "#datatmpl2", });
```
## reload 刷新显示
* options 选填 参数
```javascript
databox.QWRepeater("reload", { tmplId: "#datatmpl2", });
```
## reloadData 刷新显示,更新数据
* data 选填 数据
```javascript
databox.QWRepeater("reloadData", { rows[{name:"1"},{name:"2"}],total:20});
```
## reloadUrl 刷新显示
* urlParameter 选填 url参数
```javascript
databox.QWRepeater("reloadUrl", { page:2 });
```
## loading 显示加载提示
* isEmpty 选填 是否清空容器
```javascript
databox.QWRepeater("loading",true);
```
## loaded 隐藏加载提示
```javascript
databox.QWRepeater("loaded");
```
## destroy 释放实例
```javascript
databox.QWRepeater("destroy");
```
## external 设置获取外部参数
* external 选填 外部参数
```javascript
var exdata=databox.QWRepeater("external");
```
