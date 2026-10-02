<p align="center"><strong>简体中文</strong> · <a href="README.en.md">English</a></p>

<p align="center"><img src="assets/mark.svg" width="88" height="88" alt="SuperZip"></p>

<h1 align="center">SuperZip</h1>

<p align="center">免费的极速压缩工具。</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases"><img src="assets/badges/version.svg" alt="v0.4.3 · Build46"></a>
  <img src="assets/badges/platform.svg" alt="macOS · Apple Silicon">
  <a href="#下载"><img src="assets/badges/windows.svg" alt="Windows · 尚未发布"></a>
  <a href="RELEASE-NOTES.md"><img src="assets/badges/status.svg" alt="Beta"></a>
</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases"><strong>下载 macOS 测试版</strong></a>
  &nbsp; · &nbsp;
  <a href="#安装">安装说明</a>
  &nbsp; · &nbsp;
  <a href="#性能实测">性能实测</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/NanLany/SuperZip/issues">问题反馈</a>
</p>

SuperZip 创建 `.szp` 压缩包，也能解压 ZIP、7z 和 RAR。默认按文件内容识别适用表格并尝试优化，其余文件使用普通压缩；可关闭“自动优化表格”。

本仓库用于发布下载、维护文档和收集问题反馈。SuperZip 自有核心与界面闭源。

> **Windows 测试版预计约一周后上线。** 发布前会完成 Windows 实机验证，具体时间以 Releases 公告为准。

## 下载

| 平台 | 当前状态 | 下载 |
| :-- | :-- | :-- |
| macOS · Apple Silicon | v0.4.3 · Build46 测试版 | [Releases](https://github.com/NanLany/SuperZip/releases) · DMG / ZIP |
| Windows | 预计约一周后上线 | 准备中 |

macOS 版本面向 M 系列 Mac，暂不支持 Intel。最低构建目标为 macOS 12，当前实测环境为 Apple M1、8 GB、macOS 26.2；较旧系统尚未逐版本验证。

## 安装

1. 在 [Releases](https://github.com/NanLany/SuperZip/releases) 下载 macOS DMG，打开后将 `SuperZip.app` 拖到窗口中的“应用程序”。也可下载 ZIP，解压后将完整的应用拖到“应用程序”。
2. 首次打开若提示 Apple 无法验证，点“完成”。
3. 打开 **系统设置 → 隐私与安全性 → 安全性 → 仍要打开**，按系统提示确认。

本测试版采用本地签名，尚未经过 Apple 公证。无需关闭系统安全保护，也不要求完全磁盘访问权限。

## 功能

| 操作 | 支持范围 |
| :-- | :-- |
| 压缩文件与文件夹 | 创建 `.szp`，尝试优化适用表格，并复用重复内容块 |
| 解压常用格式 | `.szp`、ZIP、7z、RAR／RAR5；常见密码包和分卷布局已验证 |
| 处理旧中文 ZIP | 可选 GBK 或 CP437，并在解压前预览文件名 |
| Finder 服务 | 右键 → 服务 → SuperZip 压缩或解压；每次选择一个项目 |

**`.szp` 需要 SuperZip 解压。** 分享压缩包时，请把本项目的下载入口一并发给接收方。当前版本不创建 ZIP、7z 或 RAR。

## 性能实测

在一个 **4.147 GB、23,792 个文件**的日常项目文件夹上，SuperZip 默认模式的结果：

| 压缩包大小 | 压缩时间 | 解压时间 |
| :-- | :-- | :-- |
| **2.543 GB** | **24.445 秒** | **6.817 秒** |

以上为 Apple M1、8 GB、macOS 26.2 上的五次中位数。耗时包含文件扫描与自动判断；文件内容不同，压缩收益也会不同。

[下载数据预览（HTML）](https://github.com/NanLany/SuperZip/releases/download/untagged-5d8c02b10cfb82c8eac1/data-preview.html) — 28 组数据，比较常用软件默认模式下的大小、压缩时间与解压时间。图表内可切换中文／English。

下载 `data-preview.html` 后，用 Safari、Chrome 或其他浏览器打开即可，无需联网。若双击打开了编辑器，请右键 → 打开方式 → 选择浏览器。仓库公开后，会提供直接浏览的在线页面。

## 使用前了解

- 使用新名称或新目录保存结果，不覆盖已有目标。解压分卷时，请将所有分卷放在同一个文件夹。
- 暂不还原权限、时间戳等元数据；不支持链接、特殊文件、自解压包，或同一包内不同文件分别设密码。
- 这是早期测试版，请保留原文件，不将生成的压缩包作为唯一备份。

## 反馈

如遇问题，请在 [Issues](https://github.com/NanLany/SuperZip/issues) 附上应用版本、操作系统版本、硬件型号、复现步骤和错误信息。一个不含个人信息或密码的小样本，会更方便我们定位问题。

## 技术与许可

<p>
  <img src="assets/badges/rust.svg" alt="Core · Rust">
  <img src="assets/badges/swift.svg" alt="macOS UI · Swift / AppKit">
  <img src="assets/badges/sevenzip.svg" alt="Archive compatibility · 7-Zip 26.03">
</p>

压缩核心使用 Rust，macOS 界面使用 Swift／AppKit，常用格式解压使用 7-Zip 26.03 动态库。

SuperZip 自有实现保持闭源，本仓库不包含其源码。7-Zip 的完整对应源码、许可与重建及动态库替换说明随应用提供，可从 **应用菜单 → 第三方许可**查看。第三方组件保留各自许可赋予的权利。

[版本说明](RELEASE-NOTES.md) · [English](README.en.md)
