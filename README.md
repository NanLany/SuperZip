<p align="center">
  <img src="assets/mark.svg" width="76" height="76" alt="SuperZip">
</p>

<h1 align="center">SuperZip</h1>

<p align="center"><strong>轻量原生压缩，让文件自己选择合适的处理方式。</strong></p>
<p align="center">免费使用 · Apple Silicon · 默认自动优化表格 · 自有程序闭源</p>

<p align="center">
  <a href="https://github.com/NanLany/SuperZip/releases"><strong>下载 macOS 测试版 ↗</strong></a>
  &nbsp; · &nbsp;
  <a href="#安装只需几步">安装说明</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/NanLany/SuperZip/blob/main/docs/benchmarks.html">性能实测</a>
  &nbsp; · &nbsp;
  <a href="https://github.com/NanLany/SuperZip/issues">反馈问题</a>
</p>

<p align="center">v0.4.3 · Build46 · M 系列 Mac · ZIP 下载约 5.22 MB</p>

<p align="center">
  <img src="assets/superzip-window46.png" width="510" alt="SuperZip Build46 实际界面：压缩文件、压缩文件夹、解压，以及默认勾选的自动优化表格。截图裁去系统标题栏。">
</p>

## 一次选择，自动处理

把文件或文件夹交给 SuperZip。默认逐文件识别适用表格并尝试专用优化，其余文件沿用普通压缩，原始内容保持不变。也可以关闭“自动优化表格”。

| 功能 | 当前版本支持 |
| :-- | :-- |
| 文件与文件夹压缩 | 创建 `.szp`，自动处理适用表格并复用重复内容块 |
| 常用压缩包解压 | `.szp`、ZIP、7z、RAR／RAR5，以及已验证的常见密码包和分卷 |
| 旧中文 ZIP | 选择 GBK 或 CP437，解压前预览文件名 |
| Finder 服务 | 右键 → 服务 → SuperZip 压缩或解压，每次选择一个项目 |

**`.szp` 需要 SuperZip 解压。** 给别人分享压缩包时，请一并提供本页面的下载入口。当前版本不创建 ZIP、7z 或 RAR。

## 看实际文件的结果

4.147 GB 日常项目文件夹，23,792 个文件，SuperZip 默认模式：

| 压缩包大小 | 压缩时间 | 解压时间 |
| :-- | :-- | :-- |
| **2.543 GB** | **24.445 秒** | **6.817 秒** |

以上为 Apple M1、8 GB、macOS 26.2 上的五次中位数，耗时包含文件扫描和自动判断。实际收益随文件内容变化。[28 组数据与常用软件的默认模式对比 →](https://github.com/NanLany/SuperZip/blob/main/docs/benchmarks.html)

仓库中的性能页面为独立 HTML。私有预览阶段可下载后直接打开；正式公开时提供网页浏览入口。

## 安装只需几步

1. 在 [Releases](https://github.com/NanLany/SuperZip/releases) 下载 macOS ZIP，解压后将完整的 `SuperZip.app` 拖到“应用程序”。
2. 打开一次应用。若系统提示 Apple 无法验证，点“完成”。
3. 到 **系统设置 → 隐私与安全性 → 安全性 → 仍要打开**，按系统提示确认。

本测试版使用本地签名，未经过 Apple 公证；不需要关闭系统安全保护。选择需要压缩或解压的位置即可，应用不要求完全磁盘访问权限。

仅支持 **Apple Silicon（M 系列）**。构建最低系统目标为 macOS 12，当前实测为 macOS 26.2；较旧系统尚未逐版本验收。Intel Mac 暂不支持，Windows 尚未完成实际设备验收，本次不提供下载。

## 使用前了解

- 保存结果需使用新名称或新目录，不覆盖已有目标；所有分卷应放在同一个文件夹。
- 暂不还原权限、时间戳等元数据，不支持链接、特殊文件、自解压包或同一包内不同文件分别设密码。
- 测试版请保留原文件，不将生成的压缩包作为唯一备份。

## 反馈与许可

遇到问题，请在 [Issues](https://github.com/NanLany/SuperZip/issues) 提供应用版本、Mac 芯片、macOS 版本、操作步骤和错误文字。能复现问题的小样本更有帮助，请先移除个人信息与密码。

SuperZip 自有核心、压缩策略与界面保持闭源。这个仓库提供产品介绍、发布文件和问题反馈，不包含自有实现源码。7-Zip 26.03 的完整对应源码、许可与重建及动态库替换说明随应用提供，可从“应用菜单 → 第三方许可”查看；第三方组件保留各自许可赋予的权利。
