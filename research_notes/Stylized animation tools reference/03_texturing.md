# Texturing (Hand-Painted / Painterly) for Stylized 3D Animation: Arcane, Project Gold, Mielgo

> **Research conditions and verification key (read first).** This session's network egress allowed full-page fetches **only from github.com / raw.githubusercontent.com**. Every other domain (80.lv, ArtStation, Blender Studio, docs.blender.org, extensions.blender.org, developer.blender.org, docs.krita.org, armorpaint.org, befores & afters, CG Channel, AWN, YouTube, Poly Haven, etc.) was blocked, and the shared web-search budget ran out partway through. Each claim is tagged with how it was checked:
> - **[V]**: page or repo fetched directly in this session. Content verified.
> - **[S]**: from a search-engine result summary or snippet. The URL is real (returned by search) but the page body was **not** read, so wording and attribution may be imprecise.
> - **[L]**: the URL comes from a curated GitHub list that was fetched ([awesome-blender](https://github.com/agmmnn/awesome-blender) or [magictools](https://github.com/ellisonleao/magictools)) or from a fetched README. The target page was not fetched.
> - **[K]**: the URL comes from prior knowledge. It was **not found or fetched this session**, so verify it before publishing. Used only for a few official paid-product homepages.
>
> Category labels: `documentation` / `tutorial` / `recreation` / `code-addon` / `asset` / `course(paid)` / `talk`.
> "Current" means as of 2 Oct 2026.

---

## Q1. How exactly were textures made in Arcane (Fortiche), Blender Studio's Project Gold, and Alberto Mielgo's films?

### Takeaway
- **Arcane:** 3D assets were textured with hand-painted maps (Photoshop is named most often; Substance Painter is only *possibly* involved, per aggregators). A dedicated texturing department led by Texturing Supervisor Candice Theuillon did the work. Season 2 backgrounds were built as 3D sets and then matte-painted and projected, with deliberately shaky freehand lines.
- **Project Gold:** the painterly look came mainly from the procedural Geometry-Nodes **Brushstroke Tools** (3D strokes placed on the surface) plus NPR rendering in Cycles, not from conventional painted UV textures.
- **Mielgo's films:** much of the "texture" lives in **hand-painted 2D backgrounds** (Photoshop) under 3D characters (Maya), with an impressionistic, detail-reducing approach. *The Witness* used flat paintings in place of 3D lit sets, and *Jibaro* used Maya, Houdini and Arnold.

### Cited Findings

**Arcane (Fortiche): primary and near-primary sources**
- `talk`: Fortiche/industry talk titled **"Arcane S2 texturing: Animating the hand-painted look"** on YouTube. The presenter, event and date could not be confirmed because YouTube was blocked. This is the most direct source and should be watched first. [S] [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84)
- `documentation`: 80.lv **"A Closer Look at Texturing in Arcane"** shows textured production models: Vi (textured by Texturing Supervisor **Candice Theuillon**), the Firelight Leader (Senior Texture Artist **Gilles Roman**) and Jinx's Fishbones (**Simon Goeneutte-Lefevre**). [S] [80.lv Part 1](https://80.lv/articles/a-closer-look-at-texturing-in-arcane). **Part 2** covers Caitlyn and others. [S] [80.lv Part 2](https://80.lv/articles/a-closer-look-at-texturing-in-arcane-part-2)
- `documentation`: Theuillon's ArtStation says she was Texturing Supervisor on Arcane "from the beginning" under director **Pascal Charrue**, and shows texturing breakdowns for Vi, Caitlyn and Silco. [S] [Vi](https://candicetheuillon.artstation.com/projects/b505vm) · [Caitlyn](https://candicetheuillon.artstation.com/projects/aGy4zz) · [Silco](https://candicetheuillon.artstation.com/projects/X1PKwy)
- `documentation`: further production texture breakdowns by Fortiche artists:
  - Gilles Roman: [Singed textures](https://www.artstation.com/artwork/AroEYW) and [Scar textures](https://gillesroman.artstation.com/projects/Ze02PZ)
  - Thibaut Granet (character modeler and texture artist): [Jinx](https://www.artstation.com/artwork/4X8vGl)
  - Céline Giglio: [character texturing](https://www.artstation.com/artwork/DAYA40)
  - Ambre Sedogbo: [S2 prop textures](https://www.artstation.com/artwork/eR3Zdb)

  All [S]. The ArtStation "Software used" fields could not be read.
- `documentation`: 80.lv **"How Traditional Art & 3D Combine for Backgrounds in Arcane"** (Season 2). The team builds a 3D set first, then matte-paints and **projects paint onto the 3D assets** with brushes that imitate traditional tools. Artists "try to freehand the lines and make them a little shaky to get this hand-drawn feel." [S] [80.lv](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds). Matching S2 matte-painting breakdowns: [Mathis Richard](https://www.artstation.com/artwork/rle426), [Naïm Bonnot 1](https://www.artstation.com/artwork/WXYl8J), [Naïm Bonnot 2](https://www.artstation.com/artwork/EzOwZ2) [S]
- Fortiche used **projection mapping**, layering 2D matte-painted backgrounds onto simple 3D geometry, which gives parallax during camera moves. [S] Search summaries attribute this to [RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline) and [8forty](https://8forty.ca/2022/01/19/arcane-3d-animation-with-hand-drawn-backgrounds/). The exact wording could not be verified.
- "Artists hand-painted the characters' surface textures in **Photoshop**," adding brushstrokes, colour variation and imperfections instead of flat colour or procedural materials. "Substance Painter **may** have been used" for wear and gradients before refinement in Photoshop. [S] This comes mainly from the **low-authority aggregator** [yelzkizi.org](https://yelzkizi.org/what-3d-program-did-arcane-use/) and is echoed in summaries of RedShark. **Treat Substance use as unconfirmed.**
- "Fortiche developed custom shaders to preserve the hand-painted aesthetic under lighting, reducing realistic CG effects like specular highlights." [S] The source is again an aggregator summary (yelzkizi/RedShark), and no primary confirmation was found.
- `talk`: interviews about the overall pipeline, but not texturing specifically:
  - [SyncSketch: interview with Alexis Wanneroy](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) [S]
  - [AWN: Pascal Charrue & Alexis Wanneroy](https://www.awn.com/animationworld/unveiling-arcane-conversation-pascal-charrue-and-alexis-wanneroy) [S]

  Neither page body could be read.

**Project Gold (Blender Studio, 2024)**
- `documentation`: Project Gold is "a technical showcase focused on stylized rendering, along with an add-on designed to achieve a painterly look." It premiered at Blender Conference in October 2024 and was released online on 7 Nov 2024. It began as a short directed by **Jericca Cleland** and was refocused into a showcase for the new tools. [S] [Blender Studio project page](https://studio.blender.org/projects/gold/) · [Premiere blog](https://studio.blender.org/blog/project-gold-premiere/) · [Blender Studio on X](https://x.com/BlenderStudio_/status/1854560062036942921)
- `code-addon`: **Brushstroke Tools** were developed during Project Gold. They are "a set of Geometry Nodes-based tools … for creating, managing, and editing layers of 3D brushstrokes generated procedurally". Strokes can fill the entire mesh surface procedurally or be drawn directly onto the surface. The tools are free. [S] [CG Channel](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/) · [Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools)
- The film showcases light linking, Simulation Nodes, Geometry Nodes tools and "art-directable, stylized, non-photorealistic rendering with **Cycles**." [S] [Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools) · [CRUDO](https://crudo.dev/posts/blender-studio-project-gold/)
- `documentation`: production logs, e.g. [Production Log #5](https://studio.blender.org/projects/gold/production-log/246/) and the [log index](https://studio.blender.org/projects/gold/production-logs/?page=11) [S]. These were not readable, so per-asset texturing details (painted maps vs. strokes only) are unverified.

**Alberto Mielgo: *The Witness* (LD+R S1, 2019)**
- `talk`: in befores & afters, the "graphic-but-realistic style came from **2D painterly backgrounds**, the use of **Marvelous Designer** for clothing simulations, and treatments given to just about every frame." Instead of 3D sets "they had paintings," and Mielgo explained to lighters how each painting was lit so the 3D could match. Cloth shading was done by **Zeno Pelgrims**. [S] [befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/)
- `talk`: further interviews:
  - [Chaos CG Garage: Alberto Mielgo](https://www.chaos.com/cg-garage/alberto-mielgo-director-ldrs-the-witness) [S]
  - [BlenderNation: Vaughan Ling (The Witness)](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/) [S], relevant because a Blender user worked on the production. His exact role was not verified.
  - [80.lv: Creating Fantastic Visuals in LD+R](https://80.lv/articles/creating-fantastic-visuals-for-love-death-robots) [S]

**Mielgo: *Jibaro* (LD+R S3, 2022; studio Pinkman.TV)**
- `talk`: 80.lv relays Mielgo's own breakdown of how the knight and siren were modelled, **textured** and rigged. [S] [80.lv](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro)
- Toolset: **Maya** for animation, **Houdini** for simulation, **Arnold** for rendering. "The hardest part was texturing and rendering the golden siren along with the armor." [S] The source is a search summary of the 80.lv, Deadline and IndieWire set, and which page says what was not pinned down. [Deadline](https://deadline.com/2022/06/alberto-mielgo-love-death-robots-jibaro-animation-dialogue-1235039230/) · [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/)
- Mielgo: "more impressionism than realism". The characters have no pores or deep skin detail, and he removes anything he doesn't need. He shot forest video reference on a road trip and also shot **underwater video reference for textures and lighting**. [S] [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/) · [AwardsDaily](https://www.awardsdaily.com/2022/06/26/alberto-mielgo-on-his-animated-short-jibaro-in-netflixs-love-death-robots/)
- `documentation`: [Jibaro animatic via STASH](https://www.stashmedia.tv/alberto-mielgo-shares-love-death-robots-jibaro-animatic/) and a fan overview, [Medium: The Art of Alberto Mielgo](https://medium.com/@lou_lotus/the-art-of-alberto-mielgo-fba33b8cb10e) [S]

**Mielgo: *The Windshield Wiper* (2021, Oscar winner)**
- Characters were modelled and animated in **Maya**. Mielgo **painted the backgrounds in Photoshop** (with select artists), and they were integrated in After Effects and Premiere. [S] Summary drawn from [befores & afters Q&A](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/), [Cartoon Brew](https://www.cartoonbrew.com/shorts/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html), [Animation Magazine](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/), [Variety](https://variety.com/2021/artisans/markets-festivals/alberto-mielgo-windshield-wiper-1235017864/) and [Wikipedia](https://en.wikipedia.org/wiki/The_Windshield_Wiper). Per-source attribution was not verified.

### Inferences
- Across all three references, much of the "painted texture" look is **not** carried by UV albedo maps alone. It comes from three sources:
  1. Painted backgrounds or matte paintings projected from camera (Arcane S2, all three Mielgo films).
  2. Painted albedo with simplified, low-specular shading (Arcane characters, if the aggregator claim holds).
  3. Geometric or procedural brushstrokes (Project Gold).

  A free replication pipeline therefore needs both **texture-space painting** (Blender, Krita, ArmorPaint) and **camera-projection painting** (Blender Quick Edit / Apply, see Q2).
- Mielgo's "remove detail / no pores" principle argues for **large-shape, low-frequency painted textures** and against high-frequency PBR detail. This is the opposite of photoreal Substance smart-material workflows.

### Gaps
- No primary source fetched in this session confirms **which paint application** Fortiche texture artists used (Photoshop vs. Substance 3D Painter vs. Mari vs. 3DCoat), or the shader details. The YouTube S2 texturing talk and the 80.lv "Closer Look" articles are the best places to confirm this but could not be read.
- Whether Project Gold also used painted UV textures alongside Brushstroke Tools is unverified (production logs blocked).
- *The Witness* renderer and texturing software are unverified. The Chaos (V-Ray vendor) interview suggests V-Ray, but that is **not confirmed**.

---

## Q2. Which free/open-source tools can replicate a hand-painted texture workflow end to end, and what are their limitations?

### Takeaway
A complete free pipeline is achievable:

1. **Blender** for modelling, UVs, baking, texture/projection painting and Quick Edit round-trips.
2. **Ucupaint** for layers and masks inside Blender. It is actively maintained, GPL-3, and supports Blender up to 5.2 with fixes for 5.3.
3. **Krita 6.0.x** for painterly brushwork via the blender-krita-link bridge.
4. **ArmorPaint** (built free from zlib-licensed source; prebuilt binaries are paid) or **Material Maker** (MIT) as a standalone 3D painter.
5. Optionally Brushstroke Tools or a Kuwahara compositor pass for procedural, screen-space painterliness.

The main weak points are Blender's lack of native paint layers (hence add-ons), experimental bridges, ArmorLab apparently being dropped, and stale bake and UV add-ons.

### Cited Findings

**Core paint applications**
- `code-addon` / `documentation`: **Blender Texture Paint, projection and "paint from camera".** Blender's current source (main branch) defines:
  - an **External** panel (`VIEW3D_PT_tools_imagepaint_options_external`) with **"Quick Edit"** (`image.project_edit`) and **"Apply"** (`image.project_apply`). Quick Edit sends a viewport capture to an external editor such as Krita or Photoshop, and Apply re-projects the painted result onto the mesh from that view.
  - a **Stencil Mask** panel, **Clone from Paint Slot**, a **Texture Slots** panel, **Normal Falloff**, and `use_occlude` / `use_backface_culling` options.

  [V] [Blender source: space_view3d_toolbar.py](https://raw.githubusercontent.com/blender/blender/main/scripts/startup/bl_ui/space_view3d_toolbar.py). The official Blender mirror is at [github.com/blender/blender](https://github.com/blender/blender) [V].
- `code-addon`: **Krita**, a free and open-source painting program [L] ([krita.org](https://krita.org/), via [magictools](https://github.com/ellisonleao/magictools)).
  - **Krita 6.0.0 was released 19 Mar 2026.** The latest is **6.0.4.1 (1 Oct 2026)**, a critical bugfix for ICC display-profile changes.
  - The 5.2 line ended at 5.2.16 (24 Feb 2026).

  [V] [KDE/krita tags](https://github.com/KDE/krita/tags)
- `code-addon`: **ArmorPaint** (part of armory3d/armortools), "a software for 3D PBR texture painting".
  - Source is **zlib/libpng-licensed** [V] ([license.md](https://github.com/armory3d/armortools/blob/main/license.md)).
  - "Distributed binaries are paid to help with the project funding." The source is free to compile for Windows, Linux, macOS, iOS, Android and WebAssembly. The repo is "aimed at developers and may not be stable."
  - About 5.3k stars. **Active:** commits on 1 Oct 2026 ("paint: cloud projects in wasm", "base: wasm fixes").

  [V] [armortools repo](https://github.com/armory3d/armortools) · [commits](https://github.com/armory3d/armortools/commits/main) · official site [armorpaint.org](https://armorpaint.org/) (linked from README; not fetched)
- **ArmorLab status: the AI texture generator appears dropped from the main repo.**
  - The old `armorlab` repo is **archived** with "Moved to armortools/tree/main/armorlab" [V] ([deprecated-armory3d/armorlab](https://github.com/deprecated-armory3d/armorlab)).
  - The current armortools top level shows only `base` and `paint`, and `/tree/main/lab` returns 404 [V] ([armortools](https://github.com/armory3d/armortools)).
  - **Treat ArmorLab as discontinued or unmaintained (inferred).**
- `code-addon`: **Material Maker** (MIT): "a tool for creating textures procedurally and painting 3D models", built on Godot with a node-based interface. Available on [itch.io](https://rodzilla.itch.io/material-maker) and [Steam](https://store.steampowered.com/app/4110830/Material_Maker/), with nightly builds via GitHub Actions. About 6k stars and active (updated Oct 2026). [V] [RodZill4/material-maker](https://github.com/RodZill4/material-maker)
- `code-addon`: **MyPaint**, a simple painting program for graphics tablets, plus **libmypaint** ("brushlib"), the brush engine library used by MyPaint and other projects. [V-search metadata] [mypaint/mypaint](https://github.com/mypaint/mypaint) · [libmypaint](https://github.com/mypaint/libmypaint) · [mypaint-brushes](https://github.com/mypaint/mypaint-brushes)
- `code-addon`: **GIMP**, the GNU Image Manipulation Program, usable for flat UV-space painting and cleanup. [L] [gimp.org](http://www.gimp.org/)

**Bridges between Blender and 2D painting apps (camera or UV round-trip)**
- `code-addon`: **blender-krita-link-plugin** (GPL-3).
  - "Edit Blender images in Krita without the need for file reloads." It imports textures as layers, overlays Blender UVs on the Krita canvas, transfers UV-face selections into Krita selections, and live-updates the texture in Blender.
  - Has specific install instructions for Blender 4.2+. Self-described as **"highly experimental"**, and it "probably does not work well on macOS."

  [V] [heisenshark/blender-krita-link-plugin](https://github.com/heisenshark/blender-krita-link-plugin)
- `code-addon`: **BlenderLayer** (GPL-3) streams the Blender 3D viewport into Krita as a layer, so you can trace over it and use blend modes and layer styles. Texture painting back onto 3D is only a "proof of concept / potential future" feature. [V] [Yuntokon/BlenderLayer](https://github.com/Yuntokon/BlenderLayer)
- `code-addon`: **Brandy-Texture-Link-Lite**: "edit texture files in Photoshop and reload saved changes in Blender." Created July 2026 with about 1 star, so immature. [V-search metadata] [BrandySPE/Brandy-Texture-Link-Lite](https://github.com/BrandySPE/Brandy-Texture-Link-Lite)
- `code-addon`: **Camera Projection Painter** (GPL-3, v4.0.0). It clones paint from original photos onto photogrammetry meshes and is designed for photo sources, not painted concept frames. Its relevance to painted projection is inferred, not documented. [V] [BlenderHQ/camera_projection_painter](https://github.com/BlenderHQ/camera_projection_painter)

**Other open-source painters (minor or legacy)**
- `code-addon`: **godot-texture-painter**, "a GPU-accelerated texture painter written in Godot 3.0". Legacy, created 2018. [V-search metadata] [Bauxitedev/godot-texture-painter](https://github.com/Bauxitedev/godot-texture-painter)

### Inferences
- A **recommended free end-to-end chain**:
  1. Blender for modelling and UVs (native tools plus TexTools or UV-Packer).
  2. Bake AO and curvature in Blender, or with Ucupaint 2.4.9's new **curvature/thickness** bake types.
  3. Block in base colour and masks in Ucupaint layers.
  4. Do painterly brushwork in Krita via blender-krita-link, with UV overlay.
  5. Project shot-specific paint-overs from camera with Blender **Quick Edit → Krita → Apply**. This is the free analogue of Arcane S2's matte-paint projection.
  6. Optionally add Brushstroke Tools strokes and/or a Kuwahara compositor pass.
- **Limitations to flag:**
  - Blender's texture paint has no native layer stack. This is inferred from the need for Ucupaint, Layer Painter and RyMat, and the stock UI shows only "Texture Slots".
  - Bridges are experimental.
  - ArmorPaint's free route needs a compile toolchain.
  - ArmorLab appears dead.
  - Material Maker painting is less mature than its procedural side (unverified opinion).
- Krita 6.0 is a major version (released March 2026). Older Krita Python plugins, including bridges, may need updates. **Compatibility of blender-krita-link with Krita 6 is unverified.**

### Gaps
- Blender **texture-painting performance** (high-res and UDIM painting, CPU projection) and any **Blender 4.x/5.x texture-paint overhaul** (for example a layered-texture project) could not be verified: developer.blender.org and the release notes were blocked and search budget was exhausted. Before publishing, check the Blender 4.3 "brush assets" change and the 5.0–5.3 release notes.
- ArmorPaint's binary price and whether the old free "ArmorPaint for Linux / itch" builds exist remain unverified.

---

## Q3. Which free add-ons/repos help with painting, layers, baking, UVs and procedural painterly looks in Blender (name, function, license, URL, 4.x/5.x compatibility)?

### Takeaway
**Ucupaint** is the standout. It is free and GPL-3, with layers, masks, baking (including curvature in 2.4.9), UDIM and PSD-layer features. Release 2.4.9 lists compatibility from Blender 2.76 to 5.2, and commits from Sept 2026 fix Blender 5.3 issues. Several older bake add-ons (Principled-Baker, EasyBake) are stale. TexTools has not been committed since Dec 2024, and a community fork exists for Blender 5.x. For procedural painterliness, use Blender Studio's **Brushstroke Tools** (Geometry Nodes) and the native **Kuwahara compositor node** (classic and anisotropic).

### Cited Findings

**Layered painting / material add-ons**
- `code-addon`: **Ucupaint** (GPL-3).
  - "Blender addon to manage texture layers for Eevee and Cycles." About 2.2k stars. It is installable from GitHub Releases or the Blender Extensions platform (4.2+).
  - **v2.4.9 (29 Jul; year inferred as 2026):** compatibility 2.76 to 5.2, new bake types **curvature, thickness, wireframe**, and Blender 5.2 fixes.
  - **v2.4.8 (14 Jun):** image-atlas options, plus group-mask support for **PSD layers in "Ucupaint Plus."**
  - **v2.4.7 (26 May):** PSD layer import/export (Plus), and removed `exec`/`eval` for security.
  - Latest commits are dated 1 Oct 2026. A 3 Sept 2026 commit fixes UV-map operations on **Blender 5.3**.

  [V] [ucupumar/ucupaint](https://github.com/ucupumar/ucupaint) · [releases](https://github.com/ucupumar/ucupaint/releases) · [commits](https://github.com/ucupumar/ucupaint/commits/master) · [Extensions listing](https://extensions.blender.org/approval-queue/ucupaint/) [S] · [BlenderNation feature (Oct 2024)](https://www.blendernation.com/2024/10/21/ucupaint-layer-based-painting-for-eevee-and-cycles/) [S] · [BlenderArtists thread](https://blenderartists.org/t/addon-ucupaint-tool-to-manage-texture-layers-for-eevee-and-cycles/1390056) [S]
  - Feature summary per search: combines image, colour, vertex-colour and procedural sources in an ordered stack; groups and masks; UDIMs auto-detected from UV islands; bake channels to images. [S] [LinuxLinks](https://www.linuxlinks.com/ucupaint-layer-based-texture-painting-blender/)
  - Ucupaint Plus pricing and terms are **unverified**.
- `code-addon`: **Layer Painter** (GPL-3, free on GitHub) is "made to bring a workflow similar to … substance painter or armor paint directly inside blender." The changelog shows v2.0.1. Supported Blender version is **not stated**, so treat it as possibly stale. [V] [joshuaKnauber/layer_painter](https://github.com/joshuaKnauber/layer_painter). Older Gumroad listing: [gumroad](https://joshuaknauber.gumroad.com/l/layerpainter) [L]
- `code-addon`: **RyMat** (GPL-3, Blender 4.0+, marked **"Unstable"/beta**). Layer-based material UI, one-click high-to-low mesh-map baking, projection decals, channel-packed export, no telemetry. [V] [LoganFairbairn/RyMat](https://github.com/LoganFairbairn/RyMat)
- `code-addon`: **Philogix PBR Painter**, a Substance-like layer and smart-material painter for Blender. Only a docs repo was found, and its licence and price are **unverified** (probably commercial). [V-search metadata] [philogix/Philogix-PBR-Painter-Docs](https://github.com/philogix/Philogix-PBR-Painter-Docs)

**Baking (AO / curvature / cavity to drive painted edge wear)**
- `code-addon`: **Ucupaint 2.4.9 bake types:** curvature, thickness, wireframe (see above). [V]
- `code-addon`: **TexTools** (open source; LICENSE.txt, licence type not confirmed; widely reported as GPL).
  - UV layout tools, texel density, Color ID and "multiple out-of-the-box Texture Baking modes".
  - Latest release **1.6.1 (13 Mar 2024)**; "fully compatible with Blender 3.2 and later".
  - Last commits on **2 Dec 2024**; a 28 Nov 2024 commit "Adapt bake module to 4.3 Principled BSDF changes."
  - **No 4.2-extension or 5.x mentions.**

  [V] [franMarz/TexTools-Blender](https://github.com/franMarz/TexTools-Blender) · [releases](https://github.com/franMarz/TexTools-Blender/releases) · [commits](https://github.com/franMarz/TexTools-Blender/commits/master)
  - Community **Blender 5.x compatibility fork** (GPLv3, created June 2026, 0 stars, so unproven): [hieult0806/TexTools-Blender5](https://github.com/hieult0806/TexTools-Blender5) [V-search metadata]
- `code-addon`: **Bake Wrangler**, a node-based baking system that replaces the default baking UI. The thread title mentions "ver b0.9.4 curvy/cavity". The documentation repo is GPL-3. Free vs. paid status is **unverified**. [L] [BlenderArtists thread](https://blenderartists.org/t/bake-wrangler-node-based-baking-tool-set-ver-b0-9-4-curvycavity/1187732) · [V] [netherby/bakewrangler-doc](https://github.com/netherby/bakewrangler-doc)
- `code-addon`: **EasyBake**, a texture-baking UI in the 3D viewport. **Last commit 26 Oct 2022, so stale.** [V] [leukbaars/EasyBake](https://github.com/leukbaars/EasyBake/commits/master)
- `code-addon`: **Principled-Baker**, which bakes PBR textures "with a few clicks". **Last commit 10 Nov 2020, so abandoned.** [V] [danielenger/Principled-Baker](https://github.com/danielenger/Principled-Baker/commits/master)
- `code-addon`: **Grungit** adds wear and tear with one click (Gumroad; price and status unverified). [L] [gumroad](https://abdoubouam.gumroad.com/l/grungit)

**UV unwrapping / packing for stylized work**
- `code-addon`: **TexTools**, see above (UV rectify, straighten, align, texel density).
- `code-addon`: **Magic UV**. The README still lists only "Blender 2.7x/2.8" and says it was "included on Blender itself". Its 4.2+/Extensions status is **unverified**. [V] [nutti/Magic-UV](https://github.com/nutti/Magic-UV)
- `code-addon`: **DreamUV**, viewport UV manipulation tools. [L] [leukbaars/DreamUV](https://github.com/leukbaars/DreamUV)
- `code-addon`: **UV-Packer**, a free automatic UV packer for Blender. [L] [uv-packer.com/blender](https://www.uv-packer.com/blender/)
- `code-addon`: **Texel Density Checker**. [L] [mrven/Blender-Texel-Density-Checker](https://github.com/mrven/Blender-Texel-Density-Checker)
- `course(paid)` / paid add-on: **UVPackmaster**. Paid GPU packer, **no URL found this session**.

**Procedural painterly / brushstroke tools (texture-space or object-space)**
- `code-addon`: **Brushstroke Tools (Blender Studio).** Free Geometry Nodes tool from Project Gold that generates and manages layers of 3D brushstrokes, either filling the surface procedurally or drawn onto it. Licence and minimum Blender version are **unverified** (believed to be 4.3+ via the Extensions platform). [S] [CG Channel](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/) · [Project Gold](https://studio.blender.org/projects/gold/)
- `code-addon`: **Flow Map Painter** (GPL-3), a brush tool for painting flow maps in 2D, texture and vertex paint. Useful for steering stroke direction in shaders or Geometry Nodes. The README says **"DEPRECATED IN BLENDER VERSION 5.0.0"** and a refactor is in progress. [V] [ClemensBeute/flow_map_painter](https://github.com/ClemensBeute/flow_map_painter)
- `code-addon`: **Malt** (MIT), "a fully customizable real-time rendering framework for animation and illustration" (NPR) for the latest stable Blender. It offers GLSL and Python pipelines but no dedicated paint or brush features. [V] [bnpr/Malt](https://github.com/bnpr/Malt)
- `code-addon` / `tutorial`: **threejs-stylized-paint-shader** (MIT).
  - A Three.js port of **Gabriel de Laubier's stylized paint shader**.
  - Procedural brush strokes are anchored to surface positions with normal, size and direction, using **"triplanar fields that remain attached to surfaces"** with mip-based distance attenuation. Strokes foreshorten rather than face the camera.
  - Also: painted reflections, broken outlines and eroded shadow masks.
  - A good reference for porting to Blender shader or Geometry Nodes.

  [V] [SeloSlav/threejs-stylized-paint-shader](https://github.com/SeloSlav/threejs-stylized-paint-shader) · original breakdown [cyn-prod.com](https://cyn-prod.com/stylized-paint-shader-breakdown) [L]
- `code-addon`: **cymatics**, a Blender NPR surface shader plus a 14-stage compositing chain tagged "painterly". New (Aug 2026, about 2 stars), so unproven. [V-search metadata] [infinition/cymatics](https://github.com/infinition/cymatics)
- `asset`: **BNPR shaders**, a sketch and toon shader collection. [L] [blendernpr.org/downloads](https://blendernpr.org/downloads/)
- `course(paid)`/asset: **Painterly Bundle (3 Methods)** on Superhive (paid; contents and price unverified). [S] [Superhive](https://superhivemarket.com/products/painterly-bundle-3-methods)

**Screen-space painterly (post-process) vs. texture-space**
- `code-addon`: **Blender native Kuwahara compositor node.** Two variations: **Classic** ("fast but less accurate", with a High Precision option) and **Anisotropic** ("accurate but slower", with Uniformity, Sharpness 0–1 and Eccentricity 0–2 "directed along edges"). Size defaults to 6 px. Runs on GPU and CPU, using summed-area tables for large radii. [V] [Blender source: node_composite_kuwahara.cc](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/composite/nodes/node_composite_kuwahara.cc)
- `code-addon`: Kuwahara and oil-paint implementations for other hosts:
  - TouchDesigner: [TD-Anisotropic-Kuwahara](https://github.com/yeataro/TD-Anisotropic-Kuwahara), implementing Kyprianidis' anisotropic Kuwahara
  - Godot: [godot-kuwahara](https://github.com/PeterEve/godot-kuwahara)
  - Unreal: [noxtgm/kuwahara-filter](https://github.com/noxtgm/kuwahara-filter)
  - Arnold imager (C++/OpenCV, 2025): [kuwahara-arnold-imager](https://github.com/JsnMertens/kuwahara-arnold-imager)
  - Unity URP: [UnityURP_Kuwahara](https://github.com/TxN/UnityURP_Kuwahara)
  - Python: [pykuwahara](https://github.com/yoch/pykuwahara)
  - Unity oil-paint demo plus tutorial: [danlivings/oil-painting-effect-shader-unity](https://github.com/danlivings/oil-painting-effect-shader-unity) with blog [danlivings.co.uk](https://danlivings.co.uk/blog/oil-painting-effect-shader-unity) [L]

  All [V-search metadata].

**Brushstroke / painterly texture generation code (image to strokes; usable to generate painted texture images)**
- `code-addon`: **Stylized Neural Painting** (CVPR 2021, PyTorch). Outputs **stroke parameters** (vector, `.npz`) for oil-paint, watercolour, marker and tape brushes, with Colab notebooks. Licence is **CC BY-NC-SA 4.0**, so **non-commercial only**. [V] [jiupinjia/stylized-neural-painting](https://github.com/jiupinjia/stylized-neural-painting)
- `code-addon`: **Paint Transformer** (ICCV 2021), a feed-forward neural painter with stroke prediction. Re-implementation: [Huage001/PaintTransformer](https://github.com/Huage001/PaintTransformer). Official PaddlePaddle version: [wzmsltw/PaintTransformer](https://github.com/wzmsltw/PaintTransformer). [V-search metadata; licences not checked]
- `code-addon`: **Neural Painters** (PyTorch), "a learned differentiable constraint for generating brushstroke paintings". [V-search metadata] [reiinakano/neural-painters-pytorch](https://github.com/reiinakano/neural-painters-pytorch)
- `code-addon`: **PyPainterly**, a Python version of **Aaron Hertzmann's Painterly** stroke-based rendering algorithm: [pschaldenbrand/PyPainterly](https://github.com/pschaldenbrand/PyPainterly). Also [DylanHIJ/Painterly-Rendering](https://github.com/DylanHIJ/Painterly-Rendering) ("curved brush strokes of multiple sizes") and [dariusk/painterly-textures](https://github.com/dariusk/painterly-textures) (2013 JS, legacy). [V-search metadata]

**Free brushes and texture libraries**
- `asset`: **Poly Haven** textures: "high quality scanned textures for free", **CC0**. [L] [polyhaven.com/textures](https://polyhaven.com/textures)
- `asset`: **ambientCG**: "hundreds of PBR materials and textures for free under the Public Domain license". [L] [ambientcg.com](https://ambientcg.com/)
- `asset`: other free PBR or photo-texture libraries [L]:
  - [cgbookcase](https://cgbookcase.com/textures/)
  - [ShareTextures](https://www.sharetextures.com/)
  - [Texture.Ninja](https://texture.ninja/), public-domain photos
  - [3DTextures.me](https://3dtextures.me/)
  - [FreePBR](https://freepbr.com/)
  - [AMD MaterialX Library](https://matlib.gpuopen.com/main/materials/all)
  - [Substance Share](https://share.substance3d.com/) (status after Adobe's changes unverified)
  - [BlenderKit](https://www.blenderkit.com/), assets, materials and **alpha brushes** with mixed free and paid tiers
- `asset`: **Krita brush packs:**
  - [portnov/krita-brushes](https://github.com/portnov/krita-brushes), "several brush packs for Krita"
  - [brushConverter](https://github.com/yxm1122/brushConverter), converts Photoshop `.abr` sets to Krita `.kpp`/`.bundle` (new, Aug 2026, unproven)
  - [mypaint-brushes](https://github.com/mypaint/mypaint-brushes)

  [V-search metadata]

**Substance interop (if mixing free Blender with paid Substance)**
- `code-addon`: [passivestar/substance-tools](https://github.com/passivestar/substance-tools), a Blender to Substance Painter export helper. **Archived.** [V-search metadata]
- `code-addon`: [DigiKrafting/blender_addon_substance_painter](https://github.com/DigiKrafting/blender_addon_substance_painter), a bridge. Status unverified.

**Curated lists (good starting points)**
- `documentation`: [awesome-blender](https://github.com/agmmnn/awesome-blender) [V] and [magictools](https://github.com/ellisonleao/magictools) [V]

### Inferences
- **Most future-proof free stack for Blender 5.x:** Ucupaint (active, explicitly 5.2/5.3), the native Kuwahara node, Brushstroke Tools (Blender Studio-maintained, presumably kept current), and Material Maker / ArmorPaint as external painters.
- **Treat as stale on 5.x:** TexTools (no commits since Dec 2024), Flow Map Painter (self-declared deprecated in 5.0), EasyBake, Principled-Baker, and probably Magic UV's GitHub README.
- **Texture-space vs. screen-space:**
  - Texture- or object-space approaches (painted UV maps, Ucupaint layers, Brushstroke Tools strokes, triplanar paint fields like de Laubier's) **stay stuck to surfaces** in motion. This is what Arcane's characters show.
  - Screen-space filters (Kuwahara, oil-paint post) are cheap and global but can "swim" in animation, because the strokes don't follow surfaces.
  - The de Laubier/Three.js port explicitly anchors strokes to surfaces and lets them foreshorten, which is a good model for animation.
- Neural stroke generators can make painted **source images** (e.g. from a baked lighting render) to project or UV-paint. The CC BY-NC-SA licence on Stylized Neural Painting rules it out for commercial projects.

### Gaps
- The Brushstroke Tools licence, Extensions URL and supported versions could not be fetched (extensions.blender.org and projects.blender.org blocked).
- The UVPackmaster URL and price were not found. The free vs. paid status of Bake Wrangler is unverified.
- No free Blender add-on dedicated to Arcane-style "painted curvature edge highlights" was found. That effect is typically built from curvature or AO bakes as Ucupaint masks (inference).

---

## Q4. What free tutorials/courses best teach hand-painted texturing for painterly animation (vs. game hand-painted)?

### Takeaway
Free, film-oriented material is thin and scattered. The best verified free resources are:
- the **Arcane S2 texturing talk** (YouTube)
- the 80.lv **"Closer Look at Texturing in Arcane" Parts 1–2** and the **backgrounds** article
- Fortiche artists' ArtStation breakdowns
- **Project Gold** pages and logs, plus the Brushstroke Tools
- 80.lv fan **recreations** of Arcane characters (mostly Substance 3D + Blender)
- for code-minded artists, **de Laubier's stylized paint shader breakdown**

No source fetched in this session explicitly codifies "game hand-painted vs. painterly film". That distinction below is inference.

### Cited Findings
- `talk`: **Arcane S2 texturing: Animating the hand-painted look.** [S] [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84)
- `documentation`: 80.lv **A Closer Look at Texturing in Arcane**, [Part 1](https://80.lv/articles/a-closer-look-at-texturing-in-arcane) and [Part 2](https://80.lv/articles/a-closer-look-at-texturing-in-arcane-part-2), plus **Arcane backgrounds (traditional art + 3D)** on [80.lv](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds) [S]
- `recreation`: 80.lv Arcane-style recreations [S]:
  - Ekko with Substance 3D & Blender: [article 1](https://80.lv/articles/3d-artist-recreates-arcane-s-ekko-with-substance-3d-blender) and [article 2](https://80.lv/articles/learn-how-to-recreate-arcane-s-ekko-with-substance-3d-blender). Per the snippet, "textured in Substance 3D Painter and rendered with Blender, with the character's painterly looks achieved with Substance 3D's built-in brushes."
  - [Stylized prop with Arcane-like graphics (3ds Max + Substance 3D Painter)](https://80.lv/articles/stylized-3d-prop-with-arcane-like-graphics-created-with-3ds-max-substance-3d-painter)
  - [Link reimagined in Arcane style](https://80.lv/articles/how-to-make-a-reimagination-of-zelda-s-link-with-the-iconic-arcane-style)
  - [Game-ready cannon, Arcane-inspired](https://80.lv/articles/creating-a-game-ready-cannon-in-an-arcane-inspired-style)
  - [Game-ready character with Arcane aesthetic](https://80.lv/articles/creating-a-game-ready-character-with-an-arcane-aesthetic)
  - [Jinx with ZBrush](https://80.lv/articles/how-to-model-texture-jinx-from-arcane-with-zbrush)
- `recreation`: The Rookies **Arcane Art Study: Piltover Citizen**. [S] [therookies.co](https://www.therookies.co/entries/39954)
- `recreation`: 80.lv **LD+R fan art: the character from The Witness**. [S] [80.lv](https://80.lv/articles/love-death-robots-fan-art-creating-the-character-from-the-witness)
- `tutorial`: **Texturing in Blender with Ucupaint** (passivestar), a free written walkthrough of the free layer workflow. [S] [passivestar.xyz](https://passivestar.xyz/posts/texturing-in-blender-with-ucupaint/)
- `documentation`: **Ucupaint wiki** (docs and demos). [V] Linked from the [repo](https://github.com/ucupumar/ucupaint); wiki source at [ucupaint-wiki](https://github.com/ucupumar/ucupaint-wiki).
- `tutorial`: **Gabriel de Laubier, Stylized Paint Shader Breakdown** (procedural brushwork shader) [L] [cyn-prod.com](https://cyn-prod.com/stylized-paint-shader-breakdown), with an MIT Three.js implementation to study at [GitHub](https://github.com/SeloSlav/threejs-stylized-paint-shader) [V]
- `tutorial`: **Dan Livings, oil painting effect shader** (Unity post-process, transferable to the Blender compositor). [L] [blog](https://danlivings.co.uk/blog/oil-painting-effect-shader-unity)
- `documentation`: **Project Gold** pages and production logs (some Blender Studio content may require a subscription, unverified). [S] [project](https://studio.blender.org/projects/gold/) · [log #5](https://studio.blender.org/projects/gold/production-log/246/)
- An Arcane-adjacent Gumroad storefront, [Mani Salguero](https://manisalguero.gumroad.com/), appeared in search for Arcane hand-painted textures. Its content and prices are **unverified**. [S]

### Inferences
- **Game hand-painted (WoW / Blizzard style) vs. painterly film (Arcane / Mielgo).** This comparison is **inference, not sourced this session**.
  - Game hand-painted usually bakes **lighting, AO and highlights into the diffuse map**, because real-time budgets and unlit or simple shading demand it. It also leans on small texture sizes and tiling.
  - Film painterly texturing paints **albedo-like colour and brush texture** that is then **lit in the shot**, often with simplified, low-specular shaders. Shot- or camera-specific paint-overs and **projections** (Arcane S2 backgrounds, Mielgo's painted sets) are layered on top.
  - Takeaway: game tutorials teach colour-value painting and stylized form-shading, which is useful. Film tutorials should add projection painting, lighting-consistent painting, and shot-based detailing ("selectively adding detail to areas where characters interact" [S] [80.lv backgrounds](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds)).
- Several 80.lv "Arcane-style" recreations are explicitly **game-ready**, so they skew toward the game approach and should be labelled as such.

### Gaps
- Free **Blender Studio** training on painterly texture painting could not be verified (studio.blender.org blocked).
- No free, structured **course** on film-style painterly texturing was found. YouTube tutorial channels could not be searched or fetched beyond the one talk.
- David Revoy's or other popular free Krita brush packs were not verified this session.

---

## Q5. Paid tools and courses: one-line summaries + links

### Takeaway
The industry-standard paid options are:
- **Adobe Substance 3D Painter/Designer**: layered PBR painting and procedural materials. The commonest tool in Arcane-style fan recreations, and possibly used at Fortiche (unconfirmed).
- **3DCoat**: painting, retopo and UV in one package.
- **Foundry Mari**: high-res film texture painting.
- **Procreate**: iPad painting with 3D painting support.

Prices and URLs were **not fetchable** this session. Product homepages below are marked [K] and must be verified.

### Cited Findings
- `course(paid)`/tool: **Adobe Substance 3D Painter** does layered 3D painting with smart materials and masks, and is used in the Ekko and prop Arcane-style recreations [S] ([80.lv Ekko](https://80.lv/articles/3d-artist-recreates-arcane-s-ekko-with-substance-3d-blender), [80.lv prop](https://80.lv/articles/stylized-3d-prop-with-arcane-like-graphics-created-with-3ds-max-substance-3d-painter)). [K] Homepage: https://www.adobe.com/products/substance3d/apps/painter.html. Subscription or Steam licence; price unverified.
- `course(paid)`/tool: **Adobe Substance 3D Designer** builds node-based procedural materials and could make custom brushstroke or noise generators. [K] https://www.adobe.com/products/substance3d/apps/designer.html. Price unverified.
- `course(paid)`/tool: **3DCoat** combines voxel sculpting, retopology, UV and PBR painting. [K] https://3dcoat.com/. Perpetual and rental licences; price unverified.
- `course(paid)`/tool: **Foundry Mari**, a film-VFX texture painter for very high-res and UDIM work. [K] https://www.foundry.com/products/mari. Price unverified.
- `course(paid)`/tool: **Procreate** (iPad), a one-time-purchase painting app with 3D model painting. [K] https://procreate.com/. Price unverified.
- `course(paid)`/asset: **Painterly Bundle (3 Methods)**, a Blender painterly shading/texturing bundle. [S] [Superhive](https://superhivemarket.com/products/painterly-bundle-3-methods)
- `code-addon` (paid binaries): **ArmorPaint** prebuilt binaries are paid to fund the project. The source is free (zlib). [V] [armortools README](https://github.com/armory3d/armortools)

### Inferences
- For a budget-constrained studio, ArmorPaint plus Krita plus Ucupaint covers most of Substance Painter's layered painting. The exceptions are Substance's smart-material ecosystem and maturity (opinion).
- Mari mainly matters for UDIM-heavy film assets. Arcane-style stylization relies more on brushwork than on resolution.

### Gaps
- Verified current prices for Substance, 3DCoat, Mari, Procreate and UVPackmaster could not be obtained (egress blocked, search budget exhausted).
- **Paid courses** (e.g. CGMA, Schoolism, Gumroad or ArtStation Learning courses on stylized or painterly texturing) could not be searched or verified. None are listed, to avoid inventing URLs.
