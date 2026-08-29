# Platform Product Manager — a Claude Skill

> A Claude Skill that packages the judgment of a seasoned B2B / Platform Product Manager.
> From layered architecture and PRDs to user journeys, event tracking, North Star metrics — and now, **generating operational dashboards directly**.

Built for product managers working on B2B / Enterprise SaaS platforms. Whether you're designing a new platform from zero to one, scaling an existing one from one to ten, or just trying to figure out what's actually broken — this Skill helps you think through the problem like a systems thinker.

There's no shortage of resources for consumer PMs. There's very little for **B2B / Platform PMs**. This Skill tries to fill that gap.

---

## Why use it

Most AI assistants answer product questions with something "correct but generic." This Skill is different — it encodes the actual **thinking discipline** of a platform PM:

- Every capability belongs to an architectural layer; a capability with no layer has no owner
- Every product decision should trace back to a North Star Metric
- Every deliverable (PRD, tracking plan, dashboard) is designed backwards from the question it needs to answer — not forwards from whatever data happens to be available

In short: it doesn't just hand you an answer. It helps turn "I have a feeling" into "I know."

---

## What it can do

| Scenario | What you get |
|---|---|
| **Platform architecture design / audit** | The five-layer model (Data / Logic / API / Application / Observability), with a capability-to-layer mapping table |
| **Writing PRDs** | A structured PRD template that includes the commonly-skipped QA regression impact and explicit out-of-scope reasoning |
| **Multi-role user journeys** | Cross-role journey maps that surface the silent failure points where one role blocks another |
| **0→1 / 1→10 strategy** | Two distinct thinking frameworks for each stage, plus a checkable checklist |
| **Event tracking & analytics** | Tracking design that works backwards from the question, standard event properties, North Star decomposition trees |
| **🆕 Operational dashboards / monitoring cockpits** | Generates a complete dashboard — three-tier information hierarchy, health signaling, and alert states |

---

## ✨ Latest update: operational dashboard generation

Added in `v2`. Building a data dashboard is one of the most common — and least systematically taught — tasks a platform PM gets handed.

This Skill can now generate a genuinely usable operational dashboard. It doesn't just "stack charts" — it first forces four questions: **who's the viewer, what's the single most important number, what does "something's wrong" look like, and what's the time granularity** — then builds a three-tier structure:

- **Tier 1 — Pulse**: core KPIs with period-over-period deltas and health colors, answering "is everything OK right now?"
- **Tier 2 — Trends**: line charts and comparison bars, answering "how did we get here?"
- **Tier 3 — Breakdown**: ranked tables and funnels, answering "where exactly is the problem?"

The generated dashboard always includes at least one metric in an alert state — a dashboard that's all green teaches you nothing about what "wrong" looks like.

---

## How to use it

### In Claude

1. Download `SKILL.md` from this repo
2. Drop it into your Claude Skills directory, or load it as a project custom instruction
3. Describe your platform product problem — the Skill triggers automatically

### Example prompts

```
Design an operational dashboard for a cross-border e-commerce SaaS platform,
for the ops lead to check every morning — it needs to surface at a glance
which creator category is losing engagement.
```

```
I'm building a multi-tenant B2B collaboration tool, currently at zero-to-one.
Help me think through what to prioritize at this stage and what to explicitly skip.
```

```
Write a PRD for adding a "guest" role. This change touches every existing
permission check — flag the QA regression risk explicitly.
```

---

## Who it's for

- B2B / Platform / Enterprise SaaS product managers
- PMs transitioning from consumer to B2B, or from platform PM to AI PM
- Indie builders / founders who want to systematize their own product judgment
- Anyone dealing with multi-tenant, multi-role, layered-architecture product problems

---

## Roadmap

This Skill is actively evolving. Planned next:

- [x] Operational dashboard / monitoring cockpit generation
- [ ] Pricing & packaging (feature gating, plan tier design)
- [ ] Prioritization frameworks (RICE / Kano / weighted scoring)
- [ ] Competitive analysis / feature parity teardown
- [ ] Fleshed-out `references/` template library

Open an issue if there's a capability you'd want prioritized.

---

## About the author

I'm Iris, a product manager transitioning from platform PM into AI PM. This Skill is my attempt to turn years of B2B product judgment, hard-won lessons, and frameworks into something reusable.

I share B2B / Platform PM thinking and this Skill's changelog on **https://www.irisluan.com/**

---

## License

MIT — use it freely, no need to credit. If it's useful to you, a ⭐ star is the best thanks.

<br>

---

<br>

# Platform Product Manager — 一个 Claude Skill

> 一个把「资深 B端 / Platform PM 的判断力」装进 Claude 的 Skill。
> 从架构分层、PRD、用户旅程，到埋点、北极星指标，再到**直接生成运营大盘**。

