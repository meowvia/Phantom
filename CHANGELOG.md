# Phantom 版本发布与更新日志 (Changelog)

All notable changes to Phantom will be documented in this file.
This project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.1.0-Beta] - 2026-09-26

### 公测首发版 (Public Beta Release)
专为 macOS 打造的原生轻量隐私防窥与原路径文件隐藏工具。

#### 核心能力与安全架构
* **原路径文件隐藏与权限锁定 (In-Place File Concealment & Permission Locking)**：
  - 基于 macOS Darwin 内核系统调用（`lchflags`、`chmod`、`setxattr`），受保护项目在访达（Finder）与聚光灯搜索（Spotlight）中隐藏，配合 POSIX 000 权限与不可变标志（`UF_IMMUTABLE`）防止日常意外读写与篡改；
  - 时间复杂度为 O(1)，直接在原存储路径修改元数据与权限，对大体积文件夹无数据复制与重编码等待，避免掉电或写入中断造成的数据损坏风险。
* **生物识别与钥匙串隔离 (Touch ID & Keychain)**：
  - 支持 Touch ID 快速验证，主密码凭据受系统钥匙串（macOS Keychain - ThisDeviceOnly）本地安全隔离；
  - 纯本地离线运行，无网络权限，无遥测上报，无云端存储。

#### 视觉交互与防窥策略
* **原生 Liquid Glass 材质美学与视觉降噪**：
  - 深度适配 macOS 深浅主题，采用高透光多层模糊与亚像素边缘高光；
  - 顶部工具栏贯彻 macOS 原生留白设计，取消多余悬挂图标，右侧保持三键规范；
  - 偏好设置净空副标题小字，移除冗余商业版字样，底部仅保留纯净版本号。
* **「安全防窥策略」双档位模式 (Dual-Mode Anti-Peep & Focus)**：
  - **极致防窥模式（默认）**：失焦即关即锁。光标离开大窗口区域时，大窗口主动平滑关闭，会话凭证即刻从内存抹除，降低开放环境下的窥视风险；
  - **沉浸整理模式**：为多任务与跨应用拖拽设计。大窗口失去焦点时在后台保持打开；关闭窗口时自动重新锁定管理会话；
  - **原生偏好设置交互**：内置 Liquid Glass 原生双档位分段切换器与 Apple HIG 标准规范指引。
* **智能生物认证与焦点防误杀**：
  - 隔离 Touch ID 系统认证弹窗与文件选择器，防止合法交互被误判为失焦；
  - 修复冷启动下 Touch ID 验证通过后因系统焦点交还 Finder 导致大窗口沉底的问题，确保认证后窗口稳驻前台。
* **高可用容灾与「一键恢复」体系 (Rescue Scan & Redundancy)**：
  - **显式微胶囊入口**：管理中心顶部工具栏采用带文字与旋转微交互的「一键恢复」胶囊按钮；
  - **5 层深度穿透扫描**：一键恢复扫描深度覆盖至 5 层，有效检索用户工作深层子目录；
  - **全链路找回与重置**：首次启动页与待解锁页面全面提供恢复密钥重置/导入入口，误卸载重装或遗忘密码时凭恢复密钥重置密码并恢复受保护项目访问。

#### 渲染性能与 ProMotion 120Hz 优化
* **列表 Equatable 差量重绘机制**：
  - 管理列表单元行实现严格的 `Equatable` 静态比对，条目勾选与悬停时跳过无关行的计算评估，有效降低视图重绘开销；
* **CoreAnimation 异步硬件加速**：
  - 视图开启 `drawsAsynchronously = true` 与 `allowsConcurrentViewDrawing = true`，毛玻璃材质光栅化移交专用渲染队列；
* **数据供给 O(1) 预计算缓存**：
  - 衍生列表响应式预计算缓存，在高刷新率屏幕上保持流畅响应。

#### 轻量工程与包体
* **体积控制**：全模块优化 + 符号剥离 + Apple 原生 LZMA 压缩，DMG 安装包体积保持轻量纯净。
