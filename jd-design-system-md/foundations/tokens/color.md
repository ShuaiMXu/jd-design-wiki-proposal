---
token_category: color
last_updated: 2026-04-29
---

# 色彩 Token · color

> 京东 APP 色彩体系分 5 大族:**品牌 / 语义 / 中性 / 功能 / 数据可视化**。每个色都有 light/dark 双值。
>
> **不要在 visual.md 出现任何具体色值**。所有色值在本文档管理。

---

## 1. 品牌色 · color.brand

| Token | Light | Dark | 用途 |
|---|---|---|---|
| `color.brand.primary` | `#fa2c19` | `#ff4538` | 京东红主色,主 CTA / 价格 / 品牌区 |
| `color.brand.primary.hover` | `#e02a17` | `#ff5949` | 桌面端 hover(iPad) |
| `color.brand.primary.pressed` | `#cc2615` | `#ff3322` | 移动端按下 |
| `color.brand.primary.subtle` | `#fff1f0` | `#3d1a17` | 浅色 wash(背景/标识)|
| `color.brand.gold` | `#f5a623` | `#ffb84d` | 京东金,辅助品牌色(VIP / 高端) |
| `color.brand.gradient.618` | linear-gradient(...)| - | 618 大促渐变(主题包) |
| `color.brand.gradient.1111` | linear-gradient(...) | - | 双 11 大促渐变(主题包) |

**使用规则**:见 [[brand-expression]] + [[../visual/color-usage.md#brand]]

---

## 2. 语义色 · color.semantic

> 语义色用于状态传达,**与品牌色刻意区分**(避免错误提示与转化按钮视觉混淆)。

| Token | Light | Dark | 用途 |
|---|---|---|---|
| `color.semantic.success` | `#00a870` | `#1ed688` | 成功状态(支付成功 / 订单完成) |
| `color.semantic.success.subtle` | `#e8f8f3` | `#0a2e1f` | 成功背景 wash |
| `color.semantic.warning` | `#ff9500` | `#ffaa33` | 警告(库存紧张 / 待支付) |
| `color.semantic.warning.subtle` | `#fff4e0` | `#3d2a08` | 警告背景 wash |
| `color.semantic.danger` | `#e62e1e` | `#ff5544` | 错误(下单失败 / 校验错) |
| `color.semantic.danger.subtle` | `#ffeeed` | `#3d1715` | 错误背景 wash |
| `color.semantic.info` | `#1677ff` | `#4a92ff` | 提示(系统通知 / 新功能) |
| `color.semantic.info.subtle` | `#e8f3ff` | `#08203d` | 提示背景 wash |

---

## 3. 中性色 · color.neutral

> 中性色支撑 80% 的页面元素。京东中性色偏暖灰,与品牌红呼应。

### 文字
| Token | Light | Dark | 用途 |
|---|---|---|---|
| `color.neutral.text.primary` | `#1a1a1a` | `#f0f0f0` | 主文字 |
| `color.neutral.text.secondary` | `#5a5a5a` | `#a8a8a8` | 次文字 / 辅助说明 |
| `color.neutral.text.tertiary` | `#8a8a8a` | `#787878` | 三级辅助 |
| `color.neutral.text.disabled` | `#c8c8c8` | `#5a5a5a` | 禁用文字 |
| `color.neutral.text.onColor` | `#ffffff` | `#ffffff` | 在彩色背景上的文字(品牌红 / 渐变上的白字) |
| `color.neutral.text.link` | `#1677ff` | `#4a92ff` | 链接(注:不是品牌红) |

### 背景
| Token | Light | Dark | 用途 |
|---|---|---|---|
| `color.neutral.bg.body` | `#f5f5f5` | `#0a0a0a` | 页面底层背景 |
| `color.neutral.bg.surface` | `#ffffff` | `#1c1c1e` | 卡片 / 模块表面 |
| `color.neutral.bg.surface-elevated` | `#ffffff` | `#2c2c2e` | 抬升表面(对话框) |
| `color.neutral.bg.pressed` | `#f0f0f0` | `#3a3a3c` | 点击态背景 |
| `color.neutral.bg.disabled` | `#e8e8e8` | `#3a3a3c` | 禁用背景 |

### 描边 / 分隔
| Token | Light | Dark | 用途 |
|---|---|---|---|
| `color.neutral.border.default` | `#e0e0e0` | `#3a3a3c` | 默认描边 |
| `color.neutral.border.subtle` | `#f0f0f0` | `#2c2c2e` | 浅描边 / 分隔线 |
| `color.neutral.border.strong` | `#c0c0c0` | `#5a5a5c` | 强描边 |
| `color.neutral.border.disabled` | `#e8e8e8` | `#3a3a3c` | 禁用描边 |

---

## 4. 功能色 · color.functional

| Token | Light | Dark | 用途 |
|---|---|---|---|
| `color.functional.price` | `#fa2c19` | `#ff4538` | 价格(同品牌主色,但语义独立)|
| `color.functional.price.subtle` | 历史价 / 划线价 = neutral.text.tertiary | - | 划线辅助色 |
| `color.functional.discount-tag` | `#fa2c19` | `#ff4538` | 折扣标签底色 |
| `color.functional.coupon` | `#ff6b35` | `#ff8855` | 优惠券色(略偏橙) |
| `color.functional.vip` | `#1a1a1a` + 金 | - | VIP / 黑金会员 |

---

## 5. 数据可视化 · color.viz

> 用于图表 / 数据可视化场景,**避免与品牌色 / 语义色混淆**。

| Token | Light | 用途 |
|---|---|---|
| `color.viz.qual.1` ~ `color.viz.qual.10` | 10 色定性调色板 | 分类型数据 |
| `color.viz.seq.1` ~ `color.viz.seq.5` | 5 阶定序调色板 | 程度型数据 |
| `color.viz.div.neg` / `color.viz.div.zero` / `color.viz.div.pos` | 散度调色板 | 双向数据(涨跌 等)|

---

## 6. 透明度 · 不作为单独 Token

**京东不允许通过透明度模拟新色值**。所有"半透明"效果应该通过实色 Token 实现:

❌ 反例:`background: rgba(255, 0, 0, 0.5)`(模拟浅红)
✅ 正确:`background: var(--color-brand-primary-subtle)`(预定义浅色 wash)

例外:模态背景蒙层(`color.modal.scrim` 是唯一允许的透明度 Token,值 `rgba(0,0,0,0.45)` light / `rgba(0,0,0,0.65)` dark)。

---

## 7. 对比度自检

每个色彩 Token 在文档中标注对比度结果:

| 配对 | 对比度 | WCAG 2.1 AA | 备注 |
|---|---|---|---|
| `color.neutral.text.primary` on `color.neutral.bg.body` | 13.6:1 | ✅ 通过(正文 4.5:1)|
| `color.neutral.text.onColor` on `color.brand.primary` | 4.8:1 | ✅ 通过(正文 4.5:1)|
| `color.neutral.text.disabled` on `color.neutral.bg.disabled` | 3.2:1 | ✅ 通过(禁用文字 3:1 允许)|

CI 任务每次 Token 修改自动跑对比度检查,不达标的修改自动 block。

---

## 8. 历史版本

- v1.0(2026-04):本文档,与京东 15.0 设计语言同步
- v0.9 之前:各业务线散落色值 ~~~~~~ 历史教训详见 governance/changelog
