---
file: layout
last_updated: 2026-04-29
---

# 布局系统 · Layout

> 4pt 基线 + 12 列栅格 + 双列流主导。**安全区与边距是最常见的踩坑点**。

---

## 1. 屏幕尺寸覆盖

| 设备 | 宽度 | 设计稿基准 | 备注 |
|---|---|---|---|
| iPhone SE / mini | 320-375pt | 375pt | 极小屏检查必跑 |
| iPhone 标准 | 375-390pt | 375pt | 主基准 |
| iPhone Plus / Pro Max | 414-430pt | 自适应 | 双列卡略宽 |
| 折叠屏 闭合 | 375-400pt | 375pt | 同标准 |
| 折叠屏 展开 | 750-820pt | 757pt | 双栏 / 三列 |
| iPad mini | 744-820pt | 768pt | 双栏 |
| iPad Pro | 1024-1366pt | 1024pt | 桌面级布局 |

**铁律**:设计稿 375pt + 自适应规则,**不锁死像素**。

---

## 2. 栅格

### 手机端(单栏)
- 边距:`spacing.12` (24pt) 或 `spacing.8` (16pt)
- 栅格列:12 列,gutter `spacing.6` (12pt)
- 双列流:卡宽 = (屏宽 - 边距×2 - 卡间距) / 2

### 折叠屏 / iPad(双栏 / 多栏)
- 主栏 + 副栏(70:30 或 60:40)
- 三列流(在更宽的屏幕)
- 边距 `spacing.16` (32pt)

---

## 3. 安全区(Safe Area)

iOS / Android 都有刘海 / Dynamic Island / 凹口屏 / Home Indicator。

```
┌────────────────────┐
│  status bar / 刘海 │  ← top safe area(自动获取)
├────────────────────┤
│                    │
│   内容区          │
│                    │
├────────────────────┤
│  bottom safe area  │  ← iOS Home Indicator
└────────────────────┘
```

**铁律**:
- 任何固定底部元素(底部 CTA / Tab Bar / 浮动按钮)必须考虑 bottom safe area
- 全屏模态背景必须延伸到 safe area 外(否则刘海下露出底色)
- 顶部状态栏在浅色模式下使用深色 icon,深色模式下使用浅色 icon

---

## 4. 双列流标准

> 京东 APP 商品流主要形态。

| 维度 | 取值 |
|---|---|
| 卡宽 | (屏宽 - 24×2 - 12) / 2(手机)|
| 卡间距 | 横 12pt / 纵 12pt |
| 卡圆角 | `radius.card` (8pt) |
| 卡阴影 | none(默认)/ `shadow.card`(可选)|
| 卡片节奏 | 商品图(1:1)+ 标题区 + 价格区 + 角标 + 加购按钮(可选)|

**家族锚定**:[[../../horizontal/double-column-card/SKILL.md]] 已经定义五大家族 DNA。

---

## 5. 列表流

| 类型 | 行高 | 边距 |
|---|---|---|
| 标准列表项 | 56-72pt | 卡片左 16pt 右 16pt |
| 紧凑列表项 | 44-52pt | 同上 |
| 卡片列表 | 自适应 | 卡间 8-12pt |

---

## 6. Tab Bar / 顶部导航

| 元素 | 高度 |
|---|---|
| 状态栏 | 系统(iOS 44pt / Android 24pt) |
| 顶部导航栏 | 44pt |
| 顶部 Tab(在导航下) | 40pt |
| 底部 Tab Bar | 49pt(iOS)/ 48pt(Android),+ bottom safe area |

---

## 7. 沉浸式

部分页面采用沉浸式(导航栏与内容融合):
- PDP 顶部图(状态栏文字色根据图色自动切换)
- 大促首屏 Banner
- 视频流

**实现**:导航栏背景透明 + 滚动渐变到不透明,详见 [[../interaction/navigation.md]]。

---

## 8. 反例

| ❌ 反面 | 解释 |
|---|---|
| 固定底部 CTA 不考虑 safe area | iPhone X+ 用户被 home indicator 挡住 |
| 双列卡片宽度硬编码 | 在不同屏宽下溢出 |
| 边距硬编码(如 padding: 20px) | 不引用 spacing token |
| 首屏内容不考虑刘海 | 关键文字被遮挡 |
