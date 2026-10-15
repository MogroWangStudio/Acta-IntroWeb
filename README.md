# Acta 行记 · 介绍页（Acta IntroWeb）

「[Acta·行记](https://acta.mogrowangstudio.top)」的官方网站与产品介绍页。Acta 是一个**本地优先、开源**的笔记与待办应用：笔记和待办放进同一个工作区，从想法到行动不用切换软件。

- 产品主仓库与下载：<https://github.com/MogroWang/Acta>
- 网页版（PWA）：<https://actaweb.mogrowangstudio.top>
- 工作室官网：<https://www.mogrowangstudio.top/>

## 这个仓库是什么

Acta 的落地页（landing page），部署于 GitHub Pages，域名 `acta.mogrowangstudio.top`。页面介绍 Acta 的核心特性并提供各平台下载入口。

**整个站点就是一个 `index.html`**：无框架、无构建、零运行时依赖，样式内联、脚本原生，克隆即改，推送即上线。

## 页面内容

- **特性介绍** —— 笔记与待办同工作区、笔记/待办双向关联、打卡式待办与子任务（顺序执行、批量添加、导出清单）、年/月/周/日四层日历、本地优先与 WebDAV / 局域网直接互传同步、回收站与操作历史回溯
- **平台矩阵** —— 桌面端（Tauri，Windows / macOS）、Android（Capacitor 8，APK，应用内自动更新）、网页版（PWA，离线缓存，iOS/iPadOS 临时性支持）、界面语言（简体中文 / 繁體中文 / English）
- **下载区** —— 指向 GitHub Releases（Windows 便携版、macOS DMG、Android APK）与网页版
- **中英双语** —— 右上角切换，选择记忆在 `localStorage`（键 `acta-intro-lang`）

## 一些实现细节

- **顶栏** —— 滚动超过 5% 后收缩为一枚悬浮玻璃胶囊；下层内容通过渐变遮罩的背景模糊自然消隐
- **环境背景** —— 一层若隐若现的涟漪、自绘对勾与书写线条循环动效，纯 CSS 实现，`pointer-events: none`
- **触屏下拉刷新** —— 从顶部下拉触发的自定义刷新指示器，随拉伸进度填充对勾或笔记笔画，随机二选一
- **无障碍与偏好** —— 完整响应 `prefers-reduced-motion` / `prefers-reduced-transparency` / `prefers-contrast`，弹窗与菜单带焦点管理与 `aria` 标注

## 本地预览

无构建步骤，任意静态服务器即可：

```bash
# 仓库根目录下任选其一
python -m http.server 8000
npx serve .
```

然后打开 <http://localhost:8000>。

## 目录结构

```
.
├── index.html    # 全部页面（结构 + 样式 + 脚本）
├── CNAME         # GitHub Pages 自定义域名
└── assets/
    ├── acta-logo.svg / .png     # Acta 标识
    ├── mogrowang-studio.svg     # 工作室字标（页脚）
    └── preview-*.png            # 产品截图
```

## 版本

采用**日期版本号**（`YYYYMMDD`），每次页面更新递增，明细见 [CHANGELOG.md](CHANGELOG.md)。当前版本：**20261015**，同时展示于页面页脚。

## 许可

代码以 [MIT License](LICENSE) 发布。© 2026 [MogroWang Studio](https://www.mogrowangstudio.top/)。
