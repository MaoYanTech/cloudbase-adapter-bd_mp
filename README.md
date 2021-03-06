# cloudbase-adapter-bd_mp
[腾讯云服务（tcb-js-sdk）](https://cloud.tencent.com/product/tcb?from=12334)百度智能小程序适配器

## 安装
```bash
npm i @maoyan/cloudbase-adapter-bd_mp -S
```

## 使用

由于百度智能小程序没有提供getAccountInfoSync()接口,无法通过接口获取appId
所以需要将appId设置到小程序app对象上

```
App({
  onLaunch(options) {
    this.appId = appId
  }
})
```

### ES Module
```javascript
import tcb from 'tsb-js-sdk';
import adapter from 'cloudbase-adapter-bd_mp';

// 以下两种方式二选一
// 1.单参数传入
tcb.useAdapters(adapter);
// 2.数组形式传参
tcb.useAdapters([adapter]);
// adapter必须在init之前传入
tcb.init();
```

### CommonJS
```javascript
const tcb = require('tsb-js-sdk');
const {adapter} = require('cloudbase-adapter-bd_mp');

// 以下两种方式二选一
// 1.单参数传入
tcb.useAdapters(adapter);
// 2.数组形式传参
tcb.useAdapters([adapter]);
// adapter必须在init之前传入
tcb.init();
```