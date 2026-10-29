# 批改网（Pigai）五维评分规则与配额

批改网先看第六节的前置过滤，再按一到五节给分。所有阈值按最严标准执行。

## 一、内容组织：显性要点覆盖

系统提取题干动词指令（compare / analyze / propose / discuss 等），构建「动作—对象」关系图谱，再扫描学生文本是否有匹配的主谓宾小句。

- 判定三档：**显性达成**（满分项）／**隐性达成**（按 0.5 权重计分）／**未达成**（直接扣分）。
- 隐性达成的典型：用代词指代但没写出对象名称。例如题干要求 compare two policies，就必须出现含两个政策名称 + 比较动词的完整小句，写 they / these policies 只算一半。
- 重复表述同一要点**不视为补充**，不会加分。

对策：每条题干指令配一句主谓宾完整的显性小句，把专有名词、数据、机构名原样写进去。

## 二、词汇语法：准确性、多样性、学术适配度

双通道校验——基础语法 + CEFR / AWL 词级。

- 全文词形还原后去重，统计 B2 及以上（含 AWL）词汇占比，**低于 18% 触发「词汇贫乏」预警**。
- 高频基础词替换为 AWL 认证词（very→exceptionally，good→effective，think→contend / consider），每处有效替换加 0.15–0.22 分。
- 语法扣分单价：主谓不一致 -0.35／处，冠词缺失或多余 -0.18／处，非谓语动词逻辑主语错位 -0.41／处；**累计 5 处以上触发语法档位下调**。

对策：

- 主动铺设 AWL 词：mechanism、dissemination、rigorous、amplify、convert、diffusion、horizontal、mutual、transform、motivation、sustainability、collective、institutions、cultivate、expertise、ethics、constitute、demonstration、persistent、infrastructure、accelerate、transition、stewardship、commit、coexist。目标占比 25% 左右。
- 主动替换基础词：think→consider / contend / hold；very→exceptionally / remarkably；good→effective / genuine；people→individuals / citizens；only→solely / merely；because→in that / for the reason that（少量使用）。

## 三、篇章结构：三级连接词配额

系统要求连接成分呈「主层—次层—微层」三级分布，并对位置与频次严格约束，**单一类型过载导致逻辑分清零**。

| 层级 | 代表词 | 规则 |
|---|---|---|
| 主层 | Consequently / Thus / Accordingly | 只能出现在**每段首句的句首**；全篇**最多 3 次**，超量部分无效 |
| 次层 | 因果 in light of this；转折 notwithstanding；递进 furthermore / moreover | 每段**跨子类混用**，同类每个子类限 1 次；同段重复判定为机械堆砌 |
| 微层 | by contrast / on the contrary / in parallel | 必须**紧邻**所修饰的分句，偏离超过 2 个词距不计分 |

安全配位（五段式标准方案）：

- 主层：P2 `Consequently,`／P3 `Thus,`／P4 `Accordingly,` —— 恰好 3 次，均在段首。
- 次层：P2 用一个转折（whereas 作连词）／P3 用 `In light of this`（因果）／P4 用 `Notwithstanding`（让步）。
- 微层：P3 句中插入 `in parallel` 且紧贴所饰分句（如 `cultivate, in parallel, both A and B`）。
- `therefore`、`on no account can we` 这类成分只放句中，**不要放段首**，避免被判超量。

## 四、技术实现：错误定位与反馈映射

每个扣分项绑定唯一字符区间，因此修改要精确到 token：

- 语法错误标注精确到单词（如把 go 标为动词原形误用，而非整句标红）→ 修改时**最小化改动**，不要整句重写。
- 词汇建议给 3 个 AWL 候选词，按词频降序，第一个是上下文适配度最高者 → 优先采纳首选项。
- 结构反馈附带修改范例：若检测到段首缺主层连接词，按示例插入 `Thus,` 并保持与后接主句的逻辑绑定。

## 五、相似度与规范性：前置硬阈值

内容评分之前先跑两项过滤，任一超标即返回提示而非分数：

- MinHash + LSH 比对近 3 年批改网语料库，**相似度 ≥32% 冻结提交**，提示「文本疑似非原创，请重写核心段落」。
- 标点错误率 > 每百字 2.7 处（英文句号后缺空格、中英引号混用等），或拼写错误率 > 1.3%，跳过全部维度评分，只返回「格式不规范，无法进入内容评估」。

对策：写完必查句点后空格、全程英文标点；同一句式/排比不跨话题复用。

## 六、评语反查表

批改网评语是高度压缩的信号，按表反推修改动作：

| 常见评语 | 真实含义 | 修改动作 |
|---|---|---|
| 句法知识掌握不够好，可适当增加从句使用 | 简单句占比过高，复合句不足 | 补定语从句、宾语从句、状语从句、同位语从句，目标是每段至少 2 个从句 |
| 采用了简单的衔接手法 | 只有主层连接词，缺少次层/微层与从句内衔接 | 按第三节补配额，并用 which / because / whereas / only if / as long as 做句内衔接 |
| 内容相关度低 | 抒情比喻多、显性扣题句少 | 删纯修辞排比，补题干关键词句：mechanism / drives youth / shoulder responsibility / sustainable development / dignity 等 |
| 词汇基础扎实 | 该维度已达标 | 维持，不必再加难词，避免拼写风险 |
