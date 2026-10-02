<p><a href="#简体中文">简体中文</a> · <a href="#english">English</a></p>

# SuperZip v0.4.4 · Build51

## 简体中文

本次在 v0.4.3 / Build48 基础上增加 ZIP 输出和批量处理。这是 Apple Silicon macOS 测试版。

### 新增与改进

- 主窗口统一提供压缩、解压、文件选择和格式设置，开始前可确认项目与选项。
- 新增标准 ZIP 输出，可用常见压缩工具解压；不支持表格优化、加密或分卷。SZP 保留默认表格优化与重复内容块复用。
- 一次最多选择 256 个项目，逐项处理，每项单独保存。批量只需选择一个保存文件夹；重名时添加编号，不覆盖已有文件。
- 失败后继续下一项。密码或文件名预览中的“跳过此项目”只跳过当前项；主窗口“取消”停止当前与待处理项目，保留已完成结果。

### 修复

修复批次运行或密码、预览、保存对话框打开时无法正常退出的问题。菜单退出、Command-Q 和关闭窗口会结束未完成任务、清理临时结果，保留已完成结果。

### 延续功能

沿用 Build48 的中英界面和 GitHub 更新检查。系统首选语言为中文（含繁体）时显示简体中文，否则英文；手动选择会保存，界面立即切换，系统文件对话框下次启动生效。更新通过浏览器下载完整安装包，需退出后替换应用。

SZP 引擎和原有实测数据未变；本次没有新增性能测量，图表不包含 ZIP 输出。

### 安装与限制

下载 `SuperZip-0.4.4-build51-macOS-arm64.dmg`，将 `SuperZip.app` 拖到“应用程序”；也提供同名 ZIP。最低构建目标为 macOS 12，当前测试为 M1、macOS 26.2；旧系统及另一台全新 Mac 的首次授权尚未验证。Intel 不支持，Windows 等待实机验证后发布。

本版本地签名，未通过 Apple 公证。首次打开可在“系统设置 → 隐私与安全性 → 仍要打开”确认。

SZP 需要 SuperZip 解压；不创建 7z/RAR，不还原权限或时间戳，不支持链接、特殊文件、自解压包或同包内逐文件设密码。分卷须放在同一文件夹，请保留原文件。自有实现闭源；7-Zip 26.03 对应源码、许可及替换说明随应用提供。

