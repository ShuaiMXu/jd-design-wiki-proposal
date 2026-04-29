---
token_category: radius
last_updated: 2026-04-29
---

# 圆角 Token · radius

> 京东圆角体系简洁,只有 7 阶 + 5 个语义角色。所有组件圆角都引用 Token,不允许硬编码。

---

## 1. 基础阶梯

| Token | 值 | 常见用途 |
|---|---|---|
| `radius.0` | 0 | 直角(列表分隔 / 全屏) |
| `radius.4` | 4 | 小标签 / Tag |
| `radius.8` | 8 | 默认按钮 / 卡片 |
| `radius.12` | 12 | 大卡片 / 模态框 |
| `radius.16` | 16 | 顶级模态 / 大结构 |
| `radius.24` | 24 | 极大场景(大促首屏装饰) |
| `radius.full` | 9999 | 胶囊型(头像 / 圆形按钮 / 大促胶囊按钮) |

---

## 2. 语义角色

| Token | 引用 | 用途 |
|---|---|---|
| `radius.button` | `radius.8` | 默认按钮(可被主题覆盖为 full) |
| `radius.card` | `radius.8` | 默认卡片 |
| `radius.card-large` | `radius.12` | 大卡片 / 突出卡片 |
| `radius.modal` | `radius.16` | 模态对话框 |
| `radius.tag` | `radius.4` | 标签 / Chip |
| `radius.avatar` | `radius.full` | 头像 |
| `radius.input` | `radius.8` | 输入框 |
| `radius.skeleton` | `radius.4` | 骨架屏 |

---

## 3. 主题切换

大促主题可整体覆盖语义角色:

| 场景 | radius.button | radius.card |
|---|---|---|
| Default | 8pt | 8pt |
| 618 | full(胶囊) | 12pt |
| 1111 | full(胶囊) | 16pt |
| 春节 | 8pt(保持温和) | 12pt + 装饰边角 |

主题切换由 Token 层完成,组件代码不感知。

---

## 4. 反例

| ❌ 反面 | 解释 |
|---|---|
| `border-radius: 10px` | 硬编码,不在阶梯内 |
| 同一卡片不同位置不同圆角 | 不允许(除非是有意识的视觉手段) |
| 小尺寸用大圆角(如 24pt 用在 32pt 高的按钮) | 视觉破碎 |

---

## 5. 注意事项

- **iOS 自带继承超圆角(superellipse)**,Token 值在 iOS 实际渲染会略偏圆润
- **大促胶囊按钮**圆角 = 高度的一半,等价于 `radius.full`
- **图片裁剪**圆角通过 mask 实现,引用 `radius.card` 或独立 Token
