# XiaomiDuo

**让小米 18 Fold 尽可能接近 iPhone Duo**

改造小米 18 Fold 的**系统外壳**——合上时外屏呈「左 9:16 内容区 ＋ 右栏」，开合过程中两块屏同时点亮，右侧栏提供操作区与状态信息。

**非官方项目** · 不写系统分区 · 运行期 hook ＋ 叠加层 · 只用软重启

[![License](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Android%2017%20%C2%B7%20HyperOS%204-green.svg)](#开发环境)
[![Framework](https://img.shields.io/badge/framework-KernelSU%20%2B%20LSPosed-orange.svg)](#开发环境)

[中文](#中文) · [English](#english)

---

## 中文

### 项目简介

本项目致力于**让小米 18 Fold 实现尽可能接近 iPhone Duo 的效果**。

### 改造范围

| 代号 | 内容 | 状态 |
|---|---|---|
| **S1** 合上态布局 | 外屏划分为 左 9:16 内容区（963 × 1712）＋ 右栏（205 × 1712） | 部分验证 |
| **S2** 开合动画 | 开合过程中两块屏同时点亮，右栏内容随之变化 | 未开始 |
| **S3** 右侧栏 | 右侧操作栏 ＋ 状态栏，取代被掏空的系统状态栏 | 部分验证 |

### 现状

⚠️ 项目处于**早期开发阶段**，三块内容中仅 S1 / S3 有部分真机验证，S2 尚未开始。

开发过程按分层知识库记录在 `知识库/`（按条目 ID 检索，`INDEX.md` 为总目）。

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

> ⚠️ **只支持软重启。** 本项目依赖的 root 是 **LKM 临时 root，硬重启即失效**（`adb reboot` / 关机 / Recovery / OTA 均会使其丢失）。恢复需先重新提权，**再软重启一次**模块才会生效。

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

**XiaomiDuo aims to make the Xiaomi 18 Fold behave as close to an iPhone Duo as possible.**

It reshapes the device's **system shell**: in the folded state the cover screen is split into a left 9:16 content area (963 × 1712) plus a right column (205 × 1712); while unfolding, both panels stay lit and the right column follows.

### Scope

| ID | Item | Status |
|---|---|---|
| **S1** Folded layout | Cover screen split into left 9:16 area (963 × 1712) and right column (205 × 1712) | Partially verified |
| **S2** Fold animation | Both panels stay lit across the fold; right column follows | Not started |
| **S3** Right column | Right-side control bar + status column, replacing the emptied system status bar | Partially verified |

### Status

⚠️ **Early development.** Of the three items above, only S1 / S3 have partial on-device verification. S2 has not been started.

Design notes live in `知识库/` as a layered knowledge base (entry-ID indexed; `INDEX.md` is the table of contents).

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

> ⚠️ **Soft reboot only.** This project relies on an **LKM temporary root, which is lost on a hard reboot** (`adb reboot`, power off, Recovery, OTA all destroy it). After re-escalating, you must **soft reboot once more** for modules to load.

### Donate

<img src="docs/donate_wechat_qr.png" width="220" alt="WeChat tip QR code">

A plain tip — no prompts, no popups. Donating grants no extra features, priority support, or license.

### Disclaimer

- Unofficial project, **not affiliated with Xiaomi or Apple Inc.**
- "iPhone" / "iPhone Duo" are trademarks of Apple Inc.; "小米" / "Xiaomi" / "HyperOS" are trademarks of Xiaomi. Used here for reference only.
- For learning and personal use. Modifying system runtime behaviour carries risk — assess it yourself and **back up your data**.

### License

[GNU AGPL-3.0](LICENSE). If you modify this project and offer it over a network, you must publish your source.