[完整使用说明](https://github.com/NanLany/SuperZip#readme) · [反馈问题](https://github.com/NanLany/SuperZip/issues)

## English

This Apple Silicon macOS beta adds ZIP output and batch processing to v0.4.3 / Build48.

### Added and improved

- The main window groups compression, extraction, file selection and format settings. Check items and options before starting.
- Standard ZIP output opens in common archive apps, without table optimization, encryption or split creation. SZP retains table optimization and duplicate block reuse.
- Select up to 256 items for sequential processing, each with its own output. Choose one destination folder; numbered names avoid overwriting files.
- Processing continues after a failure. “Skip This Item” in password or filename preview prompts skips that item. “Cancel” in the main window stops active and pending items, keeping completed results.

### Fixed

Fixed quitting during a batch or an open password, preview or save dialog. Menu Quit, Command-Q and window close end unfinished tasks and remove temporary output while keeping completed results.

### Retained features

Build48's Chinese/English interface and GitHub update checks remain. A Chinese first system language uses Simplified Chinese; others use English. Manual choices are saved and switch the UI immediately; native file dialogs change next launch. Updates download a full installer in your browser; quit before replacing the app.

The SZP engine and earlier measurements are unchanged. No new benchmarks were run; charts exclude ZIP output.

### Installation and limits

Open `SuperZip-0.4.4-build51-macOS-arm64.dmg` and drag `SuperZip.app` to Applications; a ZIP is also available. Minimum target: macOS 12. Tested on M1/macOS 26.2; older systems and first launch on another Mac are unverified. Intel is unsupported; Windows awaits hardware testing.

Locally signed, not notarized by Apple. For first launch, use **System Settings → Privacy & Security → Open Anyway**.

SZP requires SuperZip. No 7z/RAR creation, permission or timestamp restoration, links, special files, self-extracting archives or per-file passwords. Keep split parts together and retain originals. SuperZip's own code is closed source; corresponding 7-Zip 26.03 source, licenses and replacement instructions are bundled.

[Full English guide](https://github.com/NanLany/SuperZip/blob/main/README.en.md) · [Report issues](https://github.com/NanLany/SuperZip/issues)

## 历史版本 / Previous releases

以下保留原发布说明，仅适用于对应旧版本。 / Original release notes below apply to their respective older version.

<p><a href="#简体中文">简体中文</a> · <a href="#english">English</a></p>

# SuperZip v0.4.3 · Build48

## 简体中文

这是 SuperZip v0.4.3 / Build48 的 macOS 测试版，适用于 Apple Silicon。请保留原文件。

### 界面语言

Build48 新增简体中文和英文界面，覆盖菜单、操作状态、提示与更新检查。默认跟随系统首选语言：中文（含繁体中文）显示简体中文，其他语言显示英文。

在“SuperZip → 语言”中选择“跟随系统”“简体中文”或“English”。手动选择优先于系统语言并在重启后保留；界面和菜单立即切换。压缩引擎未变，数据预览仍使用此前的实测结果。

系统文件对话框在下次打开应用时采用所选语言。

### 更新检查

应用菜单提供“检查更新…”和“自动检查更新”。自动检查每天最多一次，可关闭；处理文件时延后提示。有新版时显示版本说明并打开 GitHub 上的完整安装包。下载后退出应用，将新应用拖到“应用程序”并替换。离线或查询失败时，文件处理不受影响。

### 功能

- 压缩文件或文件夹为 `.szp`，支持 Finder 右键服务入口，每次处理一个项目。
- 默认按文件内容自动优化适用表格，其他文件使用普通压缩；可关闭“自动优化表格”。自动识别部分相似文件并复用重复内容块，实际收益取决于文件内容。
- 解压 `.szp`、ZIP、7z、RAR/RAR5，以及已验证的常见密码包和分卷布局。
- 旧 ZIP 中文文件名可选择 GBK 或 CP437 编码，并在解压前预览。传统 `.z01 + .zip` 分卷目前仅支持自动编码。
- 使用新名称或新目录保存结果，不覆盖已有目标；正常取消、缺卷或校验失败时不发布半成品。

### 安装与首次打开

仅提供 **Apple Silicon（M 系列）** 版本。构建最低系统目标为 **macOS 12**；当前实测环境为 **Apple M1、8 GB、macOS 26.2**，较旧系统尚未逐版本验收。Intel Mac 暂不支持。Windows 测试版预计约一周后上线，发布前会完成 Windows 实机验证；本次发行仅提供 macOS 版本。

打开 `SuperZip-0.4.3-build48-macOS-arm64.dmg`，将 `SuperZip.app` 拖到窗口中的“应用程序”。也可下载并解开同名 ZIP，将完整的应用移到“应用程序”。不要只复制应用内部的文件。

本测试版使用本地签名，**尚未通过 Apple 公证**。确认下载来自本项目后，若首次打开提示 Apple 无法验证：

1. 点“完成”。
2. 打开“系统设置 → 隐私与安全性 → 安全性”，找到 SuperZip 的“仍要打开”。
3. 按系统提示确认，再打开应用。

无需关闭全局安全保护。仅允许访问需要处理的位置；权限被拒绝时，可重新选择位置，或检查“隐私与安全性 → 文件与文件夹”。应用不要求完全磁盘访问权限。

当前验收来自同一台 M1 Mac；尚未完成经网页实际下载后，在另一台全新 Mac 上首次打开与授权的验证。

### 使用限制

`.szp` **需要 SuperZip 解压**，其他压缩工具暂不能打开；分享时请告知接收方。兼容约定见下载包中的 `SZP-COMPATIBILITY.txt`。

暂不还原权限、时间戳等文件元数据；不支持链接、特殊文件、自解压包或同包内不同文件分别设密码。所有分卷须放在同一文件夹。请保留原文件，不将测试版生成的压缩包作为唯一备份。

### 第三方组件

SuperZip 自有核心、压缩策略与界面保持闭源。7-Zip 26.03 的完整对应源码、许可和动态库重建及替换说明随应用提供，可通过“应用菜单 → 第三方许可”查看。第三方组件保留各自许可赋予的权利。

## English

This is the macOS beta of SuperZip v0.4.3 / Build48 for Apple Silicon. Keep your original files.

The Windows beta is expected in about a week, after testing on Windows hardware. This release only includes the macOS build.

### Interface language

Build48 adds Simplified Chinese and English across the interface, menus, operation status, dialogs, and update checks. It follows your system's first preferred language by default: Chinese, including Traditional Chinese, uses Simplified Chinese; all other languages use English.

Choose **SuperZip → Language**, then **Follow System**, **简体中文**, or **English**. Manual selections take precedence over the system language, persist across launches, and update the interface and menus immediately. The compression engine is unchanged; the data preview retains the earlier measurements.

System file dialogs use the selected language the next time you open the app.

### Update checks

The app menu includes manual and automatic update checks. Automatic checks run at most once a day and can be disabled. Prompts wait until file processing is idle. Available updates show release notes and link to a full installer hosted on GitHub. Quit the app, then drag the new copy to Applications and replace the previous one. Offline or failed checks do not affect file processing.

### Features

- Create `.szp` archives from a file or folder, or use the Finder service. One item is processed at a time.
- Automatic table optimization is on by default and can be turned off. Other files use regular compression. Similar files may share duplicate content blocks; savings depend on file content.
- Extract `.szp`, ZIP, 7z, RAR/RAR5, and tested password-protected and split archive layouts.
- For legacy ZIP filenames, choose GBK or CP437 and preview names before extraction. Traditional `.z01 + .zip` archives currently use automatic encoding only.
- Save to a new name or directory without overwriting existing destinations. When an operation is cancelled normally, a volume is missing, or validation fails, SuperZip does not publish a partial result.

### Installation and first launch

This build is for **Apple Silicon (M-series)** Macs. The deployment target is **macOS 12**. Testing so far uses an **Apple M1 with 8 GB of RAM on macOS 26.2**; older macOS versions have not been individually verified. Intel Macs are not supported.

Open `SuperZip-0.4.3-build48-macOS-arm64.dmg` and drag `SuperZip.app` to Applications in the window. You can also extract the ZIP with the same name and move the complete app to Applications. Do not copy only the files inside the app bundle.

This beta is locally signed and **has not been notarized by Apple**. After confirming that the download came from this project, if macOS says Apple cannot verify it:

1. Dismiss the dialog with “Done”.
2. Go to **System Settings → Privacy & Security → Security** and find SuperZip's **Open Anyway** button.
3. Follow the prompts and launch the app again.

Do not disable global security protections. Allow access to the folders you need to process. If access is denied, select the location again or check **Privacy & Security → Files & Folders**. The app does not require Full Disk Access.

The current checks were performed on the same M1 Mac. Download and first-launch authorization on another, previously unused Mac have not yet been verified.

### Limitations

**`.szp` archives require SuperZip to extract.** Let recipients know when sharing. See `SZP-COMPATIBILITY.txt` in the download for the format compatibility notes.

Permissions, timestamps, and other metadata are not restored. Links, special files, self-extracting archives, and separate passwords for files within one archive are not supported. Keep all parts of a split archive together. Keep original files; do not use this beta's archives as your only backup.

### Third-party components

SuperZip's own core, compression strategies, and interface are closed source. The complete corresponding 7-Zip 26.03 source, licenses, rebuild instructions, and library replacement instructions are bundled with the app under **App menu → Third-party licenses**. Third-party components retain the rights granted by their respective licenses.

<!-- superzip-update: {"schema":1,"minimum_macos":"12.0"} -->
