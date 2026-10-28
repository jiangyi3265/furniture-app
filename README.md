# furniture-app

家具项目的 uni-app 用户端初始工程，用于后续开发 H5、App 和小程序界面。

## 项目简介

本项目来自本地“家具”目录，是使用 HBuilderX 工程形式组织的 uni-app 应用。当前仅包含一个显示 Logo 和 Hello 文案的首页、应用生命周期入口、全局样式及多平台清单配置。

该工程与 `furniture-backend`、`furniture-admin` 同属家具项目；用户端尚未调用后端 API，也未实现登录、商品、购物车、订单、支付或用户中心。`manifest.json` 配置了 App、微信及其他小程序平台入口，这代表工程具备对应平台配置，不代表已发布或完成兼容性验证。

## 技术栈

- uni-app、Vue 3、JavaScript、Vue 单文件组件。
- HBuilderX 工程；`manifest.json` 的 `vueVersion` 为 `3`。
- Sass/SCSS 全局变量，`pages.json` 页面路由。
- `main.js` 保留 Vue 2/3 条件编译分支，当前配置使用 Vue 3。
- 项目没有 `package.json` 或 npm scripts，不能直接使用 `npm run dev` 启动。

## 关联仓库

| 项目 | 说明 | GitHub |
| --- | --- | --- |
| furniture-backend | 后端基础服务 | [furniture-backend](https://github.com/jiangyi3265/furniture-backend) |
| furniture-admin | Web 管理后台 | [furniture-admin](https://github.com/jiangyi3265/furniture-admin) |
| furniture-app | uni-app 用户端初始工程 | [furniture-app](https://github.com/jiangyi3265/furniture-app) |

## 快速启动

1. 在支持 uni-app / Vue 3 的 HBuilderX 中打开本仓库目录，确保 `manifest.json`、`pages.json` 与 `main.js` 位于工程根目录。
2. 使用 HBuilderX 的运行功能选择浏览器，查看当前 Hello 首页；本阶段无需数据库或后端即可预览。
3. 如需调试微信小程序，安装微信开发者工具，在本地 `manifest.json` 的 `mp-weixin.appid` 配置自己的 AppID，然后通过 HBuilderX 运行到小程序开发工具。该字段当前为空。
4. App 调试和打包需要相应设备、SDK 与签名配置；DCloud 应用标识应按自己的应用设置。签名证书、私钥、AppSecret 不得提交。

后续接入后端时，应自行增加请求封装、API 基础地址和认证逻辑，并与 `furniture-backend` 约定接口；当前代码没有可直接配置的 API 客户端。

## 项目结构

```text
pages/index/index.vue     唯一首页：Logo 和 Hello 文案
static/logo.png          首页静态图片
App.vue                  应用生命周期及全局样式入口
main.js                  Vue 应用初始化和条件编译
pages.json               页面路由及导航栏样式
manifest.json            应用标识、Vue 版本和多平台配置
uni.scss                 uni-app 样式变量
uni.promisify.adaptor.js  模板保留的 Promise 适配文件
index.html               H5 页面入口
```

## 配置与公开范围

`unpackage/`、`node_modules/`、HBuilderX/IDE 配置、环境文件、日志、签名证书与私钥均由 `.gitignore` 排除。公开的应用标识不是 AppSecret；不要把任何服务端密钥放入客户端工程。

## 简历描述示例

初始化基于 uni-app 与 Vue 3 的家具项目用户端，配置单页入口、应用生命周期和多平台清单，为后续客户端功能开发建立工程基础。该阶段仅完成工程初始化，不应描述为已交付商城或订单系统。
