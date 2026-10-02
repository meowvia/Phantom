<p align="center">
  <img src="docs/assets/logo.png" width="96" height="96" alt="Phantom Logo" />
</p>

<h1 align="center">Phantom</h1>

<p align="center">
  <strong>基于 macOS 原生机制的原路径文件隐藏与独立密码防护工具</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-macOS%2014.0%2B-blue?style=flat-square" alt="Platform" />
  <img src="https://img.shields.io/badge/Architecture-Apple%20Silicon-success?style=flat-square" alt="Architecture" />
  <img src="https://img.shields.io/badge/Language-Swift%206-orange?style=flat-square" alt="Language" />
  <img src="https://img.shields.io/badge/Privacy-Offline%20%7C%20No%20Telemetry-brightgreen?style=flat-square" alt="Privacy" />
  <img src="https://img.shields.io/badge/Package-Native%20DMG-purple?style=flat-square" alt="Package" />
</p>

<p align="center">
  <a href="#软件介绍">软件介绍</a> •
  <a href="#核心优势">核心优势</a> •
  <a href="#功能预览">功能预览</a> •
  <a href="#系统要求">系统要求</a> •
  <a href="#快速上手">快速上手</a> •
  <a href="README.md">English Version</a>
</p>

---

## 软件介绍

在日常办公、演示或与他人共用 Mac 时，私人相册、财务资料或敏感项目极易在访达检索、最近使用或隔空投送时不经意暴露。传统加密镜像耗时长且中断易损毁大文件，而直接借用系统锁屏密码更使隐私保护形同虚设。

**Phantom** 专为 macOS 深度打造：无需漫长的数据搬迁或格式重写，直接基于原生文件控制在原路径实现极速隐藏；建立独立于系统登录密码的专属凭据体系，以原生轻量形式守护个人数字边界。

---

## 核心优势

- **原路径快速响应**：直接在原路径实施隐藏保护，大文件无需耗时复制或转码，无额外存储开销，避免写入中断造成的数据损坏风险。
- **独立密码与生物识别**：建立专属主密码并联动 Touch ID，与 macOS 开机密码独立隔离，降低设备借出时的泄露风险。
- **主动防遗忘与状态栏警示**：集成动态视觉哨兵机制，编辑期间呈橙色提示；若在存在未锁定项目时关闭管理中心，状态栏立即转为醒目的纯红警示，提示及时重新锁定。
- **纯本地离线运行**：无网络权限、无后台遥测、无云端上传，核心凭据受系统钥匙串硬件级安全隔离。
- **原生轻量体验**：采用纯 AppKit + SwiftUI 构建，安装包体积轻量纯净，常驻菜单栏与双栏管理中心协同工作。

---

## 功能预览

### 1. 独立账户体系与生物识别验证
强制设定独立于系统密码的专属主密码，搭配 Touch ID 实现轻触即开，并具备递增式防暴力尝试保护。

| 图 1：初次密码设置 | 图 2：锁屏验证与 Touch ID |
| :---: | :---: |
| <img src="docs/screenshots/zh/1.png" width="420" alt="初次密码设置" /> | <img src="docs/screenshots/zh/2.png" width="420" alt="锁屏身份验证" /> |

---

### 2. 安全规范与使用须知
首次进入主界面必须知悉的核心条款：明确纯本地离线与原路径特性，指导合规使用（如避免将实时同步盘或下载器路径指向已锁定目录）。

<p align="center">
  <img src="docs/screenshots/zh/3.png" width="720" alt="使用须知与安全规范" />
</p>

---

### 3. 直观严谨的双栏管理中心
通透 Liquid Glass 材质，文件夹与文件双栏平分陈列，容量与状态一目了然；支持常驻即时搜索与访达直接拖拽纳管。

| 图 4：管理中心空白初始态 | 图 5：管理中心数据列表态 |
| :---: | :---: |
| <img src="docs/screenshots/zh/4.png" width="420" alt="管理中心空白态" /> | <img src="docs/screenshots/zh/5.png" width="420" alt="管理中心列表态" /> |

---

### 4. 自适应批量管理与单项操作
顶栏控制条随当前选中项自动切换（批量解锁/锁定）；条目右侧提供独立解锁与访达直达（Reveal in Finder），解除保护具备防误触二次确认。

| 图 6：批量自适应管理条 | 图 7：单项操作与访达直达 |
| :---: | :---: |
| <img src="docs/screenshots/zh/6.png" width="420" alt="批量管理条" /> | <img src="docs/screenshots/zh/7.png" width="420" alt="单项操作" /> |

---

### 5. 常驻状态栏小窗口与主动防遗忘警示
常驻顶部菜单栏，具备双重智能视觉哨兵：日常编辑时以橙色指示灯提醒未锁定资产；**当管理中心关闭或退入后台、但仍有项目处于未锁定（暴露可见）状态时，状态栏图标会立即发出强烈的纯红色警示**，防止用户在会议或公共场合误将暴露文件遗留于桌面或访达。呼出悬浮小面板可就地查看最近项目并一键快速锁定，不打断当下工作流。

<p align="center">
  <img src="docs/assets/sentinel_states_zh.png" width="760" alt="状态栏视觉哨兵三种工作状态" />
</p>

<p align="center">
  <img src="docs/screenshots/zh/8.png" width="440" alt="菜单栏浮动小面板" />
</p>

---

### 6. 偏好设置与专属恢复密钥
支持中英双语即时切换与凭据重设；初次配置生成的专属「恢复密钥」是离线状态下重置密码并找回受保护资产的关键凭据。

<p align="center">
  <img src="docs/screenshots/zh/9.png" width="720" alt="偏好设置与安全规范" />
</p>

---

## 系统要求

- **操作系统**：macOS 14.0 (Sonoma) 或更高版本
- **架构平台**：Apple Silicon (M1 / M2 / M3 / M4 全系列芯片)
- **推荐硬件**：支持 Touch ID 的 Mac 设备或键盘

---

## 快速上手

1. 前往 Release 下载 `Phantom-v0.1.0-Beta.dmg`（英文版对应 `-en.dmg`）；
2. 打开镜像并将 **Phantom** 拖入 `Applications` 文件夹；
3. 启动应用，依引导创建专属主密码并备份恢复密钥；
4. 点击顶部状态栏图标或将文件拖入管理中心即可开启保护。

---

## 版权与声明

- **版权所有 © 2026 Phantom Team. 保留所有权利。**
- 商业闭源软件，受知识产权法保护。未经许可严禁逆向、篡改或重新分发。
