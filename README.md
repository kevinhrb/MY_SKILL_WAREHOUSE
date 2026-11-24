# MY_SKILL_WAREHOUSE

个人 skill 仓库。每个 skill 是一个独立目录，内含 `SKILL.md`（YAML frontmatter + 正文说明），可直接放入 agent 的 skills 目录使用。

## 索引

| Skill | 用途 | 适用 |
|---|---|---|
| [`cn-academic-docx`](skills/cn-academic-docx/SKILL.md) | 中文技术/学术文档的排版与写作规范，含宋体小四、1.5 倍行距、首行缩进、OMML 公式、三线表、数据不完整时的非防御性写法 | 实验报告、课程大作业、课程论文、项目技术报告 |

## 安装

把对应目录整体复制到 skills 根目录下即可，目录名与 `name` 字段保持一致：

```
<skills-root>/
└── cn-academic-docx/
    └── SKILL.md
```

部分 agent 只扫描一层目录，此时也可平铺为 `<skills-root>/cn-academic-docx.md`。

## cn-academic-docx 能解决什么

- **版式合规**：正文宋体小四、1.5 倍行距、首行缩进 2 字符；章标题四号加粗、小节标题小四加粗；表格、图题、表注各有定规，并给出对应的 OOXML 写法（`w:sz=24`、`line=360`、`firstLineChars=200`、`w:eastAsia`）。
- **结构规范**：实验报告（北航模板骨架）与课程论文两套骨架，附章节合并规则。
- **公式可编辑**：坚持 OMML / LaTeX 转出的真公式，禁止公式截图；给出 python-docx 注入 OMML 的最小可用代码。
- **数据不完整也写成完成稿**：先定口径再算数、记录值只当实测、缺失项按判据归零、禁用"待补/需核实/数据不足"一类防御性表述，并附改写对照表。
- **可落地**：python-docx 的样式、表格、图片裁剪、分页控制配方，以及交付前自检清单和反模式清单。

## 约定

- 分支：`main`。
- 新增 skill 请在 README 索引表中补一行。
- 只收录可直接执行的规范，不收录空泛的写作建议。
