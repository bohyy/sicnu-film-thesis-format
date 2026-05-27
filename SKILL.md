---
name: sicnu-film-thesis-format
description: >-
  Use when formatting, checking, or revising a Sichuan Normal University
  (四川师范大学/川师) graduate thesis for film, television, communication, drama
  and film studies, interactive film, documentary, or related 影传/戏剧与影视方向论文.
  Applies the 2026 Sichuan Normal University doctoral/master thesis writing and
  printing requirements, including page setup, fonts, line spacing,
  headers/footers, abstracts, table/figure captions, references, and notes.
  Enforces two local overrides: chapter headings use Chinese hierarchy such as
  第一章/第一节/一、/（一） rather than Arabic 1/1.1; footnote markers use
  circled-number superscripts such as ①②③, not image markers.
---

# 川师影传毕业论文格式

## Use This Skill For

- Formatting or auditing `.docx` theses for 四川师范大学 graduate submission.
- Converting an existing thesis into 川师 2026 版格式.
- Directly modifying a Word thesis into the correct format and saving a revised `.docx` copy.
- Checking headings, page setup, 摘要、目录、图表、脚注、参考文献、页眉页脚.
- Film/television/communication/drama/interactive-film theses where case titles, films, games, documentaries, platforms, and cited scholarship need consistent academic formatting.

Primary source: `assets/sicnu-2026-format-source.zip`. Condensed rules are in `references/format-rules.md`, `references/reference-format.md`, and `references/circled-footnote-style.md`.

## Non-Negotiable Overrides

These two instructions override the source template:

1. **章节标题不用阿拉伯数字。** Use Chinese thesis hierarchy:
   - `第一章 标题`
   - `第一节 标题`
   - `一、标题`
   - `（一）标题`
   - `1. 标题`
   Do not change these headings to `1`, `1.1`, `1.1.1`.

2. **脚注编号采用圈码上标，并在每页重新编号。** When creating or repairing footnotes, use Unicode circled-number superscripts such as `①②③`, not plain Arabic digits and not image markers. The visible style should match the user's sample:正文中为圈码上标, page-bottom footnote area separated by a horizontal line, and each footnote begins with the same circled number followed by the bibliographic source. Footnote numbering restarts from `①` on each page.

Everything else follows the 2026 川师 source files unless the user gives a newer college-specific rule.

## Core Formatting Rules

Read `references/format-rules.md` before doing a full thesis formatting pass. Essential rules:

- Paper: A4, double-sided printing expectation.
- Margins: top 30 mm, bottom 25 mm, left 25 mm, right 25 mm, gutter 10 mm; header 23 mm, footer 18 mm.
- Body: 小四号宋体, fixed 20 pt line spacing, first-line indent 2 Chinese characters.
- English/Roman text: Times New Roman unless a field requires another font.
- Heading fonts from source template, with Chinese numbering override:
  - Chapter: 三号黑体, new page, title occupies 2 lines.
  - Section: 四号黑体.
  - Third level: 小四号黑体.
  - Fourth level: 小四号楷体.
- Figure/table/formula numbering still follows source convention with Arabic chapter numbers when required: `图2.1`, `表2.1`, `(2.1)`.
- Figure captions go below figures; table captions go above tables.
- Captions: 五号黑体. Table text and figure legends: 小五号宋体. Table notes: 六号宋体.
- References: 五号宋体, placed after the正文 on a new page, following GB/T 7714-2015.
- Notes/footnotes: 小五号宋体, kept at the bottom of the same page under a footnote separator line. In this user's thesis, footnotes usually carry source/reference information; do not treat bibliographic footnotes as errors.

## Workflow

1. **Inspect the document first.**
   - Identify current headings, figures, tables, footnotes, references, page sections, and whether there are existing manual styles.
   - Preserve user-authored content and thesis titles unless the user asks for wording changes.
   - When asked to fix or format a document, create a revised output file instead of only giving advice.

2. **Apply structure before micro-formatting.**
   - Ensure order: cover, originality/use authorization, Chinese abstract, English abstract, 目录, 绪论/正文 chapters, 结论, 参考文献, 附录, 致谢, 在校期间科研成果 if present.
   - Do not rename headings unless asked. Convert only the numbering style if needed.

3. **Apply page and paragraph formatting.**
   - Set margins, headers/footers, page numbering, body font, 20 pt line spacing, and first-line indent.
   - Front matter page numbers use Roman numerals; body and back matter use Arabic numerals.

4. **Format figures and tables.**
   - Ensure each figure/table is referenced in text before or near where it appears.
   - Figure title below; table title above; use `图2.1`/`表2.1` style unless the user explicitly asks for another numbering system.
   - Prefer three-line tables for academic tables.

5. **Handle footnotes.**
   - Read `references/circled-footnote-style.md` when repairing or creating notes.
   - Preserve the user's convention shown in the screenshot:正文圈码上标 + 当页页脚横线 + 底部圈码文献条目.
   - Restart footnote numbering on every page: each page begins again with `①`.
   - Use circled-number markers: `①②③④⑤⑥⑦⑧⑨⑩`.
   - In正文, the marker should be compact superscript, placed immediately after the cited claim, author summary, quoted sentence, or punctuation.
   - In the footnote area, begin the note with the same circled marker, followed by the bibliographic source information.
   - Bibliographic footnotes should follow GB/T 7714 as closely as possible, e.g. `①李彬.互动影视中的任务系统与叙事意义建构[J].电视研究,2023(1):55-59.`
   - Keep bottom footnote entries aligned and readable; long entries may wrap with continuation text aligned after the marker.
   - Preserve Word automatic footnote linkage when possible; set footnote numbering restart to each page if using Word/OOXML. If exact圈码 appearance conflicts with automatic numbering, prioritize the visible圈码 style and document the limitation.

6. **Check references.**
   - Read `references/reference-format.md`.
   - Use either 顺序编码制 or 著者-出版年制 consistently. For Chinese film/TV theses, default to 顺序编码制 if the existing thesis already uses `[1]`.
   - Do not put uncited reading material into `参考文献`; if needed, put it in `附录` under `参考书目`.

7. **Validate and report.**
   - Confirm number of embedded images, figure/table captions, heading hierarchy, footnote count/style, and reference format consistency.
   - If visual rendering tools are unavailable, say so and provide structural validation results.

## 影传方向 Style Notes

- Chinese titles of films, documentaries, interactive films, games, TV programs, and creative works use `《》`.
- Foreign works may be written as `《Late Shift》` or `《黑镜：潘达斯奈基》（Black Mirror: Bandersnatch）`; keep one style consistent.
- Case analysis should not read like a project report. Tie examples back to narrative structure, audiovisual language, interaction mechanism, cultural communication, reception, or authorship.
- Avoid marketing language and over-emotional prose in final thesis formatting; keep academic tone.
