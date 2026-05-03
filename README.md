# Toc Bar

一个油猴脚本，在页面中插入一个显示当前内容大纲的浮动组件，修改自 [toc-bar-userscript](https://greasyfork.org/zh-CN/scripts/406337-toc-bar-auto-generating-table-of-content)

[![Install](https://img.shields.io/badge/Install-v1.9.11-blue)](https://raw.githubusercontent.com/AnicSuny/toc-bar-userscript/main/toc-bar.user.js)

## ✨Features

- 使用 [tocbot](https://tscanlin.github.io/tocbot) 生成 Table of Content
- 对一些页面中 `h*` 标签不带 id 的网站，生成 id，以实现点击 TOC 标题跳转到对应内容的功能
- 不想使用的时候，组件可以一键折叠，避免挡住正在浏览的内容

## Screenshots

![tocbar-github.png](https://raw.githubusercontent.com/AnicSuny/toc-bar-userscript/master/images/screenshot-3.png)

![devto](https://raw.githubusercontent.com/AnicSuny/toc-bar-userscript/master/images/screenshot-2.png)

![zhuanlan-sspai](https://raw.githubusercontent.com/AnicSuny/toc-bar-userscript/master/images/screenshot-1.jpg)

## Changelog

### v1.9.10

| 问题 | 说明 |
|------|------|
| POSITION_STORAGE key 不一致 | `location.host` → `location.hostname`，非标准端口场景下位置存储不再错位 |
| getSiteInfo() 无效正则回退 | 移除永远匹配不到 SITE_SETTINGS 的死代码分支 |
| dragState 死代码 | 移除只写不读的 `curTop` / `curOffset` |
| getPageTocOptions 冗余展开 | 简化不必要的 `{...spread}` 对象拷贝 |
| dev.to shouldShow 可读性 | `.every(!x)` → `!.some(x)` |
| console.log 残留 | 删除两处 debug 日志 |
| 空 TOC 面板 | 页面无标题时不再显示空白浮动组件 |
| ThemeController 重复监听 | `initSystemListener` 加重复调用守卫 |
| toggle() 参数语义 | `shouldShow` → `visible`，明确参数为状态设值 |
| SPA URL 检测 | `history.pushState` 仅在 URL 实际变化时才触发 TOC 重建 |
