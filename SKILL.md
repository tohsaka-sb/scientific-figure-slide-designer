---
name: scientific-figure-slide-designer
description: Create and revise publication-style scientific diagrams, method figures, research timelines, and editable presentation slides. Use for research presentations, thesis proposals, agent systems, workflows, comparisons, experimental plans, diagrams, transparent PNG assets, and PPTX decks, especially when the user supplies a visual reference or PowerPoint template.
---

# Scientific Figure & Slide Designer

Produce scientifically accurate, visually refined research diagrams and presentation slides. Prefer **semantic clarity and projection legibility** over decorative complexity. Match the user's supplied references and existing deck conventions.

## 1. Resolve the requested deliverable

- Distinguish **raster illustration** (`.png`), **transparent image** (`.png` with real alpha), **editable slide** (`.pptx`), and **both**. Do not replace a requested editable PPTX with an image pasted on a slide.
- When an existing `.pptx` template is provided, **load and preserve it**: aspect ratio, background, footer, institutional identity, page numbering style, and established fonts/colors, unless the user specifies changes.
- For a user-supplied diagram, preserve its scientific meaning while restyling. If the user asks to separate one figure into Q1/Q2/Q3, create separate self-contained figures—not three arbitrary crops.
- Only add content consistent with the user's research plan. Clearly distinguish implemented work, proposed work, and future experiments.

## 2. Output language selection (Chinese / English / bilingual)

**Chinese and English are first-class output languages. Neither has priority by default.** Resolve the requested language before layout, and keep scientific meaning and visual quality equivalent in both modes.

- **Explicit language wins:** `language: zh-CN` / “中文版” / “中文标注” => all principal titles, headings, explanatory labels, arrows and captions in Simplified Chinese. `language: en` / “English-only” / “英文版” => all principal visible text in English. `language: bilingual` => both languages, with a deliberately defined hierarchy (for example Chinese heading with smaller English subtitle).
- **When unspecified:** follow the language of the user's request and the existing slide/figure. If these disagree and the intended output is genuinely ambiguous, ask one concise question. Never assume Chinese merely because earlier examples were Chinese.
- **Strict language fidelity:** do not leave incidental Chinese in English-only visuals or incidental English sentence fragments in Chinese-only visuals. Keep proper names, abbreviations, citations, established variable names, metric names (e.g. F1, BLEU-1), and code tokens as required by the content.
- **Technical equivalence:** translate meaning, not word-by-word layouts. Preserve formulas, agent roles, state semantics, direction of arrows, references, and distinctions such as candidate evidence versus admitted shared memory.
- **Translation before drawing:** prepare a reviewed label map for title, stage names, box labels, legends and takeaway text. For bilingual slides, avoid translating the same full paragraph twice; keep compact one-to-one terms.
- **Typesetting for each language:** Chinese requires appropriate CJK font/fallback, balanced character spacing and correct punctuation; English needs natural capitalization, line breaks at words, adequate width for longer terms, and appropriate sans-serif fonts. Reflow card width and font sizes rather than squeezing text into the same coordinates.
- **Two-language editions:** when both versions are requested, generate separate `*_zh` and `*_en` assets with consistent node IDs, icon positions, colors and connectors; allow text boxes to resize within the same grid. Do not replace language switching with an illegible bilingual overlay.
- **Quality checks:** proofread Chinese glyphs and English spelling/grammar independently. Inspect rendered images, especially generated text, to catch missing glyphs, garbled characters, unintended code-switching and clipped English compounds.

## 3. Diagram design principles

1. **Scientific rather than commercial aesthetic.** Take inspiration from top-conference method figures: precise grouping, aligned nodes, subdued panels, consistent visual grammar, restrained pastel accents, legible arrows and labels.
2. **Illustrate rather than decorate.** Use meaningful icons (document, search, reasoning, verification, execution, database, feedback, evidence dependency, confidence), paired with brief, editable labels. Icons should clarify function, never substitute for meaning.
3. **Same-level comparisons.** Compare corresponding architecture levels: e.g. agent-local memories versus shared memory, keeping agent roles and collaboration task comparable on both sides. Do not contrast a communication workflow against a memory database as if they were alternatives.
4. **Layout follows information flow.** Prefer left-to-right composition and multiple balanced columns for 16:9 slides. Use top-to-bottom only when intrinsically sequential or sufficiently short. Make Stage 1–4 flows scan in seconds.
5. **Arrows communicate semantics.** Explicitly distinguish read/write, selection, evidence support/refutation, admission, update, and feedback. Bidirectional arrows only when both directions truly exist. Highlight feedback loops, avoid crossing lines, and keep arrowheads clear.
6. **Distinguish memory states and evidence.** Candidate memory is not automatically admitted to shared memory; verification records are not the same as established truth. Keep provenance/dependency/contested states when the research question calls for them.
7. **Logical feedback loop.** If utilization feedback changes shared memory, draw the return arrow to the consolidation/maintenance decision center; if necessary, show a return to verification separately.
8. **One slide, one thesis.** Keep the key claim obvious in title or footer. Do not fill all whitespace to create artificial complexity.

## 4. Visual language

