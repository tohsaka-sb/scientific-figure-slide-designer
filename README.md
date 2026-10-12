# Scientific Figure & Slide Designer

A reusable Codex/agent skill for creating **scientifically accurate, presentation-ready research figures and editable PowerPoint slides**, based on iterative preferences developed during a multi-agent memory thesis presentation.

## Key features

- Research-paper-style method figures with coherent icons, panels, and semantic arrows
- Side-by-side **like-for-like** comparisons (e.g. independent local memory vs. shared memory)
- Wide, balanced 16:9 layouts instead of unnecessarily tall stacks
- Chinese-first precise labels and bilingual technical terminology
- Editable PPTX based on an uploaded institutional template
- True transparent-background PNG exports and visual QA
- Research workflows, evidence verification diagrams, evaluation summaries, timelines

## Installation in Codex

Copy the directory `scientific-figure-slide-designer/` into your Codex skills directory (commonly `~/.agents/skills/` or the project-local `.agents/skills/`, depending on your Codex setup):

```bash
mkdir -p .agents/skills
cp -R scientific-figure-slide-designer .agents/skills/
```

Then ask Codex to use the skill explicitly, for example:

> Use the `scientific-figure-slide-designer` skill. Read the attached `model.pptx` and generate a Chinese research method slide with separate editable icons, cards and connectors. Export PPTX and a high-resolution preview.

## Skill structure

```text
scientific-figure-slide-designer/
├── SKILL.md
├── README.md
└── references/
    ├── QA_CHECKLIST.md
    └── EXAMPLE_PROMPTS.md
```

## Design constraints

The skill describes behavior and quality standards; it does **not** include copyrighted paper figures, user-owned slide templates, school logos, or custom fonts. Users supply those at runtime.

It does not magically make generated raster icons editable vectors. Instead, it directs the agent to keep all essential text, connectors, and cards as native PowerPoint objects while treating icon images as separate reusable assets.

## License

MIT (skill text and examples only). Third-party assets supplied by users retain their own licenses.
