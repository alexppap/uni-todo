# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

基于 **uni-app** 框架的跨平台应用（hello-uniapp 示例工程），支持同时发行到 iOS、Android、H5、微信/支付宝/百度/字节跳动等小程序平台。同时兼容 Vue 2 和 Vue 3。

## 开发环境

- **推荐 IDE**: HBuilderX（App 开发版），内置 uni-app 编译环境，开箱即用
- **引擎要求**: HBuilderX >= 3.1.0, uni-app >= 4.03
- **CLI 方式**: 也可通过 `vue create -p dcloudio/uni-preset-vue` 创建，然后 `npm run dev:h5` 运行 H5 端

## 构建与运行

此项目主要通过 HBuilderX 进行编译运行（菜单 → 运行 → 选择目标平台）。package.json 中未定义自定义 build/lint 脚本。如果使用 CLI 模式：

- H5 端开发: `npm run dev:h5`
- 各小程序端: `npm run dev:mp-weixin` / `npm run dev:mp-alipay` 等

## 架构要点

### 条件编译

项目大量使用 uni-app 条件编译语法，在 JS/Vue/CSS/JSON 中通过注释指令控制代码在不同平台的编译：
- `// #ifdef APP-PLUS` / `// #endif` — 仅 App 端
- `// #ifdef H5` — 仅 H5 端
- `// #ifdef MP-WEIXIN` — 仅微信小程序
- `// #ifndef VUE3` / `// #ifdef VUE3` — Vue 2/3 差异代码

修改代码时必须注意条件编译块的范围，避免破坏平台兼容性。

### Vue 2/3 双版本兼容

`main.js` 同时包含 Vue 2 和 Vue 3 的入口逻辑，通过条件编译切换。Vue 3 模式额外集成了 Pinia。

### 状态管理

- **Vuex**: `store/index.js`，Vue 2/3 均使用，管理登录状态、UI 状态等
- **Pinia**: 仅 Vue 3 模式下启用（`store/counter.js`）

### 页面结构

- `pages.json` — 路由与页面配置（含条件编译），定义了 tabBar 四个主入口：内置组件、接口、扩展组件、模板
- 主包页面: `pages/tabBar/` (四个 tab 页) + `pages/component/` (内置组件演示)
- 分包: `pages/API/`（API 示例）、`pages/extUI/`（扩展 UI 组件）、`pages/template/`（模板示例）
- 平台特定页面: `platforms/app-plus/`（仅 App 端功能如推送、传感器等）

### uni_modules

项目通过 `uni_modules/` 目录管理 uni-app 扩展组件（uni-ui 系列），这些是独立的模块化组件，通过 HBuilderX 插件市场管理，不要手动修改其内部代码。

### 宽屏适配

`windows/` 目录包含 `left-window.vue` 和 `top-window.vue`，用于 H5 宽屏下的多窗口布局。

## 样式

- 全局样式: `App.vue` 中引入 `uni_modules/uni-scss` 和 `common/uni.css`
- 使用 `rpx` 作为响应式单位
- 自定义图标: `static/customicons.css` 和 `static/iconfont.css`

## 开发规范
- 所有 Vue 组件均使用单文件组件（SFC）格式
- 所有样式均使用 scoped 模式，避免全局污染
- 所有 JS 代码均使用 airbnb 规范
- 所有 uni-app 扩展组件均通过 uni_modules 引入，不要手动修改其内部代码
