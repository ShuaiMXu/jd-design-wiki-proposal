---
file: duration
last_updated: 2026-04-29
---

# 动效时长 · Duration

> Token 见 [[../tokens/motion.md#duration]]。本文讲"什么场景用多长时间"。

---

## 时长决策表

| 场景 | 推荐 Token | 值 |
|---|---|---|
| 按钮按下/释放 | `immediate` | 100ms |
| 状态切换(选中 / Toggle) | `immediate` | 100ms |
| Toast 显隐 | `fast` | 200ms |
| Tab 切换 | `fast` | 200ms |
| Spinner 单圈 | `fast` × 4 | 800ms |
| 模态弹出 | `normal` | 300ms |
| 抽屉(Sheet)滑入 | `normal` | 300ms |
| 加购飞动画 | `normal` | 300ms(总时长 500ms) |
| 列表项入场(阶梯) | `fast` × 3 | 600ms 总 |
| 页面转场 | `slow` | 500ms |
| 大促礼花 | `slower` | 800ms |
| 引导动效 | `slower` × 2 | 1.6s |

---

## 移动端时长铁律

**移动端动效 ≤ 500ms**(除引导/装饰性场景)。

超过 500ms = 用户感觉"系统反应慢"。

---

## 主流程 vs 装饰性

| 区域 | 时长边界 |
|---|---|
| 主流程(PDP / Cart / Checkout) | ≤ 200ms |
| 一般功能页 | ≤ 300ms |
| 大促首屏 / 节庆 | ≤ 800ms |
| 引导 / 教学 | 可更长(2-3 秒)|

---

## 反例

| ❌ 反面 | 解释 |
|---|---|
| 主流程动效 > 300ms | 影响转化效率 |
| 模态进入 < 100ms | 跳变,无层级感 |
| Toast 显示 < 1.5 秒 | 用户没看清就消失 |
| Toast 显示 > 5 秒 | 阻塞用户视线 |
