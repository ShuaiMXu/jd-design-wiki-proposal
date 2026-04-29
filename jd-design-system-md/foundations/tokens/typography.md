---
token_category: typography
last_updated: 2026-04-29
---

# 字体 Token · typography

> 京东 APP 字体体系 = **多字族支持(系统字体优先)+ 4 阶字号阶梯 + 4 阶字重 + 数字字族独立**。
>
> 数字字族独立是京东特色:价格 / 数量 / 倒计时使用等宽数字,提升识别度和稳定感。

---

## 1. 字族 · font-family

| Token | iOS | Android | 备注 |
|---|---|---|---|
| `typography.family.sans` | SF Pro Display + 苹方 | Roboto + 思源黑体 | 默认正文 |
| `typography.family.serif` | (不主用) | (不主用) | 仅特殊场景 |
| `typography.family.mono` | SF Mono | Roboto Mono | 代码 / ID 展示 |
| `typography.family.number` | SF Pro Display + 等宽数字特性 | Roboto + 等宽数字特性 | **价格 / 数量 / 倒计时** ★ |
| `typography.family.brand` | 京东品牌字体(JDLanggangXingZhi) | 同 | 品牌区 / 大促 Banner |

**数字字族特别说明**:
- 启用 OpenType `tnum`(tabular-nums)特性
- 价格 "¥99.00" 中每个数字宽度一致,跳动时不抖
- iOS:`SF Pro Display` + `featureSettings: ['tnum']`
- Android:`Roboto` + `fontFeatureSettings = "tnum"`

---

## 2. 字号阶梯 · font-size

> 4 阶基础阶梯 + 1 阶展示阶。**新设计需求不允许引入阶梯外字号**。

### 显示阶(Display)· 大促 / 营销
| Token | size (pt) | line-height | 用途 |
|---|---|---|---|
| `typography.size.display.xl` | 48 | 56 | 大促主标题 |
| `typography.size.display.l` | 36 | 44 | 营销大字 |
| `typography.size.display.m` | 28 | 36 | 节庆首屏 |

### 标题阶(Heading)
| Token | size | line-height | 用途 |
|---|---|---|---|
| `typography.size.heading.h1` | 24 | 32 | 页面主标题 |
| `typography.size.heading.h2` | 20 | 28 | 模块标题 |
| `typography.size.heading.h3` | 17 | 24 | 卡片 / 子模块标题 |
| `typography.size.heading.h4` | 15 | 22 | 列表项标题 |

### 正文阶(Body)
| Token | size | line-height | 用途 |
|---|---|---|---|
| `typography.size.body.l` | 17 | 24 | 重点正文 |
| `typography.size.body.m` | 15 | 22 | 默认正文 |
| `typography.size.body.s` | 13 | 20 | 辅助正文 |

### 辅助阶(Caption)
| Token | size | line-height | 用途 |
|---|---|---|---|
| `typography.size.caption.l` | 12 | 18 | 备注 / 辅助说明 |
| `typography.size.caption.m` | 11 | 16 | 角标文字 |
| `typography.size.caption.s` | 10 | 14 | 极小辅助(慎用) |

---

## 3. 字重 · font-weight

| Token | iOS / Android | 用途 |
|---|---|---|
| `typography.weight.regular` | 400 | 默认正文 |
| `typography.weight.medium` | 500 | 强调正文 / 列表标题 |
| `typography.weight.semibold` | 600 | 页面/模块标题 / 主按钮 |
| `typography.weight.bold` | 700 | 价格 / 大促主标题 / 强 CTA |

**禁用**:
- 不允许 100 / 200 (过细,弱视用户识别困难)
- 不允许 800 / 900 (过粗,京东视觉传统不符)

---

## 4. 行高 · line-height

行高 = 字号 × 倍率,常用倍率 1.4-1.5。每个字号 Token 已自带配套行高,**不允许自定义**。

例外:
- 单行展示场景(按钮 / Tag)行高 = 字号(无额外行间空间)
- 大促主标题可使用 1.2 倍率(节奏紧凑)

---

## 5. 字间距 · letter-spacing

| Token | 值 | 用途 |
|---|---|---|
| `typography.tracking.tight` | -0.01em | 大号标题(收紧) |
| `typography.tracking.normal` | 0 | 默认 |
| `typography.tracking.loose` | 0.04em | 全大写英文 / 标签 |

---

## 6. 语义字体角色

> 用于组件 visual.md 引用,屏蔽底层字号阶梯细节。

| Token | 引用 | 用途 |
|---|---|---|
| `typography.button.L` | `body.l` + `weight.semibold` | L 尺寸按钮 |
| `typography.button.M` | `body.m` + `weight.medium` | M 尺寸按钮 |
| `typography.button.S` | `body.s` + `weight.medium` | S 尺寸按钮 |
| `typography.button.XS` | `caption.l` + `weight.regular` | XS 尺寸按钮 |
| `typography.button.Mini` | `caption.m` + `weight.regular` | Mini 尺寸按钮 |
| `typography.price.large` | `display.m` + `weight.bold` + `family.number` | PDP 主价格 |
| `typography.price.medium` | `heading.h2` + `weight.bold` + `family.number` | 卡片价格 |
| `typography.price.small` | `body.l` + `weight.semibold` + `family.number` | 列表项价格 |
| `typography.price.strikethrough` | `caption.l` + `family.number` + 删除线 | 划线价 |
| `typography.tag` | `caption.m` + `weight.medium` | 标签文字 |
| `typography.input` | `body.m` + `weight.regular` | 输入框文字 |
| `typography.placeholder` | `body.m` + `weight.regular` + `color.neutral.text.tertiary` | 占位符 |

---

## 7. 字号缩放 · font-scaling

京东 APP 支持系统字号 85%-150%。**布局必须在 150% 字号下不崩**。

| 系统字号 | 行为 |
|---|---|
| 85% | 紧凑布局,适合信息密度高的用户 |
| 100% | 默认 |
| 130% | 适老模式默认 |
| 150% | 极端字号,所有页面必须不崩 |

**实现细节**:[[../../horizontal/a11y/font-scaling.md]]

**测试要求**:任何新组件 / 新页面上线前必须跑 85% / 100% / 150% 三个字号截图对比。

---

## 8. 多语言支持

京东 APP 主要支持中文 / 英文 / 西班牙语(京东全球版)。

| 语言 | 字族 | 备注 |
|---|---|---|
| 中文(简) | 苹方 / 思源黑体 | 默认 |
| 中文(繁) | 苹方繁 / 思源黑体繁 | 港澳台版本 |
| 英文 | SF Pro / Roboto | 京东全球版 |
| 西班牙语 | SF Pro / Roboto | 京东全球版 |
| 其他 CJK | 思源系列 | 日韩版本(若有) |

**布局考虑**:英文 / 西语字符宽度差异大,按钮文案需测试。

---

## 9. 反例

| ❌ 反面 | 解释 |
|---|---|
| 字号阶梯外的值(如 14pt 16pt) | 破坏统一性 |
| 价格不用 number 字族 | 数字跳动抖动 / 等宽不统一 |
| 字重 100/200 | 弱视用户识别困难 |
| 自定义行高 | 破坏节奏一致性 |
