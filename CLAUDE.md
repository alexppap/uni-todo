# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个基于 **uni-app x** 框架的跨平台待办事项应用（uni-todo）。uni-app x 是 DCloud 推出的下一代跨平台开发框架，支持编译到 App（Android/iOS）、小程序（微信/支付宝/百度/字节）等多个平台。

## 技术栈

- **框架**: uni-app x
- **UI 语言**: .uvue（uni-app x 的组件文件格式，类似 Vue 单文件组件）
- **逻辑语言**: UTS（uni-app TypeScript，一种类型化的跨平台语言）
- **样式**: SCSS + uni-app 内置样式变量系统
- **Vue 版本**: Vue 3（使用 SSR App 模式）

## 项目架构

### 核心文件结构

- **App.uvue**: 应用主入口组件
  - 包含应用生命周期钩子（onLaunch, onShow, onHide, onExit）
  - 实现了 Android/HarmonyOS 平台的双击返回键退出功能
  - 定义全局公共样式（.uni-row, .uni-column）

- **main.uts**: 应用启动文件
  - 使用 `createSSRApp` 创建 Vue 3 应用实例
  - 导入并挂载 App.uvue 组件

- **pages.json**: 页面路由配置
  - 定义应用的所有页面路径和导航栏样式
  - 第一项为应用启动页（pages/index/index）
  - 配置全局导航栏样式和背景色

- **manifest.json**: 应用配置清单
  - 定义应用基本信息（name, appid, version）
  - 配置各平台特有参数（小程序 appid、App 图标等）
  - 当前使用 Vue 3 版本

- **uni.scss**: 全局样式变量
  - 定义 uni-app 内置的常用样式变量（颜色、尺寸、间距等）
  - 可在任何 scss 文件中直接使用这些变量，无需 import

### 页面组织

- **pages/**: 存放所有页面
  - 每个页面为一个文件夹，包含 .uvue 文件
  - 页面使用 Vue 3 选项式 API（data, methods, onLoad 等生命周期）

## 开发注意事项

### 文件扩展名

- 页面和组件使用 `.uvue` 扩展名（不是 .vue）
- 逻辑代码使用 `.uts` 扩展名（不是 .ts 或 .js）

### 平台条件编译

项目使用条件编译语法来处理平台差异：
```
// #ifdef APP-ANDROID || APP-HARMONY
平台特定代码
// #endif
```

### 样式开发

- 可以直接使用 uni.scss 中定义的变量（如 `$uni-color-primary`）
- 布局使用 flex，提供了 `.uni-row` 和 `.uni-column` 公共类
- 尺寸单位推荐使用 rpx（响应式像素）或 px

### 应用生命周期

App.uvue 中实现的关键生命周期：
- `onLaunch`: 应用启动时触发
- `onShow`: 应用进入前台
- `onHide`: 应用进入后台
- `onLastPageBackPress`: 最后一页返回键处理（实现双击退出）
- `onExit`: 应用退出

### 核心原则
- **始终使用 Vue 3 组合式 API 的 `<script setup>` 语法**
- **模板部分应放置在 Vue 文件的顶部**
- **对函数使用具名导出**
- **变量使用驼峰命名法**
- **js代码符合前端Airbnb规范**

### js代码规范
- **forEach,find,map等方法时不要使用单个字母作为参数名，使用item,index等**
- **默认使用分号**
- **尽量遵循函数式编程原则，少使用push,splice等会改变原数组的方法，使用map,filter等返回新数组的方法**

## 构建和运行

uni-app x 项目通常通过 HBuilderX IDE 或 CLI 工具进行开发和构建。根据目标平台不同，使用相应的编译命令。编译产物会输出到 `unpackage/dist/` 目录。
