# noname-PWA

无名杀的 “渐进式网络应用程序 (Progressive Web App)” 版本 —— [点击体验](https://raineggplant.github.io/noname-PWA) ！

## 简介

本仓库基于 [无名杀网页版](https://github.com/libccy/noname) 构建了 PWA 版本。简言之，相比原网页版，PWA 技术使得无名杀能够借助浏览器轻松地进行**跨平台安装**，为用户提供接近原生应用的体验，可以做到**按需加载**、**离线运行**、**自动更新**等。当然，即使不安装到本地，用户**仍旧可以直接通过浏览器**进行游戏（即所谓的 "Progressive"）。有关 PWA 的详细介绍请参见 [维基百科](https://zh.wikipedia.org/wiki/渐进式网络应用程序)。

## 改动

为了添加 PWA 支持，主要针对原网页版做了如下改动：

1. 增加了 PWA 相关的配置文件与资源文件。
2. 由于 PWA 要求通过 HTTPS 提供服务，因此联机时默认采用 WSS 协议，如需使用不安全的 WS 协议，则应明确指定协议，例如 `ws://example.com` 。
   - 注意：一般情况下，在使用 HTTPS 时 WS 协议会被浏览器安全策略阻止（除非连接的是本机地址）。如果您必须使用 WS 协议（不推荐），则您无法再使用 PWA 方式而只能通过浏览器进行游戏。此时您需要通过 HTTP 协议访问无名杀的站点，或者更改浏览器的安全策略。
3. 针对 Android 设备，增加了 “连续两次返回键退出” 功能，避免误触退出游戏。
4. 将 ttf 字体替换为 woff2 格式，以减小文件体积。
5. 分离了网页前端和服务器的代码。

## 游戏与安装

### A. 安装 PWA 到本地（支持离线游戏）

#### Windows / Linux / Mac / Android

推荐使用基于 Chromium 内核的浏览器（如 Chrome, 新版 Edge）访问无名杀的站点地址进行安装，Firefox 可能存在显示 bug。

#### iOS

iOS 仅 Safari 浏览器可以安装 PWA，请访问无名杀的站点地址，点击分享按钮，将无名杀添加到主屏幕。

### B. 网页版

推荐使用基于 Chromium 内核的浏览器（如 Chrome, 新版 Edge），访问无名杀的站点地址即可开始游戏。

### 注意：

Safari 用户如果要使用联机功能，请启用实验性功能中的 `NSURLSession WebSocket`。
