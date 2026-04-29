---
file: icon-system
last_updated: 2026-04-29
---

# 图标系统 · Icon

> 京东图标采用 3 风格(线性 / 面性 / 双色)+ 5 尺寸 + 统一栅格。**所有图标必须从 icon library 引用,不允许业务自绘**。

---

## 1. 三种风格

| 风格 | 用途 | 关键场景 |
|---|---|---|
| **线性**(line)| 默认风格,80% 场景 | 工具栏 / 列表 / 表单 |
| **面性**(filled)| 强调态(选中 / 激活)| Tab Bar 选中 / 收藏已选 |
| **双色**(duotone)| 大促 / 营销 / 装饰 | 频道 icon / 优惠券 |

**配对规则**:
- 线性 + 面性 配对使用(切换状态)
- 双色不与线/面性混用在同一组

---

## 2. 尺寸阶梯

| Token | 值 | 用途 |
|---|---|---|
| `icon.size.xs` | 12pt | 嵌入小标签 / 角标 |
| `icon.size.s` | 16pt | 列表项 / 表单 |
| `icon.size.m` | 20pt | 工具栏 / 卡片操作 |
| `icon.size.l` | 24pt | Tab Bar / 标题栏 |
| `icon.size.xl` | 32pt | 频道入口 / 营销大 icon |
| `icon.size.xxl` | 48pt+ | 空状态 / 营销主图 |

---

## 3. 设计栅格

所有图标在 24×24 栅格中绘制,**保留 2pt 安全边距**(实际有效区域 20×20)。

| 尺寸 | 栅格 | 描边 |
|---|---|---|
| 12pt 图标 | 12×12 栅格 | 1pt |
| 16pt 图标 | 16×16 栅格 | 1.5pt |
| 20pt / 24pt | 24×24 栅格 | 1.5pt |
| 32pt+ | 不限 | 2pt+ |

---

## 4. 图标库分类

```
icon-library/
├── general/     # 通用(箭头 / 加减 / 关闭 / 设置)
├── action/      # 操作(分享 / 下载 / 编辑 / 删除)
├── status/      # 状态(成功 / 警告 / 错误 / 加载)
├── commerce/    # 商业(购物车 / 订单 / 优惠券 / 配送)
├── social/      # 社交(收藏 / 关注 / 评论 / 点赞)
├── communication/ # 沟通(消息 / 通知 / 客服)
├── media/       # 媒体(播放 / 暂停 / 音量 / 摄像头)
├── brand/       # 品牌(京东 / Logo / 子品牌)
└── illustration/ # 大尺寸插画(空状态 / 引导)
```

---

## 5. 颜色

图标颜色继承父元素,**不允许图标自带色值**(除双色 / 装饰图标)。

```css
/* 默认 */
.icon { color: var(--color-neutral-text-primary); }

/* 错误状态 */
.icon-error { color: var(--color-semantic-danger); }

/* 选中态 */
.icon-active { color: var(--color-brand-primary); }
```

**双色图标例外**:在 SVG 内嵌 currentColor + 第二色,通过 props 控制。

---

## 6. 图标 + 文字组合

| 组合 | 间距 |
|---|---|
| 图标(s)+ 文字(body.m) | `spacing.4` (8pt) |
| 图标(m)+ 文字(body.m) | `spacing.4` (8pt) |
| 图标(l)+ 文字(body.l) | `spacing.6` (12pt) |
| Tab Bar 图标(l)+ 文字(caption.l) | `spacing.2` (4pt),垂直 |

---

## 7. 反例

| ❌ 反面 | 解释 |
|---|---|
| 业务自绘图标 | 风格与库不一致 |
| 图标硬编码色值 | 不响应主题切换 |
| 不同栅格图标混用 | 视觉重量不一致 |
| 极小尺寸用极复杂图标 | 16pt 图标内放 5 个细节,看不清 |
| Tab Bar 用纯线性(不切换) | 选中态视觉弱 |

---

## 8. 工具链

- 设计师:Figma Icon Library(自动 publish)
- 工程师:`@jd/icons` npm 包(自动从 Figma 同步)
- AI 消费:`icon-library.json`(包含每个图标的 ID / 类别 / 适用场景描述)
