# 圈码脚注上标

The required footnote style is a textual circled-number superscript, not an image. It should match the user's sample: circled superscript citation markers in正文 and corresponding bibliographic footnotes at the bottom of the same page.

## Visual Rule

- In正文, use compact superscript circled-number markers: `①②③④⑤⑥⑦⑧⑨⑩`.
- Place the marker immediately after the cited claim, author summary, quoted sentence, or relevant punctuation, as in: `……交互机制相关。⑥`
- At the bottom of the same page, use the Word footnote area/separator line style. The footnote begins with the matching circled number and then the source note.
- Footnote numbering restarts on every page. Each page begins again with `①`, then `②`, `③`, and so on.
- Footnote text: 小五号宋体.
- In this user's thesis, footnotes generally correspond to references/sources. Preserve that convention.
- Do not leave orphan markers: every正文 circled number must have a matching bottom-of-page footnote on the same page.

## Number Characters

Use Unicode circled numbers where possible:

`① ② ③ ④ ⑤ ⑥ ⑦ ⑧ ⑨ ⑩ ⑪ ⑫ ⑬ ⑭ ⑮ ⑯ ⑰ ⑱ ⑲ ⑳`

If there are more than 20 footnotes, continue with available Unicode circled numbers where font support is reliable, or consider reducing notes. Academic theses should avoid excessive footnotes.

## DOCX Implementation Guidance

- Preserve Word footnote linkage when possible.
- If editing OOXML, set footnote numbering restart behavior to each page where supported by the document settings/section properties.
- If using `python-docx`, direct footnote editing requires OOXML-level work in `word/footnotes.xml` and `word/document.xml`.
- For a pragmatic visible-format repair, replace visible footnote references with superscript circled digits and ensure the footnote paragraph begins with the same circled digit.
- Apply Songti/宋体 to Chinese note text; set the marker itself as superscript in正文.
- Bibliographic footnote examples:
  - `①李彬.互动影视中的任务系统与叙事意义建构[J].电视研究,2023(1):55-59.`
  - `②王建.互动影视的沉浸体验与共情机制研究[J].当代电视,2022(9):70-75.`
  - `③王璐璐.网络互动剧的受众认知研究[D].贵州大学,2022.`
- If a footnote is bibliographic, format it close to GB/T 7714 and keep it consistent with the final `参考文献` list when both are used.
