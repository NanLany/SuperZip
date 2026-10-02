<p><a href="#简体中文">简体中文</a> · <a href="#english">English</a></p>

# SuperZip v0.4.3 · Build47

## 简体中文

这是 SuperZip v0.4.3 / Build47 的 macOS 测试版，适用于 Apple Silicon。请保留原文件。

### 更新检查

应用菜单新增“检查更新…”和“自动检查更新”。自动检查每天最多一次，可关闭；处理文件时延后提示。有新版时显示版本说明并打开 GitHub 上的完整安装包。下载后退出应用，将新应用拖到“应用程序”并替换。离线或查询失败时，文件处理不受影响。

### 功能

- 压缩文件或文件夹为 `.szp`，支持 Finder 右键服务入口，每次处理一个项目。
- 默认按文件内容自动优化适用表格，其他文件使用普通压缩；可关闭“自动优化表格”。自动识别部分相似文件并复用重复内容块，实际收益取决于文件内容。
- 解压 `.szp`、ZIP、7z、RAR/RAR5，以及已验证的常见密码包和分卷布局。
- 旧 ZIP 中文文件名可选择 GBK 或 CP437 编码，并在解压前预览。传统 `.z01 + .zip` 分卷目前仅支持自动编码。
- 使用新名称或新目录保存结果，不覆盖已有目标；正常取消、缺卷或校验失败时不发布半成品。

### 安装与首次打开

仅提供 **Apple Silicon（M 系列）** 版本。构建最低系统目标为 **macOS 12**；当前实测环境为 **Apple M1、8 GB、macOS 26.2**，较旧系统尚未逐版本验收。Intel Mac 暂不支持。Windows 测试版预计约一周后上线，发布前会完成 Windows 实机验证；本次发行仅提供 macOS 版本。

打开 `SuperZip-0.4.3-build47-macOS-arm64.dmg`，将 `SuperZip.app` 拖到窗口中的“应用程序”。也可下载并解开同名 ZIP，将完整的应用移到“应用程序”。不要只复制应用内部的文件。

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

This is the macOS beta of SuperZip v0.4.3 / Build47 for Apple Silicon. Keep your original files.

The Windows beta is expected in about a week, after testing on Windows hardware. This release only includes the macOS build.

### Update checks

The app menu now includes manual and automatic update checks. Automatic checks run at most once a day and can be disabled. Prompts wait until file processing is idle. Available updates show release notes and link to a full installer hosted on GitHub. Quit the app, then drag the new copy to Applications and replace the previous one. Offline or failed checks do not affect file processing.

### Features

- Create `.szp` archives from a file or folder, or use the Finder service. One item is processed at a time.
- Automatic table optimization is on by default and can be turned off. Other files use regular compression. Similar files may share duplicate content blocks; savings depend on file content.
- Extract `.szp`, ZIP, 7z, RAR/RAR5, and tested password-protected and split archive layouts.
- For legacy ZIP filenames, choose GBK or CP437 and preview names before extraction. Traditional `.z01 + .zip` archives currently use automatic encoding only.
- Save to a new name or directory without overwriting existing destinations. When an operation is cancelled normally, a volume is missing, or validation fails, SuperZip does not publish a partial result.

### Installation and first launch

This build is for **Apple Silicon (M-series)** Macs. The deployment target is **macOS 12**. Testing so far uses an **Apple M1 with 8 GB of RAM on macOS 26.2**; older macOS versions have not been individually verified. Intel Macs are not supported.

Open `SuperZip-0.4.3-build47-macOS-arm64.dmg` and drag `SuperZip.app` to Applications in the window. You can also extract the ZIP with the same name and move the complete app to Applications. Do not copy only the files inside the app bundle.

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
