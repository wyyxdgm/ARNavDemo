# AR 导航

![](./logo.jpg)

## 准备

申请地图 key

## 使用

* wxml

```wxml
<navigator id="nav" url="plugin://SPMinaNavPlugin/discover">
  Go to Plugin page
</navigator>
```

* js

```js
var plugin = requirePlugin("SPMinaNavPlugin");
App({
  onLaunch: function () {
    // 设置 腾讯地图WebService-开发者密钥(key)
    const keys = ["key1", "key2", "key3"]; // 任意个，至少一个，随机选用
    plugin.initMapKeys(keys);
  },
});
```
