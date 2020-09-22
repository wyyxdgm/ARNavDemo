# AR 导航

![](./logo.jpg)

## 准备

* [申请地图 key](https://lbs.qq.com/service/webService/webServiceGuide/webServiceOverview)

* 申请插件使用权限 `"provider": "wx7710a29f1fb62aa7"`

## 使用

1. 全局配置插件

```json
// app.json
{
  "plugins": {
    "SPMinaNavPlugin": {
      "version": "0.0.1",
      "provider": "wx7710a29f1fb62aa7"
    }
  },
  "permission": {
    "scope.userLocation": {
      "desc": "你的位置信息将用于小程序位置接口的效果展示"
    }
  }
}
```

2. 打开页面之前需要先设置好地图秘钥

```js
// app.js
var plugin = requirePlugin("SPMinaNavPlugin");
App({
  onLaunch: function () {
    // 设置 腾讯地图WebService-开发者密钥(key)
    const keys = ["key1", "key2", "key3"]; // 任意个，至少一个，随机选用
    plugin.initMapKeys(keys);
  },
});
```

3. 页面跳转插件

```xml
<!-- some-page.wxml -->
<navigator id="nav" url="plugin://SPMinaNavPlugin/discover">
  Go to Plugin page
</navigator>
```

## 其他

* 为保证AR导航体验，请用于5公里范围内

* [备用文档](https://github.com/wyyxdgm/ARNavDemo)

## 更新日志

#### 0.1.0 -- 定制UI(v1)、修复一些已知bug、优化交互体验
  1. 更新UI：方向图标、目的地图标、地图边框等
  2. 修复点击退出后延迟退出
  3. 修复iphone6s的地图显示适配
  4. 修复位置获取失败时就停留在摄像头那个状态
  5. 终点距离调整为E4馆中心点30m范围内，如果在终点开启导航将提示并回退

#### 0.0.1 -- 基础版本首发
  1. 基础AR导航功能: 地图导航、方向识别、相机AR导航