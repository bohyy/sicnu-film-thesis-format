# 川师影传毕业论文格式 Skill

这是一只“守格式的小狮子”。

它不替你写论文的观点，也不替你决定章节内容；它负责守住四川师范大学研究生论文格式的边界，并能把不规范的文档修改成正确格式：页边距、字体、行距、章节层级、页眉页脚、图表编号、交叉引用、圈码脚注、参考文献格式。对于戏剧与影视、广播电视、电影学、传播学、互动影视、纪录片等影传方向论文，它还会额外照看作品名、案例名和学术表达的规范性。

## 它是什么

`sicnu-film-thesis-format` 是一个 Codex skill，用来帮助 agent 按照四川师范大学 2026 版博士、硕士学位论文撰写打印要求处理影传方向毕业论文。它既可以做格式审查，也可以直接对 `.docx` 执行套版、修正和导出。

它内置了三类材料：

- `SKILL.md`：agent 每次真正使用 skill 时优先阅读的核心规则。
- `references/`：更详细的格式、参考文献、圈码脚注规则。
- `assets/sicnu-2026-format-source.zip`：川师 2026 版原始规范压缩包，用于追溯。

## 小狮子守哪几道门

| 守门处 | 它会检查和修改什么 |
|---|---|
| 章节 | 使用 `第一章`、`第一节`、`一、`、`（一）`，不把章节改成 `1 / 1.1 / 1.1.1` |
| 正文 | 小四号宋体，固定 20 磅行距，首行缩进 2 字符 |
| 页面 | A4，川师页边距、前置部分与正文页码分开 |
| 页眉页脚 | 摘要页起设置页眉；左侧为学校论文标识，右侧为章名；页码分区连续 |
| 图表 | 图题在图下，表题在表上，编号如 `图2.1`、`表2.1` |
| 交叉引用 | 检查并修正文中“如图2.1所示”“见表2.1”等引用与真实编号一致 |
| 脚注 | 正文用 `①②③` 圈码上标；每页重新从 `①` 编号；同页页脚列出对应文献 |
| 参考文献 | 按 GB/T 7714-2015 靠拢，和脚注文献信息保持一致 |
| 影传文本 | 作品名用书名号，案例分析回到叙事、视听、交互、传播、接受等学术问题 |

## 怎么使用

把这个仓库放到 Codex 的 skills 目录中：

```bash
git clone https://github.com/bohyy/sicnu-film-thesis-format.git ~/.codex/skills/sicnu-film-thesis-format
```

之后在对话里直接说：

```text
使用 sicnu-film-thesis-format skill，帮我把这篇论文按川师影传毕业论文格式排版。
```

也可以说得更自然：

```text
用川师影传毕业论文格式 skill 检查这个 docx：章节不要改成阿拉伯数字，脚注用①②③圈码上标，每页重新编号。
```

如果你要它直接修改文档：

```text
使用 sicnu-film-thesis-format skill，把这个 Word 论文修改成川师正确格式，并另存为新版 docx。
```

如果你只想查某一项：

```text
用 sicnu-film-thesis-format skill 检查我的脚注和参考文献是否对应。
```

```text
用 sicnu-film-thesis-format skill 检查第二章的图表编号和标题格式。
```

## 一行接入其他 Agent

如果对方 agent 不能原生识别 Codex skill，可以把这个仓库当作“项目规则包”接进去。

复制给任何 agent 的一句话：

```text
请先阅读 https://github.com/bohyy/sicnu-film-thesis-format 中的 SKILL.md，并把它作为本次川师影传毕业论文排版任务的最高优先级规则；需要处理脚注、参考文献、页眉或交叉引用时，再读取 references/ 下的对应规则。
```

给 Claude Code 的项目级一行命令：

