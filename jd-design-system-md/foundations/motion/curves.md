---
file: curves
last_updated: 2026-04-29
---

# 缓动曲线 · Easing Curves

> 缓动曲线决定动效的"性格"。京东 6 条曲线覆盖 95% 场景,**不允许自定义新曲线**。

---

## 曲线类型对照

| Token | 贝塞尔 | 性格 | 用途 |
|---|---|---|---|
| `motion.easing.linear` | (0,0,1,1) | 匀速,机械 | 进度条 / 持续动效 |
| `motion.easing.standard` | (0.4,0,0.2,1) | 出现+消失,平衡 | 默认 |
| `motion.easing.decelerate` | (0,0,0.2,1) | 进入,减速冲入 | 模态进入 / Toast 出现 |
| `motion.easing.accelerate` | (0.4,0,1,1) | 退出,加速离开 | 模态退出 / Toast 消失 |
| `motion.easing.spring` | 弹性曲线 | 弹回 | 加购成功 / 收藏 / Confirm |
| `motion.easing.emphasized` | (0.2,0,0,1) | 强调主转场 | 页面级转场 |

---

## 选择决策树

```
动效是什么?
├── 持续型(进度 / Loading)→ linear
├── 出现+消失(Toggle / Tab)→ standard
├── 进入(模态 / Toast / 卡片入场)→ decelerate
├── 退出(模态消失 / Sheet 关闭)→ accelerate
├── 弹性反馈(成功 / 选中)→ spring
└── 主转场(页面切换)→ emphasized
```

---

## 不同平台默认

| 平台 | 默认曲线 |
|---|---|
| iOS | standard |
| Android | emphasized(Material 3 推荐) |
| Web(京东 H5)| standard |

跨平台时通过 Token 自动映射。

---

## 与时长配合

| 时长 | 推荐曲线 |
|---|---|
| 0-150ms | standard / decelerate(短动效用单向曲线即可) |
| 150-300ms | standard / decelerate / accelerate |
| 300-500ms | emphasized / spring(更需要"性格")|
| 500ms+ | emphasized + 装饰性 spring |

---

## 反例

| ❌ 反面 | 解释 |
|---|---|
| 自定义新曲线(不在 Token 中) | 与体系不一致 |
| 进入用 accelerate(应该 decelerate) | 视觉违和 |
| 长动效用 linear(无表情)| 机械感 |
| 微交互用 emphasized(过于戏剧)| 喧宾夺主 |
