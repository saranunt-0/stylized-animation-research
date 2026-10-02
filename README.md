# Stylized Animation Research

A technical reference for making stylized, painterly 3D animation in the spirit of **Arcane** (Fortiche Production), **Blender Studio's Project Gold** and **Alberto Mielgo's films** (*The Witness*, *Jibaro*, *The Windshield Wiper*).

The reference covers documents, breakdowns, recreations, free assets and open-source code for each production stage. Free and open-source material is covered in depth; paid tools and courses get a one-line summary and a link.

**Compiled:** 2 October 2026, against Blender 5.2 LTS, with 5.3 in alpha.

## Start here

- **[Main report](reports/Stylized%20animation%20tools%20reference.md)**: one document, organized by subtopic, with tool tables (licence, status, evidence, link).
- **[Recommended free starter stack](reports/Stylized%20animation%20tools%20reference.md#11-recommended-free-starter-stack-blender-52-lts-plus-a-dozen-free-tools)**: one free pick per production stage.
- **[Where to start: six tests](reports/Stylized%20animation%20tools%20reference.md#12-where-to-start-six-tests-before-building-the-film)**: look-dev, animation, FX and sound tests to run before building the pipeline.
- **[Tools to avoid](reports/Stylized%20animation%20tools%20reference.md#10-abandoned-outdated-and-license-restricted-tools-to-avoid)**: abandoned or outdated add-ons, and tools that are free but not for commercial use.

## By subtopic

| Subtopic | Report section | Detailed research notes |
|---|---|---|
| Reference productions (how Arcane, Gold and Mielgo's films were made) | [§1](reports/Stylized%20animation%20tools%20reference.md#1-reference-productions-paint-the-image-first-and-use-3d-as-scaffolding) | [01_reference_productions.md](research_notes/Stylized%20animation%20tools%20reference/01_reference_productions.md) |
| Pre-production and pipeline | [§2](reports/Stylized%20animation%20tools%20reference.md#2-pre-production-and-pipeline-copy-blender-studios-conventions-before-its-servers) | [09_preproduction_pipeline.md](research_notes/Stylized%20animation%20tools%20reference/09_preproduction_pipeline.md) |
| Modeling and sculpting | [§3](reports/Stylized%20animation%20tools%20reference.md#3-modeling-and-sculpting-simple-forms-controlled-normals-detail-in-paint) | [02_modeling_sculpting.md](research_notes/Stylized%20animation%20tools%20reference/02_modeling_sculpting.md) |
| Texturing (hand-painted / painterly) | [§4](reports/Stylized%20animation%20tools%20reference.md#4-texturing-pairs-uv-painted-albedo-with-camera-projected-paint-overs) | [03_texturing.md](research_notes/Stylized%20animation%20tools%20reference/03_texturing.md) |
| NPR shading, lighting and rendering | [§5](reports/Stylized%20animation%20tools%20reference.md#5-npr-shading-lighting-and-rendering-blender-53-lighting-nodes-replace-a-dead-prototype) | [04_shading_lighting_rendering.md](research_notes/Stylized%20animation%20tools%20reference/04_shading_lighting_rendering.md) |
| Animation and rigging | [§6](reports/Stylized%20animation%20tools%20reference.md#6-animation-and-rigging-keyframe-from-reference-step-per-shot-rig-with-cloudrig) | [05_animation_rigging.md](research_notes/Stylized%20animation%20tools%20reference/05_animation_rigging.md) |
| VFX (2D FX over 3D, stylized 3D FX) | [§7](reports/Stylized%20animation%20tools%20reference.md#7-vfx-draw-on-twos-over-locked-3d-or-simulate-and-repaint) | [06_vfx.md](research_notes/Stylized%20animation%20tools%20reference/06_vfx.md) |
| Compositing and color | [§8](reports/Stylized%20animation%20tools%20reference.md#8-compositing-and-color-finish-the-painting-rather-than-create-it) | [07_compositing_color.md](research_notes/Stylized%20animation%20tools%20reference/07_compositing_color.md) |
| Sound design and music | [§9](reports/Stylized%20animation%20tools%20reference.md#9-sound-design-and-music-start-from-cheap-organic-recordings) | [08_sound_design.md](research_notes/Stylized%20animation%20tools%20reference/08_sound_design.md) |

The report is the curated, cross-checked version. The research notes are longer and keep every lead, including gaps and open questions.

## How reliable is this?

The research environment blocked page fetches from most sites other than GitHub, including blender.org, 80.lv, befores & afters, YouTube and most vendor sites, and its web-search budget was capped. As a result:

- **Open-source tool facts are strong.** Licence, releases, last activity and archive status were read directly from GitHub.
- **Production facts are mostly second-hand.** How Arcane, Gold and Mielgo's films were made comes largely from search-engine summaries of interviews.
- **Prices were not checked on vendor pages.**

Every entry carries an evidence tag:

| Tag | Meaning |
|---|---|
| **R** | Read directly (GitHub repo, release, API metadata, Blender source) |
| **S** | From a search-engine summary of the linked page; spot-check before quoting |
| **L** | Link found inside another document; not opened |
| **U** | Unverified (prior knowledge or aggregator claim) |

Before you build on a claim tagged S, L or U, or adopt an add-on, check the live page and the add-on's compatibility with your Blender version.

## Repository layout

```
README.md                                  ← this index
reports/
  Stylized animation tools reference.md    ← consolidated report (start here)
research_notes/
  Stylized animation tools reference/      ← one detailed notes file per subtopic (01–09)
```
