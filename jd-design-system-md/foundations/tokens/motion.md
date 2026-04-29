---
token_category: motion
last_updated: 2026-04-29
---

# 动效 Token · motion

> 动效 Token 包含 duration(时长)和 easing(缓动)两类。组件 visual.md 引用动效时**只能引用 Token,不能写裸数字**。

---

## 1. 时长 · duration

| Token | 值 | 用途 |
|---|---|---|
| `motion.duration.instant` | 0ms | 立即,无动效 |
| `motion.duration.immediate` | 100ms | 即时反馈(按下 / 状态切换) |
| `motion.duration.fast` | 200ms | 标准微交互(按钮 / Toggle / Toast 显隐) |
| `motion.duration.normal` | 300ms | 中等动效(模态弹出 / 抽屉滑入) |
| `motion.duration.slow` | 500ms | 大幅度动效(页面转场)|
| `motion.duration.slower` | 800ms | 引导动效 / 大促礼花 |

**铁律**:**移动端动效不要超过 500ms**(除非引导 / 装饰性场景)。用户感知超过 500ms = 慢 / 卡。

---

## 2. 缓动 · easing

| Token | 值 | 用途 |
|---|---|---|
| `motion.easing.linear` | `cubic-bezier(0, 0, 1, 1)` | 进度条 / 持续型动效 |
| `motion.easing.standard` | `cubic-bezier(0.4, 0, 0.2, 1)` | 默认(出现+消失) |
| `motion.easing.decelerate` | `cubic-bezier(0, 0, 0.2, 1)` | 进入(加速冲入) |
| `motion.easing.accelerate` | `cubic-bezier(0.4, 0, 1, 1)` | 退出(加速离开) |
| `motion.easing.spring` | `cubic-bezier(0.5, 1.5, 0.5, 1)` | 弹性(确认 / 加购成功) |
| `motion.easing.emphasized` | `cubic-bezier(0.2, 0, 0, 1)` | 强调(主转场) |

**iOS 推荐**:`standard` / `decelerate` / `accelerate` / `spring`
**Android 推荐**:Material 体系的 `emphasized` / `standard`

---

## 3. 语义动效角色

| Token | 引用 | 用途 |
|---|---|---|
| `motion.button.press` | `duration.immediate` + `easing.standard` | 按钮按下/释放 |
| `motion.modal.enter` | `duration.normal` + `easing.decelerate` | 模态进入 |
| `motion.modal.exit` | `duration.fast` + `easing.accelerate` | 模态退出 |
| `motion.page.transition` | `duration.slow` + `easing.emphasized` | 页面转场 |
| `motion.tab.switch` | `duration.fast` + `easing.standard` | Tab 切换 |
| `motion.add-to-cart` | `duration.normal` + `easing.spring` | 加购飞动画 |
| `motion.toast.enter` | `duration.fast` + `easing.decelerate` | Toast 出现 |
| `motion.toast.exit` | `duration.fast` + `easing.accelerate` | Toast 消失 |

---

## 4. 减少动效 · reduced motion

iOS / Android 系统设置中"减少动效"开启时:

| 默认动效 | 减少动效后 |
|---|---|
| 模态滑入 | 淡入 |
| 转场动画 | 直接切换 |
| 加购飞动画 | 仅 Toast 提示 |
| 大促礼花 | 不显示 |

**实现**:`motion.reduced.duration.fast` 自动映射到 `0ms`。组件代码不需要单独判断,Token 层处理。

详见:[[../../horizontal/a11y/motion-reduce.md]]

---

## 5. 反例

| ❌ 反面 | 解释 |
|---|---|
| `transition: all 250ms ease` | 数值不在 Token 中 |
| 缓动用 `ease`(浏览器默认) | 与 Token 体系不一致 |
| 移动端动效 > 500ms(非装饰性) | 影响感知速度 |
| 不响应"减少动效"系统设置 | 违反 a11y |
| 同一交互不同位置动效不一致 | 节奏混乱 |
