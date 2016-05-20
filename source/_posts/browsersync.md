---
title: browsersync
date: 2016-05-20 15:33:10
tags: 前端调试
---

# 省时的浏览器同步测试工具

Browsersync能让浏览器实时、快速响应您的文件更改（html、js、css、sass、less等）并自动刷新页面。更重要的是 Browsersync可以同时在PC、平板、手机等设备下进项调试。您可以想象一下：“假设您的桌子上有pc、ipad、iphone、android等设备，同时打开了您需要调试的页面，当您使用browsersync后，您的任何一次代码保存，以上的设备都会同时显示您的改动”。无论您是前端还是后端工程师，使用它将提高您30%的工作效率。

有了它，您不用在多个浏览器、多个设备间来回切换，频繁的刷新页面。更神奇的是您在一个浏览器中滚动页面、点击等行为也会同步到其他浏览器和设备中，这一切还可以通过可视化界面来控制。

### 1. 简化操作流程

每个网页在不同设备的浏览器里，测试时间呈指数级增长，无论是PC还是移动端。曾经我们每改一次的代码，都需要手动去刷新一次页面，查看我们的改动是否正确；现在，BrowserSync减少了重复的手工任务，这一切都交给BrowserSync去完成，我们只需专注在业务的逻辑里去。

### 2. 工作中您需要它

BrowserSync是建立在网络技术上的，您可以轻松安装在OS X，Windows或Linux上，然后在不同的设备及浏览器里进行调试。就连UI都可以运行在浏览器 - 尝试在另一台设备上创建第二页面来控制您的BrowserSync。

### 3. 插入到您的工作流程

通过可视化的操作方式或命令行来创建个性化的测试环境，多设备共同响应。BrowserSync很容易与您的网络平台集成，构建工具和其他Node项目中，例如gulp、grunt。

安装
``` bash
npm install --save-dev browser-sync
```

启动 BrowserSync
静态网站
``` bash
// --files 路径是相对于运行该命令的项目（目录） 
browser-sync start --server --files "**/*.css, **/*.html"
```
动态网站
``` bash
// 主机名可以是ip或域名
browser-sync start --proxy "主机名"[Browsersync.cn] "css/*.css"
```