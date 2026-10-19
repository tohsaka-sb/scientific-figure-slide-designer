# Scientific Figure & Slide Designer

A reusable Codex/agent skill for creating **scientifically accurate, presentation-ready research figures and editable PowerPoint slides**, based on iterative preferences developed during a multi-agent memory thesis presentation.

## Key features

- Research-paper-style method figures with coherent icons, panels, and semantic arrows
- Side-by-side **like-for-like** comparisons (e.g. independent local memory vs. shared memory)
- Wide, balanced 16:9 layouts instead of unnecessarily tall stacks
- Equal support for **Chinese (zh-CN)**, **English (en)**, and intentionally bilingual (zh-CN + en) research figures
- Editable PPTX based on an uploaded institutional template
- True transparent-background PNG exports and visual QA
- Research workflows, evidence verification diagrams, evaluation summaries, timelines

## Language modes

| Mode | How to request it | Expected output |
|---|---|---|
| 中文 / zh-CN | “绘制中文版；所有主要文字为中文” | Chinese titles, blocks and captions; preserve standard acronyms and proper names |
| English / en | “Generate an English-only figure” | English titles, blocks and captions; no stray Chinese labels |
| Bilingual | “中英双语，中文主标题、英文副标题” | Explicit language hierarchy, readable text, no duplicated dense paragraphs |
| Both editions | “生成中文和英文两个独立版本” | Separate `*_zh.png` and `*_en.png` (and PPTX when requested), visually consistent |

The skill chooses the language from explicit instructions first, otherwise from the user's prompt and current source figure. Text is translated **before** composition; English layouts are reflowed for longer phrases rather than simply reducing font sizes. Examples for all modes are in [references/EXAMPLE_PROMPTS.md](references/EXAMPLE_PROMPTS.md).

## Installation in Codex

Copy the directory `scientific-figure-slide-designer/` into your Codex skills directory (commonly `~/.agents/skills/` or the project-local `.agents/skills/`, depending on your Codex setup):

```bash
mkdir -p .agents/skills
cp -R scientific-figure-slide-designer .agents/skills/
```

Then ask Codex to use the skill explicitly, for example:

> Use the `scientific-figure-slide-designer` skill. Read the attached `model.pptx` and generate an English-only research method slide with separate editable icons, cards and connectors. Export PPTX and a high-resolution preview.

## Skill structure

```text
scientific-figure-slide-designer/
├── SKILL.md
├── README.md
└── references/
    ├── QA_CHECKLIST.md
    └── EXAMPLE_PROMPTS.md
```

## Example requests

**中文：** 使用这个 Skill 绘制一张16:9横向科研方法图，全部主要标注为简体中文，保持术语准确，导出可编辑 PPTX 与 PNG。

**English:** Use this skill to design a 16:9 scientific methodology diagram with English-only labels, clear causal arrows, native editable text and shapes, and a high-resolution PNG export.

**Both:** Make Chinese and English editions of the same figure, keeping its geometry, color semantics and arrow topology consistent.

## Design constraints

The skill describes behavior and quality standards; it does **not** include copyrighted paper figures, user-owned slide templates, school logos, or custom fonts. Users supply those at runtime.

It does not magically make generated raster icons editable vectors. Instead, it directs the agent to keep all essential text, connectors, and cards as native PowerPoint objects while treating icon images as separate reusable assets.

## License

MIT (skill text and examples only). Third-party assets supplied by users retain their own licenses.
