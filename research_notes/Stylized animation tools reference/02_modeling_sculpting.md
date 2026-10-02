# Modeling & Sculpting for Stylized/Painterly 3D Animation (Arcane / Project Gold / Mielgo-style)

> **How these notes were researched (read first).** Research date: 2026-10-02. Partway through, the session's shared WebSearch budget ran out, and the network egress proxy blocked full-page fetches from most non-GitHub domains (studio.blender.org, docs.blender.org, developer.blender.org, blender.org, extensions.blender.org, 80.lv, cgchannel.com, awn.com, blog.syncsketch.com, redsharknews.com, and others). So:
> - **GitHub items were checked directly.** Repository metadata (license, last push, stars, archived flag) came from the GitHub API, and README/release pages were fetched in full. These are the most reliable entries.
> - **Non-GitHub items are real URLs returned by the search engine.** Their descriptions come from search-result snippets and summaries, not full-page reads. Such claims are tagged **[snippet]**. Anything that couldn't be pinned to one source is tagged **[unverified]**.
> - Category tags used: `documentation` / `tutorial` / `recreation` / `code-addon` / `asset` / `course(paid)` / `talk`.
> - Version context: the official manual page for the Set Mesh Normal node is titled "Blender 5.2 LTS Manual", so 5.2 LTS is the current LTS as of this writing ([Blender Manual](https://docs.blender.org/manual/en/latest/modeling/geometry_nodes/mesh/write/set_mesh_normal.html)) [snippet].

---

## Q1. Which free/open-source add-ons, scripts, GitHub repos and node groups help modeling for stylized/toon/painterly shading?

### Takeaway
The free core toolkit is mature and maintained:
- **Abnormal** (MIT) and Blender's built-in **Data Transfer modifier / Smooth by Angle / Set Mesh Normal node** for normal control.
- **Lattice Magic** (Blender Studio) for camera-space "cheat" deformation.
- **Brushstroke Tools** (Blender Studio, from Project Gold) for painterly surface strokes.
- **RetopoFlow** (GPL source) for retopology.
- Several Geometry Nodes tree/scene generators.

A new wave of anime-face tools appeared in 2026 (Anime SDF Gen, PersPress, SDF Face Shadow Baker). They require Blender 4.5–5.2 and are very young, low-adoption projects. Several older normal-editing add-ons are abandoned.

### Cited Findings

#### Custom-normal editing (code-addon)
- **Abnormal** (bnpr/BlenderNPR): Blender add-on "for vertex normal editing".
  - License: MIT. Last push 2025-11-15. ~492 stars. Not archived. — [GitHub bnpr/Abnormal](https://github.com/bnpr/Abnormal)
  - Release history: v1.1.6 (Nov 15, 2025: "Update for 4.5 Vulkan", "Adds normal length scaling based on model edge lengths"), v1.1.5 ("Update for blender 4.1 API changes"), v1.1.4 ("Update for 4.0 api changes"). v1.1.2 added "operator to convert custom normals from/to vertex colors". — [Abnormal releases](https://github.com/bnpr/Abnormal/releases)
  - **No release explicitly mentions Blender 5.x.** Treat 4.5 LTS as the last confirmed target.
  - Features: mirror normals, axis alignment, flip/reset, average/smooth, copy/paste normals, "sphereize" (targeted normals), rotate gizmo with incremental steps. — [blender-addons.org: Abnormal](https://blender-addons.org/abnormal/) [snippet]
  - Docs: [Abnormal Wiki (GitBook)](https://bnpr.gitbook.io/abnormal-wiki) — `documentation`
  - Users are asking for alternatives: [Blender Artists: "Is there any alternative addon to Abnormal?"](https://blenderartists.org/t/is-there-any-alternative-addon-to-abnormal/1586463) (thread content not read).
  - Forks exist: [peroperogames/Abnormal](https://github.com/peroperogames/Abnormal), [darocha fork](https://github.com/darocha/blender-normals-addon-Abnormal).
- **Blender-Normal-Editing-Tools** (isathar): split/vertex normal editor with Default/Bent/Smooth/Weighted/Flat/Transfer presets.
  - README says "Blender 2.74-2.79 (needs to be updated for 2.8)". **ABANDONED/OUTDATED.** — [GitHub isathar/Blender-Normal-Editing-Tools](https://github.com/isathar/Blender-Normal-Editing-Tools) — `code-addon`
- **Edit Split Normals** (Oscurart): "Edit normals like meshes". Old tweet-linked tool, listed in awesome-blender; status unknown, likely outdated. — [Twitter/Oscurart](https://twitter.com/Oscurart/status/1243226933464268802) [unverified] — `code-addon`
- **Cleanup utilities** (strip bad imported custom normals, not for authoring):
  - [Remove-Custom-Splitnormals-Blender-Addon](https://github.com/3dhype/Remove-Custom-Splitnormals-Blender-Addon)
  - [BlenderSplitNormalsTool](https://github.com/Lex713/BlenderSplitNormalsTool) ("Blender 4.0+ addon … remove custom split normals in bulk") — `code-addon`
- **"Fix Auto Smooth in Blender 4.1" free add-on**, covered by BlenderNation, April 2024. — [BlenderNation](https://www.blendernation.com/2024/04/03/fix-auto-smooth-in-blender-4-1-with-this-free-add-ion/) [snippet] — `code-addon`
- **Not relevant despite the name:** theoldben/blendernormalgroups replaces *Normal Map shader nodes* to speed up the EEVEE viewport (4.4-compatible). It is not a custom-normal tool. — [GitHub](https://github.com/theoldben/blendernormalgroups)

#### Built-in Blender normal features (documentation)
- **Blender 4.1 removed the "Auto Smooth" property.** It was replaced by a **"Smooth by Angle" modifier** (a node-group asset), and **custom normals no longer require Auto Smooth to be enabled**. — [Blender PR #108014 "Mesh: Replace auto smooth with node group"](https://projects.blender.org/blender/blender/pulls/108014) [snippet]
  - Discussion threads: [Blender Artists thread](https://blenderartists.org/t/blender-4-1-auto-smooth-is-now-a-modifier-only/1488922?page=4) [snippet]; [Issue #115993: different normals in 4.1 with sharp faces](https://projects.blender.org/blender/blender/issues/115993) [snippet]
- **Set Mesh Normal geometry node (Blender 4.5 LTS):** "Mesh custom normals can now be edited with geometry nodes".
  - Two storage modes. **Free** is a plain vector in local space: fast, but does not survive deformation. **Tangent Space** is deformation-aware but slower.
  - Sources: [Blender 4.5 Geometry Nodes release notes](https://developer.blender.org/docs/release_notes/4.5/geometry_nodes/) [snippet]; [Manual: Set Mesh Normal Node (5.2 LTS)](https://docs.blender.org/manual/en/latest/modeling/geometry_nodes/mesh/write/set_mesh_normal.html) [snippet]; [code.blender.org GN workshop, July 2025](https://code.blender.org/2025/07/geometry-nodes-workshop-july-2025/) [snippet]
  - Usage demos: [80.lv: blending normals with Set Mesh Normal in 4.5](https://80.lv/articles/see-what-you-can-do-with-new-set-mesh-normal-node-in-blender-4-5) [snippet]; [Blender Artists: how to set up the node](https://blenderartists.org/t/blender-4-5-how-to-setup-set-mesh-normal-node/1601916) — `tutorial`
  - A third-party node setup is sold/distributed on Gumroad: [ditagdesign SetMeshNormal](https://ditagdesign.gumroad.com/l/SetMeshNormal) (price/licence not captured) [unverified]

#### Face-shadow (SDF / shadow-threshold-map) authoring (code-addon)
- **Anime SDF Gen** (xht8723): "a Blender extension for authoring anime face-shadow threshold textures with editable curves and live preview".
  - Workflow: editable Bézier shadow boundaries, mirrored or independent left/right editing, keyframes across light angles, 360° preview. Exports 8/16-bit PNG or 32-bit EXR with optional RGB packing.
  - License: GPL-3.0-or-later. **Requires Blender 5.2+.** Created 2026-09-15, release v0.14.0, ~1 star. **Very new; unproven.** — [GitHub](https://github.com/xht8723/Anime-SDF-Gen); [v0.14.0 release](https://github.com/xht8723/Anime-SDF-Gen/releases/tag/v0.14.0)
- **sdf_shadow_threshold_map** (akasaki1211): "Create a Shadow Threshold Map by interpolating SDF".
  - Standalone Python (3.10, numpy, opencv) or exe. Input: a folder of progressive shadow masks. Output: 8/16-bit PNG.
  - License: MIT. Last push 2025-07-22. ~128 stars.
  - Algorithm credited to Nagakagachi's blog ([SDF Based Transition Blending for Shadow Threshold Map](https://nagakagachi.hatenablog.com/entry/2024/03/02/140704), Japanese). — [GitHub](https://github.com/akasaki1211/sdf_shadow_threshold_map)
- **blender-sdf-face-shadow-baker** (ReefSnax): a Blender script that "bakes the input masks for an anime-style SDF face shadow map, no hand painting required".
  - Sweeps a light across the face in Cycles, then hands the masks to `ShadowThresholdMap.exe` to get `face_sdf.png`. Output works with Poiyomi, lilToon and UTS (Unity toon shaders).
  - "Tested with Blender 4.5.2 LTS". License: MIT. Created July 2026. — [GitHub](https://github.com/ReefSnax/blender-sdf-face-shadow-baker)
- **NagaSdfTextureToolForUE**: Unreal Engine equivalent for generating SDF/shadow-threshold textures. — [GitHub](https://github.com/nagakagachi/NagaSdfTextureToolForUE) [snippet]
- **Reference shaders that consume face SDF maps** (useful for studying the technique; mostly game-rip oriented):
  - [festivities/Blender-miHoYo-Shaders](https://github.com/festivities/Blender-miHoYo-Shaders): Genshin-style Blender shader, ~1.1k stars, **ARCHIVED**, "for datamined assets".
  - [festivities/Blender-StellarToon](https://github.com/festivities/Blender-StellarToon): Star Rail-style shader for Goo Engine.
  - [NoiRC256/URPSimpleGenshinShaders](https://github.com/NoiRC256/URPSimpleGenshinShaders) (Unity URP).
  - [EricHu33 AnimeShadingPlus: "Face Shadow Map – Creation & Baking Workflow" doc](https://github.com/EricHu33/AnimeShadingPlus-Anime-Toon-Shader/blob/main/Anime%20Shading%20Plus(+)%20User%20Manual%20e9875988ae1e41caa5198370d9cc963d/Face%20Shadow%20Map-%20Creation%20&%20Baking%20Workflow%20d3b8769021e04683a2f2ae4cf16ac810.md) (Unity product; the doc is free to read) — `documentation`

#### Camera-dependent "cheat" deformation and 2D-silhouette tools (code-addon)
- **Lattice Magic** (Blender Studio, by "Mets"): two tools, Tweak Lattice and **Camera Lattice**.
  - Camera Lattice "lets you deform a collection of objects from a particular camera perspective, essentially like Liquify, except it's operating on vertices instead of pixels".
  - Lattice points can't be animated, so the add-on manages shape keys and keyframes for animated "liquify" cheats.
  - Available on the Blender Extensions platform. — [Blender Studio: Lattice Magic](https://studio.blender.org/tools/addons/lattice_magic) [snippet]; [Blender Extensions listing](https://extensions.blender.org/add-ons/latticemagic/) and [version history](https://extensions.blender.org/add-ons/latticemagic/versions/) [snippet]; [source: camera_lattice.py (GitLab)](https://gitlab.com/blender/lattice_magic/-/blob/master/camera_lattice.py); [BlenderNation 2021 coverage](https://www.blendernation.com/2021/06/10/lattice-magic-in-blender-2-9/)
- **PersPress** (a2d4f3s1): "Counter-perspective face correction for Blender".
  - Uses camera-space depth remapping so the head reads as if shot on a telephoto lens, while the body and background keep wide-angle perspective. Exactly the kind of 2D-style camera cheat used in anime and painterly films.
  - Implemented "entirely with Geometry Nodes and drivers", so render farms don't need the add-on. Keeps pre-correction normals and depth as attributes and AOVs.
  - **Blender 5.2 LTS+.** GPL-3.0-or-later. Created July 2026; very low adoption. — [GitHub](https://github.com/a2d4f3s1/perspress)
- **Grease Pencil helpers for drawing in 3D space**, all by Samuel Bernou (Pullusb):
  - [greasepencil_tools](https://github.com/Pullusb/greasepencil_tools): "Pack of extended tool for Grease pencil". Updated 2026-09.
  - [Box_deform](https://github.com/Pullusb/Box_deform): "Deforming box for grease pencil drawing". Last update 2022-12; likely predates the Grease Pencil v3 rewrite **[unverified compatibility]**.
  - [GP_clipboard](https://github.com/Pullusb/GP_clipboard): world-space copy/paste.
  - Also [gomez_poser](https://github.com/dzigaVertov/gomez_poser) (auto rigging and skinning of GP strokes) — `code-addon`

#### Retopology / topology (code-addon)
- **RetopoFlow** (CG Cookie): "a suite of fun, sketch-based retopology tools … geometry which snap to your high poly objects as you draw".
  - v3.4.0, "Blender 3.6 or later". Code is GPL-3.0 and on GitHub (non-code assets are not). The paid version on the website/Superhive funds development. ~3.3k stars, actively updated (2026-10). — [GitHub CGCookie/retopoflow](https://github.com/CGCookie/retopoflow)
  - Separate docs repo is archived: [retopoflow-docs](https://github.com/CGCookie/retopoflow-docs)

#### Sculpt brushes (asset / code-addon)
- **Blender 4.3+ brush assets.** A free 5-brush pack (Dots, Noise, Line, Rock, Voronoi plus a rock displacement map) is pre-set up as 4.3 brush assets and installed via an Asset Library path. "Free for personal and commercial use". — [Patreon post](https://www.patreon.com/posts/blender-brushes-116454657) / [Fab listing](https://www.fab.com/listings/3c8a71eb-76d6-4680-a16b-8f05c7e7bc7c) / [Blendatlas](https://blendatlas.com/products/blender-sculpting-brushes-free-download) [snippet]
- **Rakurri Brush Set**: 9 free rock texture brushes, installed via File > Append > Brush. Described as "very early development". No license file is visible in the README. That append workflow is the **pre-4.3 brush model** [inference: may need re-saving as assets in 4.3+]. — [GitHub](https://github.com/Rakurri/rakurri-brush-set-for-blender)
- **SculptWolf-Essentials**: "Free Blender Sculpt Brushes!", stylized chisel shapes and VDM brushes. Created 2026-01; ~2 stars. — [GitHub](https://github.com/CamouForge/SculptWolf-Essentials)
- **Other free brush packs** (content not inspected): [Wendelin Jacober free sculpt brushes (Gumroad)](https://wendelinjacober.gumroad.com/l/free-blender-sculpt-brushes); [Ryan King free brushes (Gumroad)](https://ryankingart.gumroad.com/l/free-brushes); [Blender Artists "Free Blender Sculpting Brushes" thread](https://blenderartists.org/t/free-blender-sculpting-brushes/1442850)
- **Utilities:**
  - [batch_import_images_to_brushes](https://github.com/raja-muda/batch_import_images_to_brushes): batch-import alphas as sculpt/paint brushes, Blender 4.4+.
  - [eka-blender-createBrush](https://github.com/eka-afk/eka-blender-createBrush): brushes from grayscale images.
  - [Sculpt Alphas Manager (Blender Artists)](https://blenderartists.org/t/sculpt-alphas-manager/1200725): old, status unknown.

#### Hair (code-addon / asset)
- **Daniel Bystedt's free hair-cards-from-curves setup**: a Geometry Nodes setup converting curve hair into card geometry. Blender 3.6+, free. — [CG Channel (Mar 2024)](https://www.cgchannel.com/2024/03/daniel-bystedts-free-blender-add-on-creates-hair-cards-from-curves/) [snippet]; [80.lv](https://80.lv/articles/free-hair-cards-from-curves-setup-for-blender) [snippet]
- **Nino DefoQ free GN generators**: [Hair](https://ninodefoq.gumroad.com/l/hairgeometrynodes), [Braid](https://ninodefoq.gumroad.com/l/braidify), [Cornrow](https://ninodefoq.gumroad.com/l/cornrows) (listed as free in awesome-blender). — [awesome-blender README](https://github.com/agmmnn/awesome-blender)
- **Clumping** (chunky painterly locks): Blender's hair-curves **Clump Hair Curves** node groups strands into locks, with clump size/strength controls. — [yelzkizi guide](https://yelzkizi.org/blender-hair-tutorial-hair-cards/) [snippet; low-quality aggregator site, verify against the official manual]
- **Blendatlas GN packs** (pricing not captured): [Hair Card Node Pack](https://blendatlas.com/products/a-hair-card-node-pack); [Hair Curves to Hair Cards Converter](https://blendatlas.com/products/hair-curves-to-hair-cards-converter-blender-geometry-nodes-36) [snippet]
- **Tiny 2026 GitHub hair-card tools** (0 stars; experimental):
  - [hair-card-deform-edit](https://github.com/tanakorn2544/hair-card-deform-edit): "Blender 4.2 add-on: edit hair cards in the space you see when a Curve modifier is bending them".
  - [hair_armature_gen](https://github.com/PsyDreamer-3D/hair_armature_gen): generates a guide armature from a hair-card mesh.

#### Procedural stylized environments (Geometry Nodes)
- **Brushstroke Tools** (Blender Studio, from Project Gold): "a set of Geometry Nodes-based tools … for creating a variety of stylized looks in asset production".
  - Fills a whole mesh surface with procedural strokes, or lets you draw strokes on it, organized in layers with per-layer shape, style and material.
  - On the Blender Extensions platform. — [Blender Extensions: Brushstroke Tools](https://extensions.blender.org/add-ons/brushstroke-tools/) [snippet]; [CG Channel Nov 2024](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/) [snippet]; [Gold: Brush Strokes asset page](https://studio.blender.org/projects/gold/3c7fb86d72b766/) [snippet] — `code-addon`
- **GeometryNodes-Stylized-Scene-Generator** (Shahriyar Shahrabi / IRCSS): procedural stylized trees, rocks, landscape, houses, roads, rivers, fences and smoke, with procedural color control.
  - Tested on Blender 3.4.1; **no license stated**. Companion write-up: [Medium: Blender Geometry Nodes — Create Stylized Scenes](https://shahriyarshahrabi.medium.com/blender-geometry-nodes-create-stylized-scenes-e336967c7f84). — [GitHub](https://github.com/IRCSS/GeometryNodes-Stylized-Scene-Generator)
  - Same author: [Trees-With-Geometry-Nodes-Blender](https://github.com/IRCSS/Trees-With-Geometry-Nodes-Blender) — `code-addon`/`tutorial`
- **Stylized Fantasy Tree Generator** (RC12): free, fully procedural GN; basic procedural bark and generated UVs. — [Gumroad](https://rc12.gumroad.com/l/fantasytree); [80.lv](https://80.lv/articles/free-stylized-tree-generator-made-with-geometry-nodes-in-blender) [snippet]; [BlenderNation May 2024](https://www.blendernation.com/2024/05/25/free-download-stylized-tree-generator/) [snippet]
- **Other tree tools:**
  - [Easy Tree (Blender Extensions)](https://extensions.blender.org/add-ons/easy-tree/): GN-based procedural trees [snippet].
  - [Albero by David Cescatti (80.lv)](https://80.lv/articles/geometry-nodes-powered-tree-generator-for-blender) [snippet; pricing not captured].
  - [Blender Artists "Fantasy style tree generator with GN"](https://blenderartists.org/t/fantasy-style-tree-generator-with-geometry-nodes/1356968).
- **MTree / modular_tree** (Maxime Herpin): function-based (not GN) tree generator. Add-on GPLv3, core library MIT. ~1.3k stars, 117 open issues. README says Blender 2.93+ for add-on development; **current 4.x/5.x support not confirmed**. — [GitHub](https://github.com/MaximeHerpin/modular_tree)
- **tree-gen** (friggog): "procedural generation of tree models in blender". Status not checked. — [GitHub](https://github.com/friggog/tree-gen) [unverified maintenance]
- **Pleebs free GN generators**: [Bush](https://pleebs.gumroad.com/l/BushDraw), [Wall](https://pleebs.gumroad.com/l/WallDraw), [Cobble](https://pleebs.gumroad.com/l/cobbledraw). Also [Nino DefoQ Moss](https://ninodefoq.gumroad.com/l/mossify) and [Snow](https://ninodefoq.gumroad.com/l/Snowify). [Gscatter](https://www.graswald3d.com/gscatter) is "Artist-friendly scattering for free". — via [awesome-blender](https://github.com/agmmnn/awesome-blender)
- **Official GN demo files** (procedural buildings, hex-grid map): [blender.org demo files](https://www.blender.org/download/demo-files/#geometry-nodes) — `documentation`

#### NPR-oriented Blender builds and frameworks (context; render-side, but they affect modeling choices)
- **Goo Engine** (Dillon Goo Studios): "Custom build of blender with some extra NPR features". The README mentions four custom EEVEE shader nodes and Light Groups. GPL-3. Prebuilt downloads via Patreon. ~1.4k stars. — [GitHub](https://github.com/dillongoostudios/goo-engine)
- **Malt** (BNPR): "Render framework for NPR". License "Other". Last push 2026-03-29. ~1.1k stars. — [GitHub](https://github.com/bnpr/Malt)

#### Meta-lists
- [agmmnn/awesome-blender](https://github.com/agmmnn/awesome-blender): ~7.4k stars, updated daily.
- [devanshutak25/3d-resources](https://github.com/devanshutak25/3d-resources): "Curated, CC0 reference hub … 3,400+ tools, assets, and tutorials"; ~975 stars.

### Inferences
- **Anime-face normal toolchain for Blender 4.5–5.x:** Abnormal (manual sculpting of normals), Data Transfer from proxy spheres (bulk smoothing), and the native Set Mesh Normal node (procedural or animated normals that can be rigged).
  - The Set Mesh Normal node's Tangent Space mode is the one to use on deforming characters; Free mode is for static props.
- **Face-shadow maps:** the free pipeline is: bake light-sweep masks (ReefSnax script), then interpolate (akasaki1211). Anime SDF Gen collapses this into one hand-authoring tool, but it only targets 5.2+ and is weeks old.
- **Highest abandonment risk:** isathar Normal Editing Tools, Edit Split Normals, Box_deform (pre-GPv3), Sculpt Alphas Manager, and pre-4.3 append-style brush packs.
- **Most project-relevant free add-ons for an Arcane/Mielgo look:** Lattice Magic's Camera Lattice and PersPress. They implement per-shot "drawn" distortions that are standard in 2D but rare in 3D tools.

### Gaps
- No verified Blender 5.x compatibility statement for Abnormal, Lattice Magic, Brushstroke Tools or MTree; the extension pages couldn't be fetched.
- Blender's built-in sculpt brush "Essentials" library (4.3) and any official Blender Studio brush-asset packs could not be verified this session.
- The Polycount wiki pages on vertex normals/toon shading could not be reached. Only a forum thread was found: [Polycount: Blender 2.8 normal transfer tricky case](https://polycount.com/discussion/211369/solved-blender-2-8-normal-transfer-a-tricky-case).
- No free GN "clumped painterly hair" node group with a clear open license was found beyond Blender's own hair nodes.

---

## Q2. What specific techniques control shading on faces (normal transfer, custom split normals, face shadow maps / SDF face shadows), and where are the best free tutorials and docs?

### Takeaway
Three established techniques:
1. **Proxy-shape normal transfer.** A Data Transfer modifier copies "Custom Normals" from a smooth sphere/ellipsoid proxy. Face Corner Data is on, mapping is Nearest Corner and Best Matching Face Normal.
2. **Hand-edited split normals.** Pioneered publicly by Arc System Works for Guilty Gear Xrd (GDC 2015); done in Blender with Abnormal.
3. **Face shadow threshold maps (SDF).** A texture that encodes at which light angle each texel goes into shadow.

Since Blender 4.1, custom normals no longer need Auto Smooth. Since 4.5, normals can also be authored procedurally with the Set Mesh Normal node.

### Cited Findings

#### Normal transfer from proxies (tutorial / documentation)
- **Step-by-step:** add a DataTransfer modifier, pick the source object, tick Face Corner Data, select Custom Normals. — [Yarsa DevBlog: Transferring Normal Data in Blender](https://blog.yarsalabs.com/normal-transfer-in-blender/) [snippet] — `tutorial`
- **Cel-shading-specific settings:** Face Corner Data, Custom Normals, mapping "Nearest Corner and Best Matching Face Normal". — [VRC Library (Trixxed): Data Transfer Normals for Cel-Shading](https://vrclibrary.com/wiki/books/random-assorted-tips-with-trixxed/page/normals-data-transfer-normals-for-cel-shading) [snippet] — `tutorial`
- **Older tutorials say to enable "Auto Smooth".** That step is **obsolete in 4.1+**, where Auto Smooth was removed and custom normals work without it. — [3DSkillUp: Blender Data Transfer Modifier](https://3dskillup.art/blender-data-transfer-modifier/) [snippet] vs. [Blender PR #108014](https://projects.blender.org/blender/blender/pulls/108014) [snippet] — `tutorial` (partially outdated)
- **Video:** "Editing normals for shading anime" (Blender 3.3), using Abnormal plus Data Transfer on face and hair. — [YouTube](https://www.youtube.com/watch?v=1puHJSkZy24) [snippet] — `tutorial`
- **Manual reference** for the modifier (an old mirror; the current URL on docs.blender.org couldn't be fetched): [Data Transfer Modifier — Blender Manual (mirror)](http://builder.openhmd.net/blender-hmd-viewport-temp/modeling/modifiers/modify/data_transfer.html) [snippet] — `documentation`
- **Commercial alternative** that avoids proxy-mesh interpolation problems: "Anime Face Proxy System" from Fondant Tools. — [fondanttools.gumroad.com](https://fondanttools.gumroad.com/) [snippet; price not captured] — `course(paid)`/paid tool

#### Hand-authored normals: the Guilty Gear Xrd reference (talk)
- **GDC 2015, Junya Motomura (Arc System Works), "GuiltyGearXrd's Art Style: The X Factor Between 2D and 3D".** The team "shunned mathematical accuracy to create perfectly consistent cel shading", and normals were done by hand because it looked better than procedural results. — [GDC Vault](https://www.gdcvault.com/play/1022031/GuiltyGearXrd-s-Art-Style-The); [Arc System Works: talk available online](https://www.arcsystemworks.com/guilty-gear-xrds-art-style-the-x-factor-between-2d-and-3d-talk-from-gdc-2015-is-now-available-online/); [Game Developer write-up](https://www.gamedeveloper.com/art/see-i-guilty-gear-xrd-i-s-striking-2d-3d-art-deconstructed-at-gdc-2015) [snippet] — `talk`
- Motomura's techniques were also covered in a Blender context. — [BlenderNation 2015](https://www.blendernation.com/2015/07/26/junya-c-motomura-behind-the-scenes-of-guilty-gear-xrd/) [snippet] — `talk`

#### Procedural normals (documentation)
- **Set Mesh Normal node (4.5+):** stores a normal per mesh element "to control shading appearance". Free and Tangent Space storage modes. It can blend two meshes' shading without changing topology. — [Blender 4.5 GN release notes](https://developer.blender.org/docs/release_notes/4.5/geometry_nodes/) [snippet]; [80.lv demo](https://80.lv/articles/see-what-you-can-do-with-new-set-mesh-normal-node-in-blender-4-5) [snippet]

#### Face shadow threshold maps / SDF (documentation / tutorial / code)
- **Theory:** Nagakagachi's Japanese blog post on SDF-based transition blending for shadow threshold maps is the algorithmic source credited by akasaki1211's tool. — [ながむしメモ](https://nagakagachi.hatenablog.com/entry/2024/03/02/140704)
  - Japanese coverage of his UE5 toolset: [3dnchu](https://3dnchu.com/archives/sdf-generator-for-unreal-engine-nagakagachi/) [snippet]
- **Free practical workflows:**
  - [akasaki1211 README](https://github.com/akasaki1211/sdf_shadow_threshold_map/blob/main/README.md)
  - [ReefSnax baker README](https://github.com/ReefSnax/blender-sdf-face-shadow-baker): Blender light-sweep mask bake, then SDF interpolation.
  - [EricHu33 Face Shadow Map creation & baking workflow](https://github.com/EricHu33/AnimeShadingPlus-Anime-Toon-Shader/blob/main/Anime%20Shading%20Plus(+)%20User%20Manual%20e9875988ae1e41caa5198370d9cc963d/Face%20Shadow%20Map-%20Creation%20&%20Baking%20Workflow%20d3b8769021e04683a2f2ae4cf16ac810.md) (Unity-oriented).
- **Authoring tool:** [Anime SDF Gen](https://github.com/xht8723/Anime-SDF-Gen) (Blender 5.2+), described under Q1.

### Inferences
- **Choosing an approach for an Arcane/Gold-like painterly project** (rather than strict anime cel):
  - Proxy normal transfer gives soft, simplified light falloff on faces, and that softness is what painterly shading wants.
  - SDF face maps matter mainly when using hard 2-tone cel shading with a key light that moves.
  - Painted lighting (as Arcane reportedly did, see Q3) reduces the need for either.
- **Production tip:** keep the proxy normal transfer as a live modifier above the Armature modifier, or rig the proxy along with the head, so normals survive facial deformation. Applying it bakes normals that break once the face deforms. This is general practice, not sourced here **[unverified]**.

### Gaps
- **"Y-Bot" anime face-normal technique:** no source found under that name. The likely canonical references are Guilty Gear Xrd (hand-edited normals) and the proxy-sphere transfer method. Ask the requester what "Y-Bot" refers to.
- Couldn't fetch the official Blender Manual pages for Normals editing, Data Transfer or Smooth by Angle, so the 5.2 UI labels are unconfirmed.
- No free, rigorous written tutorial specifically on painterly (non-anime) face normal control was found.

---

## Q3. How did Arcane / Project Gold / Mielgo-style productions approach modeling (simplified planes, exaggerated proportions, painted rather than modeled detail)?

### Takeaway
All three reference productions keep modeled detail low and push detail into **paint**:
- **Arcane** reportedly hand-painted all textures and used projected paintings for backgrounds.
- **Project Gold's** look comes from Geometry-Nodes brushstrokes layered over relatively simple sculpted/retopologized forms.
- **Mielgo** describes a "very simplified" character look, intentionally removing details, with many shots painted over.

Source quality is weak for Arcane's specific modeling software: aggregator sites conflict and primary interviews couldn't be fetched.

### Cited Findings

#### Arcane (Fortiche)
- **[unverified]** "Every texture is completely painted, and backgrounds use projected paintings rather than traditional 3D modeling". Concept paintings guided 3D modelers and texture artists, and "four or five 2D artists" made most effects.
  - This came from a search-engine summary whose source set included [iAnimate podcast with Alexis Wanneroy](https://ianimate.net/animationpodcast/arcane-magic-secrets-fortiche-lead-alexis-wanneroy-podcast), [SyncSketch: The Making of Arcane (Wanneroy interview)](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) and [AWN: conversation with Pascal Charrue & Alexis Wanneroy](https://www.awn.com/animationworld/unveiling-arcane-conversation-pascal-charrue-and-alexis-wanneroy). The exact originating page couldn't be confirmed (fetch blocked). — `talk`/interview
- **Talk: "Arcane S2 texturing: Animating the hand-painted look".** A YouTube talk on how S2 textures were painted and animated. — [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84) [snippet; title only] — `talk`
- **Pipeline article:** [RedShark News: "Why Netflix's Arcane looks so good: How Fortiche ramped up the animation pipeline"](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline). The snippet says artists "painted highlights and shadows directly onto textures" and that "forms are not symmetrical, angles are super defined, and brushstrokes are visible but not noisy". [snippet; attribution within the search summary uncertain]
- **Software used: CONFLICTING, low-quality sources.**
  - [yelzkizi.org](https://yelzkizi.org/what-3d-program-did-arcane-use/): Maya base meshes, ZBrush detailing, retopo in Maya, 3ds Max for complex gadgets.
  - Another search summary: Maya + Photoshop hand-painted textures + Nuke compositing.
  - Both are aggregator-level. yelzkizi.org appears to be SEO content and should not be trusted without a primary source. **Treat Arcane's software stack as unverified.**
- **Recreations / study pieces:**
  - [80.lv: How to Model & Texture Jinx from Arcane with ZBrush](https://80.lv/articles/how-to-model-texture-jinx-from-arcane-with-zbrush)
  - [80.lv: Arcane-inspired hand-painted 3D character](https://80.lv/articles/have-a-look-at-this-amazing-arcane-inspired-hand-painted-3d-character) [snippet] — `recreation`
- **Other interviews** (season 2, mostly story-focused): [IndieWire: Christian Linke interview](https://www.indiewire.com/features/animation/arcane-season-2-co-creator-christian-linke-interview-netflix-1235063175/) [snippet] — `talk`

#### Project Gold (Blender Studio)
- **What it is:** "a technical and artistic showcase, focused on highly stylized rendering and animation". It began as a short directed by Jericca Cleland and was refocused into a showcase for the painterly tools; Cleland continues the full short.
  - The **Brushstroke Tools** extension is the main released tool. The technique is described in the paper "Creating Tools for Stylized Design Workflows" and the BCON 2024 talk "Procedural Oil Painting".
  - Sources: [Project Gold page](https://studio.blender.org/projects/gold/) [snippet]; [Project Gold Premiere blog](https://studio.blender.org/blog/project-gold-premiere/) [snippet]; [Announcing Project Gold](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/) [snippet]
- **Production logs:** 3D artist Julien Kaspar documented character retopology, "refining sculpts and testing new custom modifiers and tools to speed up the retopo process". He finalized body topology for the character **Mikassa** for rigging/animation tests. — [Gold Production Logs, Nov 2023](https://studio.blender.org/projects/gold/production-logs/2023/nov/) [snippet] — `documentation`
- **Blog article "Gold: Boat Modeling"** (developing and modeling the boat) is referenced in search results. **URL not captured**; find it via the [Gold project page](https://studio.blender.org/projects/gold/) [snippet].
- **Training:** "Stylized Rendering with Brushstrokes" workshop. — [Blender Studio training](https://studio.blender.org/training/stylized-rendering-with-brushstrokes/) [snippet] — `tutorial` (Blender Studio; access tier not verified)
- **Film and project files** were released together. — [80.lv: Blender Studio Released Project Gold](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files) [snippet]; [Creative Bloq: how to watch Project Gold and get the project files](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools) [snippet]; [YouTube: Project Gold](https://www.youtube.com/watch?v=nV_awXI9XJY) — `asset`/`talk`

#### Alberto Mielgo (Jibaro; The Witness and The Windshield Wiper not covered)
- **Jibaro production:**
  - Characters were built from scratch and rigged. Water and jewelry simulations were "very much a nightmare". Texturing and rendering the golden siren and Jibaro's armor (plus two dozen knights) was the hardest part.
  - Jibaro is "essentially a 3D film where many shots are painted like a painting". Some shots built and lit a whole 3D forest, with lots of 2D in post.
  - The character look is "very simplified". Mielgo "intentionally removed details they didn't need" for a more pleasant image. Dancers were used as motion reference for the knights.
  - Sources: [SlashFilm interview](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/); [80.lv: development process behind Jibaro](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro); [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/) [snippet; the search summary combined these, so per-quote attribution is uncertain] — `talk`/interview
- **Toolset:** Maya (animation), Houdini (simulation), Arnold (rendering). — [Game Rant interview](https://gamerant.com/interview-alberto-mielgo-love-death-and-robots-volume-3-jibaro-netflix/) [snippet]
- **More interviews:** [80.lv: Mielgo on creating LD+R short episodes](https://80.lv/articles/alberto-mielgo-talks-specifics-of-creating-love-death-robots-short-episodes); [Screen Rant](https://screenrant.com/love-death-robots-vol-3-alberto-mielgo/); [Gold Derby video interview](https://www.goldderby.com/feature/alberto-mielgo-love-death-robots-jibaro-video-interview-1204988524/); [Netflix official Making of Jibaro clip (YouTube)](https://www.youtube.com/watch?v=kPRMOFQ23TM) — `talk`

#### Shared stylized-character modeling method (Blender Studio)
- **Julien Kaspar's "Stylized Character Workflow"** covers the whole pipeline for a film-production stylized character, "with a strong focus on design, sculpting & retopology", using the character **Rain**.
  - Built for Blender 2.8/2.81. Lessons include primitive-body blocking, wrinkles and folds, and clean retopology.
  - Sources: [Course page](https://studio.blender.org/training/stylized-character-workflow/); [Creating a Primitive Body](https://studio.blender.org/training/stylized-character-workflow/5d7f7cf055ccaf1a4a78102d/); [Sculpting Wrinkles & Folds](https://studio.blender.org/training/stylized-character-workflow/5d7f9598e7de39444aa9171f/); [Clean Retopology chapter](https://studio.blender.org/training/stylized-character-workflow/chapter/5d384edea5b8f5c2c32c8507/); [Retopology Setup](https://studio.blender.org/training/stylized-character-workflow/5e5408188faf011a381510da/); [Live: Retopology Finale](https://studio.blender.org/training/stylized-character-workflow/live-retopology-finale/) [snippet] — `course` (Blender Studio)
  - Free ~30-minute YouTube overview: [YouTube](https://www.youtube.com/watch?v=f-mx-Jfx9lA); author's blog post: [ArtStation](https://julienkaspar.artstation.com/blog/X4ar/stylized-character-workflow-blender-2-8-tutorial) — `tutorial`
- **Topology for deformation:** [Live Retopology at BCON22](https://studio.blender.org/blog/live-retopology-at-bcon22/) [snippet]. Also [Realistic Character Workflow: Retopology & Layering](https://studio.blender.org/training/realistic-human-research/chapter/retopology-layering/) for deformation-ready layering [snippet] — `talk`/`tutorial`

### Inferences
- **Common modeling philosophy across the three:**
  1. Block with simple, graphic planes and strongly designed (often asymmetric) silhouettes.
  2. Keep topology clean and animation-ready rather than detail-heavy.
  3. Put surface detail, light and "brushwork" into painted textures (Arcane), procedural brushstroke geometry (Gold) or 2D paintover/compositing (Mielgo).
- **For a Blender-based team:** Kaspar's workflow (sculpt → clean retopo → rig-ready) plus Brushstroke Tools plus normal control from Q2 is the closest fully free and documented analogue to these productions.
- **Arcane-specific technical claims** (software, how faces were built) should only be cited from the primary interview pages, once they can be read. Aggregator claims conflict.

### Gaps
- No primary Fortiche technical breakdown of *modeling* (topology density, face construction, normals) was found. SIGGRAPH/Annecy/Substance talks may exist but weren't reachable.
- No sources on modeling in *The Witness* or *The Windshield Wiper*: the WebSearch budget was exhausted before these queries ran.
- Couldn't verify the URLs for the Gold "Boat Modeling" article, the "Creating Tools for Stylized Design Workflows" paper, or the BCON 2024 "Procedural Oil Painting" talk.
- The license of the Project Gold production files (Blender Studio content is generally CC-BY) wasn't verified this session.

---

## Q4. Which paid tools and courses are widely recommended? (one line each with link)

### Takeaway
Paid options cluster in four areas:
- Sculpting software: ZBrush.
- Brush and hair packs on Superhive (formerly Blender Market), ArtStation and Gumroad.
- Specialized anime/normal tools (Fondant Tools).
- Structured courses (Blender Studio subscription, Packt book).

**No prices could be verified this session** (page fetches were blocked); every price below is "not captured".

### Cited Findings
- **ZBrush (Maxon):** industry-standard digital sculpting, reportedly used alongside Maya for stylized characters, including Arcane recreations. — [maxon.net/zbrush](https://www.maxon.net/en/zbrush-1) — paid software; price not captured.
- **Superhive "3000+ Blender Sculpting Brushes. Asset Browser."** Large brush-asset library for the Blender asset browser. — [Superhive](https://superhivemarket.com/products/600-blender-sculpting-brushes) [snippet] — paid.
- **ArtStation "600+ Blender Sculpting Brushes. Assets Browser."** — [ArtStation Marketplace](https://www.artstation.com/marketplace/p/AYpmb/600-blender-sculpting-brushes-assets-browser) [snippet] — paid.
- **Stylized Hair PRO (Dean Zarkov):** GN-based add-on for procedural stylized hairstyles on hair curves (shape, geometry, materials, ornaments). — [Gumroad](https://deanzarkov.gumroad.com/l/stylized_hair_pro) [snippet] — paid (price not captured).
- **Fondant Tools ("Tools for stylized character creation", incl. Anime Face Proxy System):** sold as a way to avoid unreliable proxy-mesh/data-transfer interpolation on anime faces. — [Gumroad](https://fondanttools.gumroad.com/) [snippet] — paid (assumed; not verified).
- **RetopoFlow (paid build):** purchases on the CG Cookie site/Superhive fund development; GPL source is free on GitHub. — [Superhive/Blender Market listing](https://blendermarket.com/products/retopoflow); [GitHub](https://github.com/CGCookie/retopoflow)
- **Blendatlas hair GN packs:** [Hair Card Node Pack](https://blendatlas.com/products/a-hair-card-node-pack); [Hair Curves → Hair Cards Converter](https://blendatlas.com/products/hair-curves-to-hair-cards-converter-blender-geometry-nodes-36) [snippet] — pricing not captured.
- **Tradigital, "Painterly 3D Tools Inside Blender":** Gumroad storefront for painterly Blender tools. — [tradigital.gumroad.com](https://tradigital.gumroad.com/) [snippet; contents not inspected]
- **Brush Manager for Blender:** organizes and stores custom brush libraries. — [Gumroad](https://gumroad.com/l/zLBPz) (via [awesome-blender](https://github.com/agmmnn/awesome-blender)); likely pre-4.3 **[unverified compatibility]**.
- **Albero tree generator (David Cescatti):** GN tree generator with presets. — [80.lv](https://80.lv/articles/geometry-nodes-powered-tree-generator-for-blender) [snippet; pricing not captured]
- **Courses:**
  - Julien Kaspar's **Stylized Character Workflow** on Blender Studio (subscription platform; tier not verified). — [studio.blender.org](https://studio.blender.org/training/stylized-character-workflow/) — `course(paid)` [unverified paywall]
  - **"Stylized Environments with Blender 4 Geometry Nodes"** (Packt book; companion code repo is free). — [GitHub PacktPublishing](https://github.com/PacktPublishing/Stylized-Environments-with-Blender-4-Geometry-Nodes) — `course(paid)`

### Inferences
- For a free-first studio, almost every paid item has a free counterpart:
  - ZBrush → Blender sculpt mode with 4.3+ brush assets.
  - Stylized Hair PRO → Blender hair curves plus Bystedt's free hair-cards setup.
  - Fondant Tools → Data Transfer plus Abnormal.
  - Paid RetopoFlow → GPL RetopoFlow from GitHub.
- Paid tools mainly buy convenience and support.

### Gaps
- No verified prices. Couldn't confirm widely recommended paid anime/stylized character courses (e.g., Lightning Boy Studio, CGMA, YanSculpts) because searches ran out before these were queried.
- Couldn't verify the "Hair Tool" (Bartosz Styperek) listing, a commonly cited paid Blender hair-card add-on. Not included.

---

## Q5. Which free stylized asset libraries and production files can be studied?

### Takeaway
- **Best study material for this style:** Blender Studio's Project Gold files and Brushstroke Tools, plus Kaspar's "Rain" course materials.
- **Free stylized props and environments:** Poly Haven models (CC0, mostly realistic), Quaternius and Kenney (stylized low-poly; CC0 commonly stated but not verified here), Sketchfab's downloadable filter (check each model's CC license), and TheBaseMesh (base meshes).
- **Scan alternatives** (Smithsonian Open Access) work as reference or remodeling bases, not as stylized assets.

### Cited Findings
- **Project Gold production files + Brushstroke Tools:** Blender Studio released the showcase with project files. — [80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files) [snippet]; [Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools) [snippet]; [Project Gold page](https://studio.blender.org/projects/gold/) — `asset` (license not verified; Blender Studio content is generally CC-BY **[unverified]**)
- **Stylized Character Workflow character "Rain":** course-linked character assets. — [Blender Studio course](https://studio.blender.org/training/stylized-character-workflow/) [snippet] — `asset`/`course` (download terms unverified)
- **Poly Haven Models:** "free high quality 3D assets … All models here are CC0". — [polyhaven.com/models](https://polyhaven.com/models) (per [awesome-blender](https://github.com/agmmnn/awesome-blender)) — `asset`
  - Asset-browser integration add-on (source on GitHub, ~523 stars): [Poly-Haven/polyhavenassets](https://github.com/Poly-Haven/polyhavenassets) — `code-addon`
- **Quaternius:** "Ultimate Low-Poly Models" collection. — [quaternius.com](http://quaternius.com/index.html) (per [awesome-blender](https://github.com/agmmnn/awesome-blender)) — `asset` (license not verified this session)
- **Kenney:** game assets; the GitHub profile links to [kenney.nl](http://kenney.nl/) — [GitHub KenneyNL](https://github.com/KenneyNL) — `asset` (CC0 commonly stated but **not verified this session**)
- **Sketchfab downloadable models filter:** — [Sketchfab search (downloadable)](https://sketchfab.com/search?features=downloadable&sort_by=-pertinence&type=models) — `asset` (per-model CC licenses; check each)
- **TheBaseMesh:** "A public library of over 600+ base meshes. All assets are real world scale and come unwrapped." — [thebasemesh.com](https://thebasemesh.com/model-library) — `asset`
- **Smithsonian Open Access:** "Download, share, and reuse millions of the Smithsonian's images"; awesome-blender also lists Smithsonian 3D digitization as a CC0 photoscan library. — [si.edu/openaccess](https://www.si.edu/openaccess) — `asset` (scan reference)
- **Free stylized GN scene files to dissect:** [IRCSS GeometryNodes-Stylized-Scene-Generator](https://github.com/IRCSS/GeometryNodes-Stylized-Scene-Generator) (Autumn/Winter scenes); [RC12 Stylized Fantasy Tree Generator](https://rc12.gumroad.com/l/fantasytree); [Blender GN demo files](https://www.blender.org/download/demo-files/#geometry-nodes) — `asset`
- **Anime foliage pipeline tutorials (free):** [Trung Duy Nguyen: Blender Anime Foliage Pipeline](https://trungduyng.substack.com/p/tutorial-blender-anime-foliage-pipeline); [Anime grass tutorial](https://trungduyng.substack.com/p/anime-grass-tutorial-blender) [snippet] — `tutorial`

### Inferences
- Poly Haven, Quaternius and Kenney skew towards realistic or low-poly game styles, so they suit blockout and set dressing, not hero assets. For a painterly finish, pair them with Brushstroke Tools or painted textures.
- **Stylized scan alternative** [inference]: use Smithsonian or Poly Haven scans as reference or base, then re-model or re-topologize with simplified planes and painted detail. This mirrors the productions' "remove details" philosophy.

### Gaps
- Couldn't verify the licenses of Quaternius and Kenney (commonly CC0) or of the Blender Studio Gold files, or list the specific Gold asset files.
- Couldn't enumerate other Blender Studio open-movie character files (e.g., Sprite Fright, Charge, Wing It!) with stylized characters. Their asset pages weren't reachable and weren't returned in searches.
- No dedicated "stylized scan" library (scans pre-stylized for NPR) was found.
