# FXXK ACE - 一个功能强大的ACE反作弊进程控制和优化工具

[![.NET](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/download)
[![Windows](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)](https://www.microsoft.com/windows)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Download](https://img.icons8.com/external-kmg-design-flat-kmg-design/32/external-download-ui-essential-kmg-design-flat-kmg-design.png)](https://pan.quark.cn/s/b4a21078168e)

一个功能强大的ACE反作弊进程控制和优化工具，提供7项核心控制策略和自动暂停功能，限制ACE进程的资源消耗
![FXXK-ACE](https://github.com/user-attachments/assets/925181b7-ffeb-4b1b-bdfd-7b03f8caf0f2)

## ✨ 核心功能

### 🎯 7项进程控制策略
- 精确分配CPU核心，支持大小核架构
- 优化内存分配和回收策略
- 管理磁盘读写优先级
- Win11效率模式/Win10电源节流模式
- 动态调整进程执行优先级和基于资源使用率的自动暂停

### 🧠 自动暂停系统
- 持续监控CPU和磁盘使用率，当资源使用超过阈值时自动暂停进程，资源空闲时自动恢复进程
- 支持自定义CPU和磁盘使用率阈值，同时支持最小暂停时间，防止频繁暂停/恢复操作

## 🖥️ 系统要求

- **操作系统**: Windows 10 1903+ / Windows 11
- **架构**: x64 / x86

## 🚀 快速开始

### 安装
1. 下载最新版本的可执行文件
   - [FXXK_ACE_Ver1.1.3.rar](https://pan.quark.cn/s/b4a21078168e)（跳转至夸克网盘）
   - FXXK_ACE_x64.exe：64位版本（推荐）
   - FXXK_ACE_x86.exe：32位版本
3. 以管理员身份运行程序
4. 首次运行会自动生成配置文件

### 基本使用
1. **添加目标进程** - 默认已经内置进程（`SGuard64.exe`、`SGuardSvc64.exe`）
2. **配置控制策略** - 默认使用7项控制策略
3. **启用自动暂停** - 根据需要开启自动暂停功能
4. **查看详细状态** - 点击"详细状态"按钮查看实时信息

> [!WARNING]
> 程序可能会自动提权至SYSTEM

## ⚙️ 配置说明

### 自动暂停配置 (`config.json`)
```json
{
  "enabled": true,
  "monitorCpu": true,
  "monitorDisk": true,
  "cpuThreshold": 1,
  "diskThreshold": 1,
  "monitorInterval": 50000,
  "suspendTriggerCount": 3,
  "resumeTriggerCount": 2,
  "minSuspendDuration": 5000
}
```

### 配置参数说明
- `cpuThreshold`: CPU使用率阈值（%）
- `diskThreshold`: 磁盘使用率阈值（MB/s）
- `monitorInterval`: 监控间隔（毫秒）
- `suspendTriggerCount`: 触发暂停的连续次数
- `resumeTriggerCount`: 触发恢复的连续次数
- `minSuspendDuration`: 最小暂停持续时间（毫秒）

## 🎨 界面预览

### 主控制界面
- 进程列表管理
- 7项控制策略开关
- 实时状态显示
- 自动暂停控制

### 详细状态报告
- 进程控制状态详情
- 资源使用率监控
- 自动暂停配置信息
- 系统环境信息


## 🛡️ 安全特性

- 仅在需要时提权，避免非必要的权限滥用
- 使用Windows自带的API
- 有一层配置文件验证，阻断恶意配置
- 对关键进程有防护，防止修改不该碰的东西

## 📝 更新日志

### v1.1.3 (最新)
- ✅ 修复已知和未知的BUG

### v1.1.2
- ✨ 新增自动暂停功能
- 🎨 优化详细状态报告界面
- 🔧 修复CPU和磁盘监控准确性
- 📊 增强实时状态显示
- ⚡ 提升整体性能和稳定性
- ✅ 解决Windows 11 启用效率模式失败问题（虚空修复）

### v1.0.0
- 🎉 初始版本发布
- 🎯 实现6项基础控制策略
- 🔐 支持权限管理
- 📱 现代化UI界面

## ❓ 常见问题

### Q: 为什么需要管理员权限？
A: 进程控制需要访问系统级API，管理员权限是必需的。SYSTEM权限可以控制更多系统进程。

### Q: 自动暂停会影响系统稳定性吗？
A: 不会。自动暂停使用Windows官方API，且有最小暂停时间保护，确保系统稳定。

### Q: 支持哪些Windows版本？
A: 支持Windows 10 1903+和Windows 11。部分功能（如效率模式）需要特定版本支持。

### Q: 如何备份和恢复配置？
A: 配置文件位于程序目录，可以直接复制`config.json`等配置文件进行备份。

### Q: 程序会收集用户数据吗？
A: 不会。程序完全本地运行，不会收集或上传任何用户数据。


> [!CAUTION]
> **免责声明**
> 
> **本工具仅供学习和研究使用。使用者在使用本工具前应当了解进程控制的风险和影响，在使用前应当在测试环境中验证功能是否稳定可用，并承担使用本工具的所有风险。**


## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

感谢所有为这个项目做出贡献的开发者和用户！

---

**⭐ 如果这个项目对你有帮助，请在软件内点击** **请我喝杯咖啡** **!**
