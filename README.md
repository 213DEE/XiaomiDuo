# XiaomiDuo

**致力于让小米 18 Fold 的 UI、操作、动画接近 iPhone Duo**

非官方项目 · 仅供学习与个人使用

[![License](https://img.shields.io/badge/license-PolyForm_Noncommercial_1.0.0-orange.svg)](LICENSE)
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

**关于收费**：Alpha 阶段将始终保持免费；不排除将来推出 Beta 或正式版后，部分功能收费的可能。

纯粹的打赏——不问、不跳、不弹窗。打赏不会带来额外功能、优先支持或任何授权。

### 免责声明

- 本项目**非官方**，与小米公司、Apple Inc. 均无关联。
- 「iPhone」「iPhone Duo」等商标归 Apple Inc. 所有；「小米」「Xiaomi」「HyperOS」「澎湃 OS」等商标归小米公司所有。此处仅作指称使用。
- 仅供学习与个人使用。修改系统运行时行为存在风险，使用前请自行评估并**备份数据**。

### License

[PolyForm Noncommercial License 1.0.0](LICENSE) —— **仅限非商业用途**。

- ✅ **免费使用**：个人学习、研究、实验、爱好项目，以及非营利组织／学校／公共研究机构。
- ⛔ **需另行授权**：任何商业用途 —— 包括销售、作为付费产品或服务的一部分、SaaS／托管服务、
  企业内部生产环境使用、基于本项目的收费咨询或支持 —— **均须事先取得作者的书面商业许可**。
- 📧 需要商业授权，请通过 [Issues](https://github.com/213DEE/XiaomiDuo/issues) 联系作者。

> Required Notice: Copyright © 2026 213DEE (https://github.com/213DEE/XiaomiDuo)

⚠️ 本项目是「**源码公开**（source-available）」，**不是** OSI 认可的开源协议 —— 因为它限制商业使用。

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

**On pricing**: free throughout the Alpha stage. Charging for some features after a future Beta or stable release is **not ruled out**.

A plain tip — no prompts, no popups. Donating grants no extra features, priority support, or license.

### Disclaimer

- Unofficial project, **not affiliated with Xiaomi or Apple Inc.**
- "iPhone" / "iPhone Duo" are trademarks of Apple Inc.; "小米" / "Xiaomi" / "HyperOS" are trademarks of Xiaomi. Used here for reference only.
- For learning and personal use. Modifying system runtime behaviour carries risk — assess it yourself and **back up your data**.

### License

[PolyForm Noncommercial License 1.0.0](LICENSE) — **noncommercial use only**.

- ✅ **Free to use** for personal study, research, experimentation, hobby projects,
  and by nonprofits, schools and public research organizations.
- ⛔ **Separate license required** for *any* commercial use — including selling it, shipping it inside a paid
  product or service, offering it as SaaS / hosted service, production use inside a company, or paid
  consulting/support built on it. Written commercial permission from the author is required **in advance**.
- 📧 For commercial licensing, reach the author via [Issues](https://github.com/213DEE/XiaomiDuo/issues).

> Required Notice: Copyright © 2026 213DEE (https://github.com/213DEE/XiaomiDuo)

⚠️ This project is **source-available**, *not* an OSI-approved open source license — it restricts commercial use.
