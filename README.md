# FXXK ACE - 一个功能强大的ACE反作弊进程控制和优化工具

[![.NET](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/download)
[![Windows](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)](https://www.microsoft.com/windows)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Download](https://img.icons8.com/external-kmg-design-flat-kmg-design/32/external-download-ui-essential-kmg-design-flat-kmg-design.png)](https://pan.quark.cn/s/b4a21078168e)

一个功能强大的ACE反作弊进程控制和优化工具，提供7项核心控制策略和智能暂停功能，限制ACE进程的资源消耗
![FXXK-ACE](https://github.com/user-attachments/assets/925181b7-ffeb-4b1b-bdfd-7b03f8caf0f2)

## ✨ 核心功能

### 🎯 7项进程控制策略
- **CPU亲和性控制** - 精确分配CPU核心，支持大小核架构
- **内存优先级管理** - 优化内存分配和回收策略
- **IO优先级控制** - 管理磁盘读写优先级
- **电源模式管理** - Win11效率模式/Win10电源节流模式
- **进程优先级控制** - 动态调整进程执行优先级
- **动态优先级提升** - 智能优先级提升控制
- **智能暂停/恢复** - 基于资源使用率的自动暂停

### 🧠 智能暂停系统
- **实时监控** - 持续监控CPU和磁盘使用率
- **自动暂停** - 当资源使用超过阈值时自动暂停进程
- **智能恢复** - 资源使用降低时自动恢复进程
- **可配置阈值** - 支持自定义CPU和磁盘使用率阈值
- **最小暂停时间** - 防止频繁暂停/恢复操作

### 🔐 权限管理
- **管理员权限检测** - 自动检测当前权限级别
- **SYSTEM权限提升** - 支持提升到最高系统权限
- **安全令牌管理** - 安全的权限令牌存储和管理

### 📊 详细状态报告
- **实时状态显示** - 7项控制策略的实时状态
- **资源使用监控** - CPU和磁盘使用率实时显示
- **智能暂停状态** - 暂停/恢复状态和时长统计
- **系统信息展示** - 权限级别和系统版本信息

## 🖥️ 系统要求

- **操作系统**: Windows 10 1903+ / Windows 11
- **框架**: .NET 8.0 Runtime
- **权限**: 管理员权限（推荐SYSTEM权限）
- **架构**: x64 / x86

## 🚀 快速开始

### 安装
1. 下载最新版本的可执行文件
   - [FXXK_ACE_Ver1.1.3.rar](https://pan.quark.cn/s/b4a21078168e)
   - FXXK_ACE_x64.exe：64位版本（推荐）
   - FXXK_ACE_x86.exe：32位版本
3. 以管理员身份运行程序
4. 首次运行会自动生成配置文件

### 基本使用
1. **添加目标进程** - 默认内置进程（`SGuard64.exe`、`SGuardSvc64.exe`）
2. **配置控制策略** - 默认使用7项控制策略
3. **启用智能暂停** - 根据需要开启智能暂停功能
4. **查看详细状态** - 点击"详细状态"按钮查看实时信息

## ⚙️ 配置说明

### 智能暂停配置 (`config.json`)
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

## 🏗️ 技术架构

### 核心技术栈
- **.NET 8.0** - 现代化的.NET框架
- **Windows API** - 深度集成Windows系统API
- **WinForms** - 原生Windows界面框架
- **异步编程** - 非阻塞的UI和后台处理

### 关键组件
- `ProcessController` - 进程控制核心引擎
- `SmartSuspendManager` - 智能暂停管理器
- `WinAPI` - Windows API封装层
- `DetailedStatusDialog` - 详细状态报告界面

### 架构特点
- **模块化设计** - 清晰的功能模块划分
- **配置驱动** - 灵活的配置文件管理
- **权限安全** - 安全的权限提升和管理
- **实时监控** - 高效的资源监控机制

## 🎨 界面预览

### 主控制界面
- 进程列表管理
- 7项控制策略开关
- 实时状态显示
- 智能暂停控制

### 详细状态报告
- 进程控制状态详情
- 资源使用率监控
- 智能暂停配置信息
- 系统环境信息

## 💡 使用场景

### 游戏优化
- 限制ACE反作弊进程后台进程资源占用
- 为ACE反作弊进程分配专用CPU核心
- 智能暂停ACE反作弊进程（超出预设阀值）

### 开发环境
- 控制编译进程资源使用
- 管理虚拟机和容器资源
- 优化开发工具性能

### 系统维护
- 限制系统服务资源占用
- 管理安全软件行为
- 优化系统整体性能

## 🛡️ 安全特性

- **权限最小化原则** - 仅在需要时提升权限
- **安全的API调用** - 使用官方Windows API
- **配置文件验证** - 防止恶意配置注入
- **进程保护** - 防止意外终止关键进程

## 📝 更新日志

### v1.1.3 (最新)
- ✅ 修复已知和未知的BUG

### v1.1.2
- ✨ 新增智能暂停功能
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

### Q: 智能暂停会影响系统稳定性吗？
A: 不会。智能暂停使用Windows官方API，且有最小暂停时间保护，确保系统稳定。

### Q: 支持哪些Windows版本？
A: 支持Windows 10 1903+和Windows 11。部分功能（如效率模式）需要特定版本支持。

### Q: 如何备份和恢复配置？
A: 配置文件位于程序目录，可以直接复制`config.json`等配置文件进行备份。

### Q: 程序会收集用户数据吗？
A: 不会。程序完全本地运行，不会收集或上传任何用户数据。

## 🤝 贡献指南

欢迎提交Issue和Pull Request！

1. Fork 本仓库
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

### 贡献类型
- 🐛 Bug修复
- ✨ 新功能开发
- 📝 文档改进
- 🎨 UI/UX优化
- ⚡ 性能优化

## ⚠️ 免责声明

本工具仅供学习和研究使用，使用者需要：
- 了解进程控制的风险和影响
- 在测试环境中验证功能
- 承担使用本工具的所有风险

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

感谢所有为这个项目做出贡献的开发者和用户！

---

**⭐ 如果这个项目对你有帮助，请在软件内点击** **请我喝杯咖啡** **!**
