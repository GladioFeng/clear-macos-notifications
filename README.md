<p align="center">
  <img src="icon.png" alt="Clear macOS Notifications icon" width="128">
</p>

# Clear macOS Notifications

Alfred 5 workflow。在 Alfred 中输入 `clear`，清除 macOS 通知中心内当前可访问的通知。

## 安装

1. 下载 [`Clear macOS Notifications.alfredworkflow`](./Clear%20macOS%20Notifications.alfredworkflow?raw=1)。
2. 双击文件，在 Alfred 中确认导入。
3. 调出 Alfred，输入 `clear` 并回车。

## 权限

首次运行前，在 **系统设置 → 隐私与安全性 → 辅助功能** 中允许 **Alfred 5**。macOS 询问自动化权限时，允许 Alfred 控制 **System Events**。该 workflow 不需要 Full Disk Access。

## 兼容性

- 包内只有 AppleScript 和 PNG，不含 Intel 或 Apple Silicon 专属二进制。
- 已在 macOS 14 Intel 上实测。代码针对 macOS 15 的通知中心层级变化做了兼容处理，但尚未在 macOS 15 Apple Silicon 实机验证。

## 工作方式

Workflow 打开通知中心，递归查找 `AXNotificationCenter` 元素，执行通知卡片的关闭 action，然后收回通知中心。它不修改通知数据库或通知设置。
