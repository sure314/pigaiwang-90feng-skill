---
name: english-essay-pigai
description: 撰写面向批改网（Pigai / 句酷批改）评分体系的中文命题英语应试作文。当用户给出中文材料（社会热点、青年担当、文化现象、科技、环保、老龄化等话题）、字数要求（如 300-800 词）并要求写成英语作文时使用；也适用于用户贴回批改网批改报告、要求按评语修改并提高句法/衔接/内容相关度分数时。内置十项高级修辞模板、三级连接词结构、AWL 词汇策略、高分短语库、批改网实测雷区清单与两篇高分范文。
agent_created: true
---

# 批改网高分英语作文写作法

## 目的

把一段中文命题材料，写成**同时满足三套标准**的应试英语作文：

1. 用户指定的修辞/句型要求（见 `references/rhetorical-devices.md`）；
2. 批改网五个评分维度的机器判定规则（见 `references/pigai-scoring.md`）；
3. 高分万能短语的自然融入，**但不硬塞**（见 `references/high-score-phrases.md`）。

交付形态：一段可直接复制进批改网的**纯英文正文**（不含任何中文与标注），外加一份给用户看的中文说明（修辞落点表、连接词配位表、短语清单）。

## 何时使用

- 用户发来中文材料 + 「以……为题写一篇 XXX 词的英语作文」。
- 用户说「要求如上」「同样要求」——沿用上一次框架，不要重新设计。
- 用户贴回批改网批改报告/评语，要求修改、改语法标记、提句法与衔接分。

## 工作流

### 第 0 步：确认沿用项

用户说「要求如上」时，先读本 skill 的 references，沿用既有框架。默认沿用项：
十项修辞全部覆盖、三级连接词配位、12-16 个短语自然融入、词数落在 520-620。

### 第 1 步：拆解题干动词指令 → 显性动作-对象图谱

批改网靠「主谓宾结构」判定要点覆盖，**用代词隐性指代只算 0.5 权重**。每条题目指令都要在正文配一个**完整小句**，把对象名称写出来。

| 题干指令 | 必须出现的显性小句 |
|---|---|
| 剖析传播/运行机理 | `the mechanism through which … deserves rigorous analysis` + 一句点名具体机制的谓语 |
| 青年参与动力 | `it is worth examining what drives young people to …` |
| 展望……意义 | `the significance of this phenomenon extends far beyond …` / `… will accelerate the transition toward …` |
| 你如何参与 | 第一人称身份句：`I am a learner of … , a volunteer who … , and a communicator who …` |
| 引数据 | `according to <机构名>, <年份> witnessed a … increase in …` |

数据、国别、机构名必须原样写进句子，不能降格为 "these countries"。

### 第 2 步：五段式骨架

| 段 | 功能 | 必须包含 |
|---|---|---|
| P1 | 现象 + 数据 + 论点 | 一项比较级表最高级修辞（Nothing is more…）+ 数据宾语从句 |
| P2 | 分析机理 | 主层 `Consequently,` + 机制显性句 + 三个国别/案例例证 |
| P3 | 青年动力 + 教育/制度支撑 | 主层 `Thus,` + 次层因果 + 微层短语 |
| P4 | 意义展望 | 主层 `Accordingly,` + 次层让步 + 价值升华 |
| P5 | 个人行动 + 收束 | 否定前置 + 三个身份名词 + 结尾升华 |

标题统一用 `<Topic>, Youth Responsibility, and <Vision>` 三段式。

### 第 3 步：铺设「主层—次层—微层」三级连接

严格按 `references/pigai-scoring.md` 第三节的配额。最容易翻车的三条：

1. **主层**（Consequently / Thus / Accordingly）只出现在**段首句句首**，全篇**恰好 3 次**。
2. **次层**同一段内不可同子类重复：因果、转折、递进各占 1 次，跨段轮换子类。
3. **微层**（by contrast / in parallel 等）必须**紧邻**所修饰分句，中间插入不超过 2 个词。

`therefore` 只放句中（如 `I therefore spare no effort to …`），不触发段首规则。

### 第 4 步：嵌入十项修辞（每项至少 1 处）

逐项对照 `references/rhetorical-devices.md`。标准配方：

- 名词化：身份三连 `I am a learner of … , a volunteer who … , a communicator who …` + `deserves rigorous analysis`
- 连续介词：`from <A> to <B>` 套双层名词短语（如 `from the design of X to the art of Y`）
- 比较级表最高级：首段 `Nothing is more <adj> of <noun> than …` + 收尾段 `no mission is more worthy of youth than …`
- `not … enough`：`Yet X alone is not enough, because it is not rigorous enough to …, nor strong enough to …`
- `not so much A as B`：放在机理段的核心判断句
- `can't / never … too`：`one can't be too careful/patient when …`
- 部分否定 + 双重否定同句：`Not every young person is …, yet there is hardly anyone who doesn't …`
- 否定前置：`I don't consider <noun> a sufficient answer.`
- 定语后置：`the illumination of <X> through <Y>`、`the harmony between A and B`、`people aged 60 and above`

### 第 5 步：短语清单自然融入

从 `references/high-score-phrases.md` 挑 12-16 个契合语境的短语。
取舍标准：删掉它句子仍成立、但加上更地道 → 留；删掉它句子塌了 → 说明在硬撑，删。

### 第 6 步：语法自查（批改网最贵扣分项）

扣分单价：主谓一致 -0.35、冠词 -0.18、非谓语逻辑主语错位 -0.41，**累计 5 处以上触发语法档位下调**。

- 并列主语 + 复数动词常被误报 → 换 `constitute`，或改 `every A and every B is …`。
- 落笔前逐条核对 `references/pigai-known-fixes.md` 中已被实测标红的结构。
- 标点：句点后必须有空格；全程英文标点，禁中文引号/书名号混用；拼写错误率控制在 1.3% 以下。

### 第 7 步：字数与相似度

- 指定 300-800 词时，写 **520-620 词** 最稳。
- 相似度 ≥32% 会冻结提交：同一意象/排比句式不要跨话题原样复用（如 "masthead / morning sun / baby" 三联比喻只用一次）。

### 第 8 步：若用户提供批改报告

逐条对应处理：
「句法知识不够好」→ 增补各类从句（定语/宾语/状语/同位语各若干）；
「衔接手法简单」→ 增加从句内部衔接与主层之外连接层级；
「内容相关度低」→ 删减纯抒情比喻，补显性扣题句（mechanism / drives youth / shoulder responsibility / sustainable development 等题干关键词）。

## 输出格式

1. 先给**纯英文正文**（标题 + 5 段），不含中文与标注，便于整段复制进批改网。
2. 另起一份**中文说明**：词数、十项修辞落点表、三级连接词配位表、短语清单、本轮修复项（若贴了报告）。
3. 结尾提示可继续迭代：改个人事例、压词数、二改批改标记。

## 参考资源

- `references/rhetorical-devices.md` — 十项修辞：句型模板、母语负迁移提示、例句
- `references/pigai-scoring.md` — 批改网五维评分细则与计数阈值
- `references/high-score-phrases.md` — 30 个万能高分短语 + 适配建议
- `references/pigai-known-fixes.md` — 实测被标红的结构与替换方案
- `assets/sample-essays.md` — 两篇已交付高分范文（绿色科技、银龄关怀），作为句式与节奏参照
