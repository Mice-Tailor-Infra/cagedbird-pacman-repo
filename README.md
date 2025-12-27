# CagedBird Private Pacman Repository

[![Build Status](https://img.shields.io/badge/status-active-brightgreen)](#)
[![Arch](https://img.shields.io/badge/arch-x86__64%20%7C%20aarch64-blue)](#)

这是一个私有的 Arch Linux 软件仓库，托管由 CI/CD 自动构建的 **sing-box-ref1nd** 系列软件包。

## 📦 包含软件包

*   `sing-box-ref1nd`: 稳定版分支，基于 `reF1nd-main`。针对 `x86_64_v3/v4` 及 `aarch64` 优化。
*   `sing-box-ref1nd-dev`: 开发版分支，基于 `reF1nd-dev`。

## 🚀 使用方法

### 1. 配置软件源
编辑你的 `/etc/pacman.conf`，在文件末尾添加以下内容：

```ini
[cagedbird-repo]
SigLevel = Optional TrustAll
Server = https://cagedbird043.github.io/cagedbird-pacman-repo/$arch
```
> **注意**: 如果 GitHub Pages 尚未生效，可使用 Raw 链接（不推荐长期使用）：
> `Server = https://raw.githubusercontent.com/cagedbird043/cagedbird-pacman-repo/main/$arch`

### 2. 同步并安装
执行以下操作：
```bash
sudo pacman -Syy
sudo pacman -S sing-box-ref1nd
```

## 🛠️ 仓库维护逻辑

*   **自动化编译**：由 [sing-box-auto-build-ci](https://github.com/cagedbird043/sing-box-auto-build-ci) 触发。
*   **多架构支持**：
    *   `x86_64`: 优先采用 `v3` 微架构编译，提升现代 CPU 性能。
    *   `aarch64`: 针对 ARM 开发板、手机及 Apple Silicon 优化。
*   **依赖声明**：本仓库包与官方 `sing-box` 互斥并提供相同功能。

---
*Powered by GitHub Actions*
