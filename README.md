# wall-sdk

wall-sdk 是 wall 监听系统的前端 SDK，负责收集前端信息

## 主要性能

1.  采用 express 中间件， 可以快速处理 [event](#event)
2.  监听用户行为：用户点击，路由改变，用户请求， 资源加载
3.  [indexDB](https://github.com/xmoyking/localForage-cn) 存储，可以追寻用户行为路径，可以追踪到错误发生之前的用户行为
4.  适用 `vue` `react` 微信小程序
5.  监控: 普通错误，primose 异常， console.error, 图片加载错误， xhr 错误，fetch 错误
6.  可以上传自定义错误
7.  可以自定义用户行为//TODO: demo
8.  对 ERROR 设置上报频率
9.  performance 页面性能数据
10. TS 搭建

## npm 引用

```
npm install wall-sdk --save
```

```
import  Wall from 'wall-sdk'

Wall.init({
  token: xxxxxxxxxx, // 项目标识
  frequency: 1, // 上报频率（只针对错误和用户行为，页面性能相关，每天上报一次）
  // 敏感请求参数（post get）参数加密方式
  paramEncryption: value => {
    return JSON.stringify(value);
  }
});

```

## vue 使用

## react 使用

## 快速开始

进入目录安装依赖:

```bash
npm i 或者 yarn install
```

开发：

```bash
npm run start
打开 http://localhost:8001
```

打包

```
npm run build:deploy
```

测试：

## event 说明

### <a id="event">event</a>

## //TODO:

1. 崩溃和卡顿
2. sourceMap
3. webpack 插件
4. 测试
5. 用户访问应用次数记录统计(记录第一次加载， 记录刷新) session pv
6. 每个页面首次加载时间统计(记录第一次加载) uv
