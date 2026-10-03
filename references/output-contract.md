# 输出约定

默认可读 Markdown；用户要求 YAML 时使用下列字段。字段语义在两种格式中保持一致。未知值为 null 或 unknown，空列表为 []，不要为了填模板编造信息。所有等级、频率默认 estimated；有核验依据时附 source URL，但来源未提供的结论仍是估计。

## 顶层

结构化文档包含 metadata、vocabulary、expressions、grammar、context_notes、transfer、cards。metadata 记录用户给出的 musical/song/character/context、实际 scope、带 ID 的原始行、完成覆盖范围、level_basis 和 frequency_basis。缺省背景用 null。

## 词汇

以下为字段约定示例，不是待分析文本。每个重点词汇都应包含这些字段；example 必须是当前用户文本的原样摘录，不能使用示例填充。

```yaml
id: V1
word: renoncer
surface_forms: [renoncer]
categories: [A, D]
part_of_speech: verb
gender_number: null
construction: "renoncer à + nom / infinitif"
level: B1–B2
level_basis: estimated
level_confidence: medium
level_reason: "放弃行动或目标的表达具有跨主题学习价值；此范围为教学估计。"
frequency: medium
frequency_basis: estimated
importance: high
selection_reason: "可用于讨论选择、目标和妥协。"
meaning:
  zh: 放弃；不再坚持
definition_fr: "Décider de ne plus poursuivre un projet ou de ne pas faire quelque chose."
source_refs: [L1]
example: "Je ne veux pas renoncer à notre projet."
translation: "我不想放弃我们的计划。"
collocations:
  - expression: "renoncer à un projet"
    origin: source
  - expression: "renoncer à faire quelque chose"
    origin: extension
word_family:
  - word: renoncement
    note_zh: "阳性名词，强调放弃的行为或态度。"
register: standard
musical_context: "说话者拒绝放弃共同计划；仅据本句，无法断定人物背景。"
transferable_expression:
  template: "Il ne faut pas renoncer à…"
  example_fr: "Il ne faut pas renoncer à améliorer les transports publics."
  translation_zh: "不应放弃改善公共交通。"
  origin: original
  use: "口语或写作中坚持建议；注意情境是否需要更委婉的语气。"
sources: []
```

origin: source 表示出现在原文（搭配可还原形并关联原句）；extension 为拓展搭配；original 为新编例句。source_refs 始终指实际输入行。可用 V/E/G 编号分别表示词汇、表达、语法。

## 表达与语法

expressions 每项字段：id、expression、categories、structures（含补语类型）、meaning_zh、register、source_refs、source_quote、context_meaning、original_example_fr、translation_zh、b2_template、usage_limits、related_ids。

grammar 每项字段：id、structure、source_refs、source_quote、observed_form、trigger、function_zh、explanation_zh、common_error、original_example_fr、translation_zh、b2_use。语法估计等级可选；不要自动把每个语法点称为 B2 独有。

context_notes 每项关联 source_refs，区分 literal_meaning、contextual_reading、certainty、register、neutral_rewrite。没有合理的现代等价表达时说明限制，不强行改写。

transfer 每项关联已有 V/E/G 的 ID，包含 communicative_function、template_fr、original_example_fr、translation_zh 和 register。例句使用教育、环境、文化、工作等通用议题，语义自然，避免空泛套话。

## 单词卡与知识卡

默认表格列：ID、类型、正面、背面、关联项、标签。单词卡测试词义或配价；知识卡测试一种表达结构或语法规则。卡片正面需提供足够语境以消除多义，但不要泄露目标答案。背面包含答案、简短说明和必要例句。

用户要求导出时提供 UTF-8 TSV 文件（无文件工具则提供 TSV 代码块），列固定为：

```text
card_id	card_type	front	back	item_ids	tags
```

每卡一行，字段内 Tab 和换行转换为空格，保留法语重音和撇号。标签空格分隔，使用 french musical b2 及 vocabulary/expression/grammar 等；等级估计不必作为绝对标签。说明首行为列名，导入时按目标软件映射字段并排除表头；不声称 TSV 是 .apkg，也不自动同步账号。
