# 原创示例与验收场景

本文件的法语短文为原创教学语料，不属于任何真实音乐剧。示例说明决策，不要求运行时固定输出这些项目。

## 输入

```text
A : Bien que la ville soit silencieuse, je veux faire face à mes doutes.
B : Pourtant, tu as pris conscience de nos difficultés.
A : Si nous avions plus de temps, nous pourrions défendre ce projet.
A : Ô nuit, emporte mes regrets !
```

无作品背景。行号依次 L1–L4。

## 示例分析摘录

- E1 faire face à + nom：D/C，面对、应对。原文证据 L1：`je veux faire face à mes doutes`。中性语域、迁移价值高；难度 B1–B2（教学估计）。原创迁移：`Les petites entreprises doivent faire face à la hausse des coûts.`（小企业必须应对成本上涨。）不单列 face 的基础义来替代词块。
- V1 pourtant：B，然而、可是。证据 L2：`Pourtant, tu as pris conscience de nos difficultés.`；表达与前文预期相反的信息。常见程度 high（估计），不能据本段出现一次推导频率。
- E2 prendre conscience de + nom：C/D，意识到。证据 L2 中 `tu as pris conscience de nos difficultés`，surface form 为 as pris conscience de。原创迁移：`Cette expérience m'a permis de prendre conscience de l'importance du dialogue.`。可拓展 prendre conscience que + proposition，并按实际句义选择语气；不要写成 prendre conscience de que。
- G1 bien que + subjonctif：L1 的 soit 为 être 的虚拟式现在时；让步，即承认一种情况仍坚持后面的立场。原创迁移：`Bien que cette solution soit intéressante, elle présente certaines limites.`（尽管这一方案有吸引力，它仍有一些局限。）此句是新编例句，不是续写用户原文。
- G2 si + imparfait，主句 conditionnel présent：L3 avions / pourrions，用于现在或未来的假设；此处不写 si nous aurions。原创迁移：`Si la ville investissait davantage, les habitants pourraient se déplacer plus facilement.`
- E3 Ô nuit：E，文学呼语。L4 将夜拟人化；可描述为向夜倾诉，但不能据此断定角色失恋或死亡。可用于分析文学语气，不推荐作为 B2 议论文开头。

以上仅为分析摘录；实际完整输出按 output-contract.md 补齐选中项目的统一字段。

## 卡片示例

| ID | 类型 | 正面 | 背面 | 关联项 | 标签 |
| --- | --- | --- | --- | --- | --- |
| C1 | 单词卡 | pourtant 表示哪一种逻辑关系？ | 转折或反预期：“然而、可是”。 | V1 | french musical b2 vocabulary |
| C2 | 知识卡 | 补介词：faire face ___ la hausse des coûts | à；faire face à + nom，面对/应对。此句为原创迁移语境。 | E1 | french musical b2 expression |
| C3 | 知识卡 | 在 bien que 引导的让步从句中，être 如何填入：Bien que cette solution ___ intéressante… | soit，虚拟式现在时；bien que 引导让步从句。 | G1 | french musical b2 grammar |

## 行为验收

1. 用上述输入要求“只分析 B”：仅 L2 作为提取证据；可以参考上下文，但不检测 L1 的虚拟式或 L3 的条件式。
2. 重复 L1 三次：不生成三套相同词条或卡片；保留多个出现位置。
3. 输入 `Je chante. Tu danses.`：可以说明主要为基础表达，不能为了凑 B2 项目引入原文不存在的 revendiquer 或虚拟式。
4. 输入 `Bien qu'il…`：标记截断；可解释 bien que 的通常用法，但不能声称实际检测到某个未出现的变位。
5. 仅输入“分析 Belle”：请求片段，不虚构歌词或默认角色。
6. 无背景输入文学呼语：使用语境假设，不补充未经提供的人物身份或剧情。
7. 同时请求 TSV：核对每行六列、无字段内换行、重音保留、所有 item_ids 可追溯；表头不可成为一张卡片。
8. 输入只有某词的变位：按词义还原原形，但 example 保留输入原样，不把词典形式当引文。

## 核验资源

- [France Éducation international：DELF B2 考生手册](https://www.france-education-international.fr/document/manuel-candidat-delf-B2)：用于理解论证与表达的考试目标，不用于声称某词是官方 B2 词汇。
- [法兰西学院词典：conscience](https://www.dictionnaire-academie.fr/article/A9C3663)：核验 prendre conscience de 的意义和构式。
- [加拿大政府语言门户：prendre conscience que](https://nos-langues.canada.ca/fr/cles-de-la-redaction/conscience-prendre-conscience-que)：需要核验 que 补语用法时参考。
