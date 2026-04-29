---
token_category: spacing
last_updated: 2026-04-29
---

# 间距 Token · spacing

> 4pt 基线体系 + 语义间距。**所有 padding / margin / gap 必须引用 Token,不允许写裸数字**。

---

## 1. 基础阶梯(4pt 基线)

| Token | 值 | 常见用途 |
|---|---|---|
| `spacing.0` | 0 | 紧贴 |
| `spacing.1` | 2 | 极小间隙(图标-数字 微调)|
| `spacing.2` | 4 | 元素内极小间距 |
| `spacing.3` | 6 | (慎用,优先 4 或 8) |
| `spacing.4` | 8 | 文-icon / icon-icon 间距 |
| `spacing.6` | 12 | 紧凑列表项间距 |
| `spacing.8` | 16 | 标准卡片内边距 / 模块间距 |
| `spacing.10` | 20 | 卡片间距 |
| `spacing.12` | 24 | 模块间距 / 页面边距 |
| `spacing.16` | 32 | 大模块间距 |
| `spacing.20` | 40 | 节庆装饰间距 |
| `spacing.24` | 48 | 大结构间距 |
| `spacing.32` | 64 | 大留白(空状态) |

**核心约定**:**优先使用 4 的倍数**,即 0/4/8/12/16/20/24/32/40/48/64。`spacing.1`(2pt)和 `spacing.3`(6pt)是例外阶梯,仅用于像素级微调,谨慎引用。

---

## 2. 语义间距

> 用于组件 visual.md 引用,避免开发到处写 `spacing.8`。

| Token | 引用 | 用途 |
|---|---|---|
| `spacing.page-edge` | `spacing.12` (24pt) | 页面左右边距 |
| `spacing.section-gap` | `spacing.16` (32pt) | 大模块之间 |
| `spacing.card-gap` | `spacing.10` (20pt) | 卡片之间 |
| `spacing.card-padding` | `spacing.8` (16pt) | 卡片内边距 |
| `spacing.list-item-gap` | `spacing.6` (12pt) | 列表项之间 |
| `spacing.icon-text-gap` | `spacing.4` (8pt) | 图标与文字 |
| `spacing.button.padding-h.L` | `spacing.12` (24pt) | L 按钮水平内边距 |
| `spacing.button.padding-h.M` | `spacing.8` (16pt) | M 按钮水平内边距 |
| `spacing.button.padding-h.S` | `spacing.6` (12pt) | S 按钮水平内边距 |
| `spacing.button.padding-h.XS` | `spacing.4` (8pt) | XS 按钮水平内边距 |
| `spacing.button.padding-h.Mini` | `spacing.4` (8pt) | Mini 按钮水平内边距 |
| `spacing.modal-padding` | `spacing.12` (24pt) | 弹窗内边距 |

---

## 3. 栅格(Grid)

页面采用 8pt 基线 + 12 列栅格(双列流场景)。

| 设备 | 栅格列宽 | 列间距 | 边距 |
|---|---|---|---|
| 手机(375pt 宽) | 双列流:170pt 卡 + 12pt gap + 12pt 左右边距 | - | `spacing.12` |
| 手机(414pt 宽) | 双列流:189pt 卡 + 12pt gap + 12pt 左右边距 | - | `spacing.12` |
| 折叠屏(展开) | 三列流 / 双栏布局 | `spacing.10` | `spacing.16` |
| iPad | 多列布局 / 两栏布局 | `spacing.12` | `spacing.16` |

**双列卡固定规则**:卡片宽度 = (屏宽 - 边距×2 - gap) / 2

详见:[[../visual/layout.md]]

---

## 4. 安全区 · safe-area

iOS 刘海屏 / Dynamic Island / Home Indicator,Android 凹口屏 / 导航栏:

| Token | 值 |
|---|---|
| `spacing.safe-area.top` | 设备相关(自动获取) |
| `spacing.safe-area.bottom` | 设备相关(自动获取) |
| `spacing.bottom-tab-height` | 49pt(iOS)/ 48pt(Android) |

**重要**:任何固定底部的元素(底部 CTA / 工具栏)必须考虑 safe-area。

---

## 5. 反例

| ❌ 反面 | 解释 |
|---|---|
| 写裸数字 `padding: 14px` | 破坏 4pt 基线 |
| 通过 transform 模拟间距 | 工具链无法识别 |
| 自定义新阶梯(如 spacing.7) | 必须走治理 |
| 不使用语义间距(如组件直接引用 spacing.8) | 可读性差(应该用 spacing.card-padding)|

---

## 6. 历史

- v1.0(2026-04):本版,4pt 基线 + 语义间距
- v0.x:各业务线随意 padding,导致跨业务节奏不一致