```bash
mkdir -p .agent-skills && [ -d .agent-skills/sicnu-film-thesis-format ] || git clone --depth 1 https://github.com/bohyy/sicnu-film-thesis-format.git .agent-skills/sicnu-film-thesis-format; printf '\n## 川师影传毕业论文格式\nWhen editing or formatting this thesis, read .agent-skills/sicnu-film-thesis-format/SKILL.md first. Use it to modify the DOCX into the correct SICNU format, including headers, cross-references, circled footnotes, figures/tables, and GB/T 7714 references.\n' >> CLAUDE.md
```

给 Hermes / OpenClaw / OpenCode / 其他支持 `AGENTS.md` 的 agent：

```bash
mkdir -p .agent-skills && [ -d .agent-skills/sicnu-film-thesis-format ] || git clone --depth 1 https://github.com/bohyy/sicnu-film-thesis-format.git .agent-skills/sicnu-film-thesis-format; printf '\n## 川师影传毕业论文格式\nWhen editing or formatting this thesis, read .agent-skills/sicnu-film-thesis-format/SKILL.md first. Use it to modify the DOCX into the correct SICNU format, including headers, cross-references, circled footnotes, figures/tables, and GB/T 7714 references.\n' >> AGENTS.md
```

## 四步教程

<table>
  <tr>
    <td><img src="assets/tutorial/01-install-skill.png" alt="步骤一：安装 Skill"></td>
    <td><img src="assets/tutorial/02-call-skill.png" alt="步骤二：调用 Skill"></td>
  </tr>
  <tr>
    <td><img src="assets/tutorial/03-fix-format.png" alt="步骤三：修改成正确格式"></td>
    <td><img src="assets/tutorial/04-fix-footnotes.png" alt="步骤四：修正脚注与文献"></td>
  </tr>
</table>

这四步对应的实际工作是：先安装 skill，再让 agent 调用它；随后由 agent 按川师规则修改论文格式，最后校对页眉、交叉引用、每页重新编号的圈码脚注、页脚文献和文末参考文献的一致性。

## 不同 agent 怎么学习这个 skill

### Codex

Codex 会根据 skill 描述自动触发。触发后应按这个顺序学习：

1. 先读 `SKILL.md`，确定总规则和强制覆盖项。
2. 全文排版时读 `references/format-rules.md`。
3. 处理脚注时读 `references/circled-footnote-style.md`。
4. 处理参考文献时读 `references/reference-format.md`。
5. 如果规则冲突，以用户补充规则优先，其次以 `SKILL.md` 的 Non-Negotiable Overrides 优先。

### Claude、ChatGPT 或其他通用 agent

如果没有原生 skill 系统，可以把仓库作为“项目规则文档”喂给 agent：

```text
请先阅读这个仓库中的 SKILL.md，并把它作为本次论文排版任务的最高优先级规则。
当处理脚注时，再阅读 references/circled-footnote-style.md。
当处理参考文献时，再阅读 references/reference-format.md。
不要把章节标题改成阿拉伯数字。
```

### Cursor、Windsurf、IDE agent

把本仓库放进项目目录，例如：

```text
docs/skills/sicnu-film-thesis-format/
```

然后在 agent 规则里写：

```text
When editing the thesis DOCX or Markdown, follow docs/skills/sicnu-film-thesis-format/SKILL.md.
Load reference files only when the task touches formatting, footnotes, or bibliography.
```

### RAG / 知识库型 agent

建议索引这些文本文件：

- `SKILL.md`
- `references/format-rules.md`
- `references/circled-footnote-style.md`
- `references/reference-format.md`

不建议把 `assets/sicnu-2026-format-source.zip` 直接拆成大量碎片加入知识库，除非需要逐条追溯原始学校文件。

## 文件结构

```text
sicnu-film-thesis-format/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── assets/
│   ├── sicnu-2026-format-source.zip
│   └── tutorial/
│       ├── 01-install-skill.png
│       ├── 02-call-skill.png
│       ├── 03-fix-format.png
│       └── 04-fix-footnotes.png
└── references/
    ├── circled-footnote-style.md
    ├── format-rules.md
    └── reference-format.md
```

## 一句话记忆

这只小狮子做的事很简单：不让论文跑偏，不让格式散架，不让页眉、交叉引用、脚注和参考文献失联。