- Canvas: widescreen 16:9 unless the user supplies a different template. Use high-resolution output (prefer at least 1920×1080 for a full-slide raster illustration).
- Background: clean white, very light blue, or **the actual PPTX template background**. Do not cover mandatory school/institution footer or branding.
- Colors: deep navy text; blue for retrieval/formation, violet for verification/conflict, green/teal for shared-memory maintenance, amber/orange for task execution or feedback, red reserved for conflicts/errors. These mappings are examples, not rigid rules; preserve user palette.
- Components: aligned softly rounded pastel cards, thin consistent strokes, subtle shadows only when they enhance hierarchy, dedicated label zones, simple vector-like icon illustrations.
- Typography: follow the selected output language. For Chinese use a readable CJK sans-serif (e.g. Microsoft YaHei or Noto Sans CJK); for English use a well-supported sans-serif (e.g. Aptos, Arial, Calibri). Use secondary-language subtitles only when bilingual output is requested. **Render all text as actual PPTX text boxes in editable files**.
- Projection-first sizing: title around 26–34 pt, module headings 17–22 pt, explanation 13–17 pt for typical 13.33×7.5 in slides; avoid tiny dense body text. Scale proportionally for other slide sizes.
- Avoid too many bullets, microscopic annotations, heavy borders, high-gloss gradients, random icon styles, or labels overlapping arrows and diagrams.

## 5. Figure composition patterns

### A. Before vs. after comparison

Keep the same agent roles on both sides. Left: each agent has **its own private/local memory**, with collaboration messaging shown as a secondary link. Right: same agents read from and write to one **persistent shared memory space**, and optionally retain local memories. Compare persistence, cross-agent reuse, and information fragmentation—not different task types.

### B. Literature evolution

Show conceptual progression (e.g. single-agent long-term memory → experience abstraction/reuse → multi-agent communication → multi-agent shared memory). Clearly note that these are **research emphases**, not mutually exclusive replacement generations. Cite representative methods accurately and redraw simplified architecture diagrams rather than illegibly shrinking entire paper figures.

### C. Multi-question figures

For Q1 selection, Q2 dependency-aware consolidation, and Q3 feedback-driven maintenance, create three standalone landscape diagrams with a shared title/subtitle style, distinct but harmonious color accents, and a consistent bottom takeaway. Preserve their specific scientific questions and mechanisms.

### D. Four-stage research route

Stage 1: Candidate Formation & Selective Sharing → Stage 2: Cross-Agent Evidence Verification → **Stage 3: Shared Memory Consolidation & Dynamic Maintenance (decision center / admission)** → Stage 4: Role-Aware Memory Utilization & Feedback. Explicitly draw Stage 4 → Stage 3, optionally Stage 3 → Stage 2 for renewed verification. Stage 1 produces candidates, Stage 2 produces evidence records; Stage 3 actually decides admission/state.

### E. Research timeline

Use 4–6 aligned milestones/cards along a horizontal timeline, with date, phase name, simple icon, and 1–3 concise actions per stage. Keep the original dates and scope unchanged. Never invent completed results or change the dates silently.

## 6. Asset and implementation strategy

- Plan content and arrow topology **before** rendering. Prefer creating icons as independent transparent PNG or vector assets, and integrating them with native PowerPoint shapes/text.
- When a static image is requested, generate or render the diagram at presentation resolution. For diagram text, favor programmatic text rendering when exact Chinese characters and technical symbols are important; image generation may introduce typos.
- When a PPTX is requested, use suitable PowerPoint tooling (e.g. `python-pptx`, PptxGenJS, or another installed slide skill) to implement the composition. Keep text, lines, panels, tables, and labels editable; independent icon images are acceptable. Avoid using an entire diagram screenshot as the only slide element.
- Preserve the provided template by modifying a copy; inspect its slide dimensions, master/footer, existing slide objects, and picture relationships. Do not manually recreate or substitute the brand identity with an approximation.
- Export a PNG preview for inspection when possible. Editable shapes are more important than a preview screenshot.
- **Transparent PNG is a technical requirement**: the exported file must have RGBA with true alpha zero outside the intended figure, not a black/white simulated backdrop. Remove only the background, preserve interior white card fills. Inspect transparency against both dark and light checkerboard backgrounds and check halo artifacts.
- Do not distribute third-party copyrighted paper figures, institutional logos, or user templates in the public skill package unless permission/license is clear; the user may supply these assets during invocation.

## 7. Validation: mandatory before delivery

- **Research accuracy:** labels, directionality, stage dependencies, source attributions, role-specific vs shared memory semantics, and proposed vs completed claims.
- **Language accuracy:** requested zh-CN, en or bilingual mode is consistently applied; Chinese glyphs/punctuation and English spelling/grammar are checked; bilingual hierarchies and invariant equations/acronyms are reviewed. Inspect rendered output rather than relying only on source strings.
- **Readability:** 100% slide view and a reduced thumbnail; no tiny annotations, crowded cards, unexplained arrows, or unbalanced empty space.
- **PPTX editability:** actual native text/shapes for all principal components; verify template remains visible, no clipping/overlaps, images proportionally scaled, source file opens.
- **Transparency:** verify real alpha in the final PNG; check dark and light background compositing.
- **Deliverables:** provide exact file paths/links for requested output types. Never claim generated PPTX or transparency without checking the file.

## 8. Revision behavior

- Treat user feedback as a precise change request; preserve every unaffected module, visual decision, and scientific relationship.
- Typical fixes: shift vertical pipeline to a balanced horizontal grid; retain two relevant comparison panels while removing an unwanted third; add separate local memory cylinders to traditional MAS; improve icon consistency; convert English annotations to precise Chinese; separate one dense Q1/Q2/Q3 figure into three figures; correct arrow feedback target; perform *actual* background removal without reconstructing content.
- If the user says a previous version's content was better, use that **specific previous version** as semantic reference and update only the requested styling or structure. Do not silently redesign or simplify away important mechanisms.

## 9. Output expectations

Default delivery includes the final requested asset and, for PPTX, a rendered preview if possible. If asked for reusable assets, place icons and editable source files in a clear folder structure. Briefly state what is editable and any remaining limitations (e.g. generated icon images are raster assets).

For detailed QA procedure and example prompts, read `references/QA_CHECKLIST.md` and `references/EXAMPLE_PROMPTS.md`.
