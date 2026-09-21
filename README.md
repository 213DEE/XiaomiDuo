# XiaomiDuo

**致力于让小米 18 Fold 的 UI、操作、动画接近 iPhone Duo**

非官方项目 · 仅供学习与个人使用

[![License](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Android%2017%20%C2%B7%20HyperOS%204-green.svg)](#开发环境)
[![Device](https://img.shields.io/badge/device-Xiaomi%2018%20Fold-orange.svg)](#开发环境)

[中文](#中文) · [English](#english)

---

## 中文

### 项目简介

**XiaomiDuo 致力于让小米 18 Fold 的 UI、操作、动画接近 iPhone Duo。**

> ⚠️ **早期开发阶段。** 具体实现手段与可行边界**仍在验证中** —— 本文不写死任何技术方案。
> 已实测的结论会标 **✅ 实测**，仍属推断的会标 **🔎 推断**，不去猜没验证过的事。

### 关注方向

| 方向 | 内容 | 状态 |
|---|---|---|
| **S1** 开合动画 | 展开 / 合上过程中的过渡动画 | 未开始（当前主线） |
| **S2** 合上态布局 | 合上时外屏的画面分区 | 部分验证 |
| **S3** 右侧栏 | 右侧的操作区与状态信息 | 部分验证 |

> 编号按**执行优先级**排列。设计过程按分层知识库记录在 `知识库/`（按条目 ID 检索，`INDEX.md` 为总目）。

### 开发环境

本项目在下列环境完成实机验证（数值均取自设备 `getprop` / `uname`）：

| 项 | 值 |
|---|---|
| 设备 | 小米 18 Fold —— 型号 `2608BPX34C`，产品代号 `lhasa` |
| 处理器 | 小米玄戒 **XRing O3**（`ro.board.platform` = `xring_o3_asic`） |
| 系统 | Android **17**（API 37）· 小米澎湃 OS **OS4.0.11.0.XPNCNXM** |
| 系统构建 | `CP2A.260605.016` · 安全补丁 **2026-08-01** · `arm64-v8a` |
| 内核 | `6.18.21-android17-5-g1d099fcb35e0-abogki538445360-4k`（`#1 SMP PREEMPT`，2026-07-28） |
| 屏幕 | 外屏 1168 × 1712 @ 440 dpi；内屏 1672 × 2364 |
| Root | **KernelSU** `v3.3.0-25-gdfadc083`（versionCode 32626）· LKM 临时 root |
| Zygisk | **Zygisk Next** `1.5.0 (843-5217106-release)` |
| Hook 框架 | **LSPosed** `v2.2.0 (7854)` · libxposed API **102** |

其他机型 / 系统版本未验证。

### 捐赠

<img src="docs/donate_wechat_qr.png" width="220" alt="微信打赏收款码">

纯粹的打赏——不问、不跳、不弹窗。打赏不会带来额外功能、优先支持或任何授权。

### 免责声明

- 本项目**非官方**，与小米公司、Apple Inc. 均无关联。
- 「iPhone」「iPhone Duo」等商标归 Apple Inc. 所有；「小米」「Xiaomi」「HyperOS」「澎湃 OS」等商标归小米公司所有。此处仅作指称使用。
- 仅供学习与个人使用。修改系统运行时行为存在风险，使用前请自行评估并**备份数据**。

### License

[GNU AGPL-3.0](LICENSE)。改了这个项目并通过网络提供服务，你需要公开你的源码。

---

## English

### About

**XiaomiDuo aims to bring the Xiaomi 18 Fold's UI, interactions and animations close to the iPhone Duo.**

> ⚠️ **Early development.** The implementation approach and its limits are **still being verified** —
> this document deliberately commits to no technical specifics. Verified findings are marked **✅ tested**,
> inferences are marked **🔎 inferred**.

### Focus areas

| Area | Description | Status |
|---|---|---|
| **S1** Fold animation | Transition animation while unfolding / folding | Not started (current focus) |
| **S2** Folded layout | On-screen partitioning of the cover display when folded | Partially verified |
| **S3** Right column | Control area and status info on the right side | Partially verified |

> IDs are ordered by execution priority. Design notes live in `知识库/` as a layered knowledge base
> (entry-ID indexed; `INDEX.md` is the table of contents).

### Test environment

All values below were read from the device via `getprop` / `uname`.

| Item | Value |
|---|---|
| Device | Xiaomi 18 Fold — model `2608BPX34C`, codename `lhasa` |
| SoC | Xiaomi XRing **O3** (`ro.board.platform` = `xring_o3_asic`) |
| OS | Android **17** (API 37) · Xiaomi HyperOS **OS4.0.11.0.XPNCNXM** |
| Build | `CP2A.260605.016` · security patch **2026-08-01** · `arm64-v8a` |
| Kernel | `6.18.21-android17-5-g1d099fcb35e0-abogki538445360-4k` (`#1 SMP PREEMPT`, 2026-07-28) |
| Displays | Cover 1168 × 1712 @ 440 dpi; inner 1672 × 2364 |
| Root | **KernelSU** `v3.3.0-25-gdfadc083` (versionCode 32626) · LKM temporary root |
| Zygisk | **Zygisk Next** `1.5.0 (843-5217106-release)` |
| Hook framework | **LSPosed** `v2.2.0 (7854)` · libxposed API **102** |

No other device or OS version has been verified.

### Donate

<img src="docs/donate_wechat_qr.png" width="220" alt="WeChat tip QR code">

A plain tip — no prompts, no popups. Donating grants no extra features, priority support, or license.

### Disclaimer

- Unofficial project, **not affiliated with Xiaomi or Apple Inc.**
- "iPhone" / "iPhone Duo" are trademarks of Apple Inc.; "小米" / "Xiaomi" / "HyperOS" are trademarks of Xiaomi. Used here for reference only.
- For learning and personal use. Modifying system runtime behaviour carries risk — assess it yourself and **back up your data**.

### License

[GNU AGPL-3.0](LICENSE). If you modify this project and offer it over a network, you must publish your source.
