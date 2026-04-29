---
zone: horizontal
section: double-column-card
last_updated: 2026-04-29
---

# 🎴 双列卡专项 · Double Column Card

> 跨部门双列卡治理。**已沉淀为可被任意 AI Agent 调用的 Skill**。

---

## 这是一个 Skill,不是一篇文档

本 Zone 的内容是一个完整的 agentskills.io 标准 Skill,**实际位置**:
- 公开仓库:https://github.com/ShuaiMXu/jd-double-column-card-skill
- 本地工作区:`/root/happyclaw/data/groups/main/skills/jd-double-column-card/`
- 当前版本:v0.5.2

---

## 核心架构

### 五大家族
| 家族 | 锚点(底部不变量)| 主要业务 |
|---|---|---|
| 内容家族 | 互动数 / UGC 标签 | 推荐流(种草 / 测评)|
| 商品家族 | 价格 / 加购按钮 | 主站 / 超市 / 生鲜 |
| 圈子家族 | 圈子标识 / 关注 | 京东养车 / 美妆社区 |
| 点评家族 | 评分 / 评价数 | 点评 / Beauty / 厨房 |
| 新品家族 | "新品" / 上市标识 | 新品频道 |

### 双标签协议
- `business_line`:**人工声明**(永远不要推断)
- `card_type`:Skill 视觉识别

### L1(9 条跨家族规约)+ L2(家族专属)
- L1-1 至 L1-9 是所有家族都必须满足的
- L2 是每家族特有的

### 8 条核心原则
特别注意:
- **原则 7**:结构优先、内容无涉
- **原则 8**:动态数据不作家族识别硬条件

详见 SKILL.md 完整说明。

---

## 定位

**观察 + 评价**,不是审查 + 纠错。帮设计师发现"哪些地方不一样"+"从体验视角理解这种不一样的代价"。最终处置交给设计师和评审委员会。

---

## 调用方式

### Agent 调用
```
1. Read SKILL.md(主入口)
2. Read prompts/page-level-review.md(执行契约)
3. 输入截图 + business_line(人工声明)
4. Skill 输出观察报告(差异 + 严重度 + 建议)
```

### PE 模板
- `agent-pe-guide.md`(完整 system prompt + 调用示例 + 自检清单)

---

## 与京东 Design Wiki 的关系

- 双列卡 family DNA → Zone 4 各事业部业务组件继承
- 主站 ProductCard 必须遵守"商品家族"L1+L2 规约
- 跨 BG 双列卡冲突 → 走 horizontal/governance 评审

---

## 维护

- **专项组**:综合业务设计组(Shaka 主导)
- **review**:DS 维护组 + 评审委员会
- **更新频次**:每发现新基线 / 新规则 → 立即更新 Skill

---

## 待补事项

- references/jd-15-spec.md 空壳待注入官方 token
- 圈子视频卡、商品图文卡基础款等少数基线待补
- 真实跨 agent 验证(PE 模板已就位,待另一个 agent 独立跑过验证闭环)