面向 B2B / Enterprise SaaS 场景的平台产品经理。无论你是从 0 到 1 设计一个新平台、把已有平台从 1 做到 10，还是想搞清楚"现在到底哪里出了问题"——这个 Skill 帮你像一个系统思考者那样拆解问题。

市面上给 C端 PM 的资源很多，给 **B端 / Platform PM** 的却很少。这个 Skill 想补上这个空缺。

---

## 为什么用它

大多数 AI 助手回答产品问题时，给的是"正确但通用"的答案。这个 Skill 不一样——它内置了一套 Platform PM 的**思维纪律**：

- 每个能力都归属于某一架构层，没有层归属的能力就是没有 owner 的能力
- 每个产品决策都要能追溯回北极星指标
- 每个交付物（PRD、埋点方案、大盘）都从"要回答什么问题"倒推，而不是从"手上有什么数据"正推

换句话说：它不只是给你答案，它帮你把"我感觉"变成"我知道"。

---

## 能做什么

| 场景 | 它给你什么 |
|---|---|
| **平台架构设计 / 审查** | 五层架构模型（数据 / 逻辑 / API / 应用 / 可观测），能力到层的映射表 |
| **写 PRD** | 结构化 PRD 模板，含常被忽略的 QA 回归影响、Out-of-scope 说明 |
| **多角色用户旅程** | 跨角色的旅程地图，专门标出"一个角色卡住另一个角色"的静默失败点 |
| **0→1 / 1→10 策略** | 两个阶段完全不同的思考框架 + 可勾选的 checklist |
| **埋点与分析** | 从问题倒推的事件设计、标准属性、北极星指标分解树 |
| **🆕 运营大盘 / 监控驾驶舱** | 直接生成一整张 dashboard（三层信息结构 + 健康度信号 + 预警状态） |

---

## ✨ 最新更新：运营大盘生成能力

`v2` 新增。B端 PM 最常接、却最少被系统化训练的一个活儿：做数据大盘。

这个 Skill 现在能直接帮你生成一张可用的运营驾驶舱。它不是"堆图表"，而是先逼你想清楚四件事——**给谁看、最重要的数字是什么、"出问题"长什么样、什么时间粒度**——再按三层信息结构搭建：

- **第一层 · 脉搏**：核心 KPI + 环比 + 健康色，回答"现在正常吗"
- **第二层 · 趋势**：折线与对比柱状，回答"怎么走到今天的"
- **第三层 · 拆解**：排行表与漏斗，回答"问题出在哪"

生成的大盘默认会包含一个"亮红灯"的指标——因为一个全绿的大盘，教不会你怎么看异常。

---

## 怎么用

### 在 Claude 里使用

1. 下载本仓库的 `SKILL.md`
2. 放进你的 Claude Skills 目录，或作为项目自定义指令加载
3. 描述你的平台产品问题，Skill 会自动触发

### 示例 prompt

```
帮我给一个「跨境电商 SaaS 平台」设计运营大盘，
给运营负责人每天早上看，要能一眼发现哪个类目的达人在掉量。
```

```
我在做一个多租户的 B端协作工具，现在处于 0→1 阶段，
帮我理一下这个阶段该做什么、不该做什么。
```

```
帮我写一个「新增访客角色」功能的 PRD，
这个改动会影响所有已有的权限校验，注意标出 QA 回归风险。
```

---

## 适合谁

- B端 / Platform / Enterprise SaaS 产品经理
- 从 C端转 B端、或从平台 PM 转 AI PM 的人
- 想系统化自己产品判断力的独立开发者 / 创业者
- 任何要处理多租户、多角色、分层架构产品问题的人

---

## 路线图

这个 Skill 在持续迭代。已规划的方向：

- [x] 运营大盘 / 监控驾驶舱生成
- [ ] 定价与打包（feature gating、plan tier 设计）
- [ ] 需求优先级框架（RICE / Kano / weighted scoring）
- [ ] 竞品对标 / feature parity 分析
- [ ] 补全 `references/` 深度模板库

欢迎提 Issue 告诉我你最想要哪个能力。

---

## 关于作者

我是 Iris，一个正在从平台 PM 转向 AI PM 的产品经理。这个 Skill 是我把自己这些年做 B端产品的判断框架、踩坑记录、方法论整理出来的产物。

我在个人网站上持续分享 B端 / Platform PM 的实战思考和这个 Skill 的迭代日志，欢迎来找我玩：**https://www.irisluan.com/**

---

## License

MIT — 随便用，改了也不用告诉我。如果对你有帮助，给个 ⭐ Star 就是最好的支持。
