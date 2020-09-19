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
