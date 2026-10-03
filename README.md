# French Musical B2 Learning Skill

面向 B1–B2 法语学习者，将用户提供的音乐剧歌词、对白和戏剧片段转化为可复习、可迁移的语言材料。默认中文讲解，法语释义和例句。

## 使用

将此目录放入支持 SKILL.md 的 AI 工具的技能目录。Codex 的默认个人目录为 `~/.codex/skills/french-musical-b2/`；此仓库目录也可作为开发与分发版本。

```text
使用 $french-musical-b2 分析下面的文本，重点关注 B2 口语，生成单词卡和知识卡。
范围：全部（也可指定行号、段落或角色）
Musical: 可选
Song: 可选
Character: 可选
Context: 可选

在此粘贴法语文本。
```

可以追加“输出 YAML”“导出 TSV”“只分析角色 A”或“详细分析全部有价值的内容”。没有背景信息也能分析；只有曲名时需提供文本。

## 交付内容

- 五类词汇/表达标签、重点词条统一字段及词族、搭配。
- 原文有证据的语法与戏剧语境说明。
- 明确标记的新编 B2 迁移例句。
- 有原文及分析项关联的单词卡、知识卡，支持 TSV 导出。

入口为 [SKILL.md](SKILL.md)，结构约定见 [output-contract.md](references/output-contract.md)，原创示例和行为验收见 [examples.md](references/examples.md)。

这是由宿主语言模型执行的 Skill，不是独立应用，也没有内置词频数据库。等级与频率默认是教学估计，不是官方逐词定级。示例为原创；用户输入的作品文本不属于本项目许可证的授权范围。

## 开源许可

项目文件采用 [MIT License](LICENSE)。
