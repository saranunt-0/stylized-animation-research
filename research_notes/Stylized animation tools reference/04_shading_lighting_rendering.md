# NPR Shading, Lighting & Rendering Tools for Painterly/Stylized 3D Animation (Arcane / Project Gold / Mielgo) — as of 2 Oct 2026

How these notes were sourced. Most non-GitHub sites (code.blender.org, devtalk.blender.org, projects.blender.org, docs.blender.org, studio.blender.org, extensions.blender.org, cgchannel, 80.lv, befores & afters, gdcvault, YouTube, Superhive, ACM DL, Wikipedia, artineering.io, psoft.co.jp, malt3d.com) were blocked by the research environment's egress proxy, and the session's shared web-search quota ran out partway through. Each claim therefore carries a verification tag:
- **[fetched]**: page opened and read directly (GitHub pages and READMEs).
- **[source]**: checked against Blender's official GitHub source mirror (github.com/blender/blender, `main` branch, read 2 Oct 2026).
- **[search]**: seen in a web-search result title or snippet for that exact URL. The page itself was not opened.
- **[2nd-hand URL]**: the URL appears in a third-party GitHub document (named in each case). Neither the URL nor the claim was opened or checked independently.

Category labels: documentation / tutorial / recreation / code-addon / asset / course(paid) / talk / paper.

---

## Q1. What is the current state (Oct 2026) of Blender's NPR engine/prototype tied to Project Gold — features, version, official docs/blog posts?

### Takeaway
The standalone "EEVEE NPR Prototype" (2024–25, built on Blender 4.4, made with Dillon Goo Studio) has been **discontinued and archived**. Blender is now landing its NPR features in pieces inside regular EEVEE. The first official piece is the **"Material Lighting Nodes"** set (Light Evaluation, Light Info, Shadow Raycast, Light Accumulation). It was merged to `main` on **2 Sep 2026** and ships in **Blender 5.3**, which is in alpha as of 2 Oct 2026; one aggregator gives a 17 Nov 2026 release date. Project Gold (2024) itself did not use a new engine. Its painterly look relied on the Geometry-Nodes **Brushstroke Tools** extension (Blender 4.2+).

### Cited Findings
**NPR project history and the prototype**
- [documentation] The official NPR project began with a July 2024 workshop between Dillon Goo Studio and Blender developers. Development of the NPR system was planned to start after the Blender 5.0 release (Nov 2025). — [NPR Project, Blender Developers Blog (May 2025)](https://code.blender.org/2025/05/npr-project/) [search]
- [documentation] The design task is "#120403 – NPR Design" — [projects.blender.org #120403](https://projects.blender.org/blender/blender/issues/120403) [search]. The prototype PR is "#127258 – NPR-Prototype: Initial implementation" — [PR #127258](https://projects.blender.org/blender/blender/pulls/127258) [search]. Its to-do list is in [#127354 NPR Prototype (To Dos)](https://projects.blender.org/blender/blender/issues/127354) [search]. A related task is [#124615 EEVEE: Light Node Tree Support](https://projects.blender.org/blender/blender/issues/124615) [search].
- [documentation] How the prototype worked: it used a separate **NPR node tree**, selected from the Material Output node. That tree uses the regular material nodes plus new NPR-only nodes, and BSDF nodes are forbidden in it. Initial goals were filter support, custom shading and AOV access. Later builds added Multi-layer Refraction, Repeat Zones, Light Loops and NPR support for Light Probes. — [EEVEE NPR Prototype – Feedback (devtalk)](https://devtalk.blender.org/t/eevee-npr-prototype-feedback/37098) [search]; [CG Channel, Dec 2024](https://www.cgchannel.com/2024/12/check-out-blenders-experimental-non-photorealistic-rendering-build/) [search]
- [documentation] CG Channel (Dec 2024) reported that the prototype builds were based on Blender 4.4 and were "unlikely to be part of the stable release of Blender 4.4". Dillon Gu said merging into master "could be two years". — [CG Channel](https://www.cgchannel.com/2024/12/check-out-blenders-experimental-non-photorealistic-rendering-build/) [search]
- [code-addon] **Status: discontinued.** The devtalk thread states that "The NPR Prototype is no longer in development and will not receive further bug fixes", and that the final builds were archived on GitHub. — [devtalk post #372 by pragma37](https://devtalk.blender.org/t/eevee-npr-prototype-feedback/37098/372) [search]. The archive is [pragma37/Blender-NPR-Prototype](https://github.com/pragma37/Blender-NPR-Prototype): "Archived code and builds of the 2024 Blender NPR Prototype", created 10 Oct 2025, last push 10 Oct 2025 [fetched]. The old experimental build page was [builder.blender.org/download/experimental/npr-prototype/](https://builder.blender.org/download/experimental/npr-prototype/) [search; may no longer serve builds].

**What actually landed in official Blender (5.3)**
- [code-addon] Commit **c3f2d1f "EEVEE: Material Lighting Nodes"** was committed on **2 Sep 2026**, authored by pragma37 (the prototype's developer) with Clément Foucault (fclem) as co-author. It references [PR #161429](https://projects.blender.org/blender/blender/pulls/161429) and adds `ShaderNodeLightEvaluation`, `ShaderNodeLightInfo`, `ShaderNodeShadowRaycast` and `ShaderNodeLightAccumulation`, plus internal light-iteration nodes (73 files, +1,837/−172 lines). — [GitHub mirror commit c3f2d1f](https://github.com/blender/blender/commit/c3f2d1f) [fetched/source]; [file history](https://github.com/blender/blender/commits/main/source/blender/nodes/shader/nodes/node_shader_light_evaluation.cc) [fetched]
- [documentation] From the Blender 5.3 release notes: "Material Lighting nodes allow authoring how the Material reacts to Lights, and can be used for toon and stylized shading, but also for complex physical effects like iridescence." The nodes are **Light Accumulation** (evaluates its inputs for each scene light and accumulates the result), **Light Info** (Color, Power, Position), **Light Evaluation** (Diffuse/Specular term, Attenuation Mask, Direction, Distance) and **Shadow Raycast** (shadow mask for the light being shaded). — [Blender 5.3 release notes: EEVEE & Viewport](https://developer.blender.org/docs/release_notes/5.3/eevee/) [search]; see also [release-notes commit fe783c6104](https://projects.blender.org/blender/blender-developer-docs/commit/fe783c6104ac493b22ca58b62695f98289e58336) [search]
- [documentation] The devtalk thread describes the nodes as "similar to the 'For Each Light' node zone from the NPR prototype". Shadow Raycast has a **Softness** control (so area lights can still give sharp shadows) and can sample at an offset Position. The thread says the feature is "merged in main and available in daily builds", with a light-falloff node and other quality-of-life features planned. — [Material Lighting Nodes – Feedback (devtalk)](https://devtalk.blender.org/n/material-lighting-nodes-feedback/45695) [search]; [page 5](https://devtalk.blender.org/t/material-lighting-nodes-feedback/45695?page=5) [search]
- [documentation] Light Evaluation node, as defined in source: inputs Position, Normal and Roughness (default 0.5); outputs Factor ("Shading reflection factor, scaled by PI"), Mask (cutoff/spot attenuation; 1.0 for sun lights), Direction and Distance. It has a Diffuse/Glossy mode and only a GPU (EEVEE) implementation, with no Cycles code path. — [node_shader_light_evaluation.cc](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/shader/nodes/node_shader_light_evaluation.cc) [source]
- [documentation] Light Accumulation, as defined in source: inputs Diffuse/Glossy/Transmission Light and Color. Its description reads "Adds the result of all the evaluated lights and stores each input into its respective Compositing Pass… (Diffuse Light * Diffuse Color) + (Glossy Light * Glossy Color)". This means custom toon lighting still writes into the standard render passes. — [node_shader_light_accumulation.cc](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/shader/nodes/node_shader_light_accumulation.cc) [source]
- [documentation] On 2 Oct 2026, `main` reports `BLENDER_VERSION 503` with cycle `alpha`, i.e. 5.3 alpha. — [BKE_blender_version.h](https://raw.githubusercontent.com/blender/blender/main/source/blender/blenkernel/BKE_blender_version.h) [source]. The release-notes aggregator Releasebot says 5.3 alpha runs to 30 Sep and the final release is scheduled for 17 Nov (unverified aggregator) — [Releasebot](https://releasebot.io/updates/blender) [search]
- [tutorial] Early community testing: a Mix 3D post asks whether the new nodes "can actually replace Shader to RGB" for anime/cel shading — [Mix 3D on X](https://x.com/Mix3Design/status/2097814429521809460) [search]

**Project Gold (Blender Studio) and its tools**
- [documentation] Project Gold is Blender's 16th Open Movie, announced in 2023. It began as a short directed by Jericca Cleland and was refocused into a showcase of new tools for a painterly look. It premiered at Blender Conference 2024 (October) and was released online on 7 Nov 2024. — [Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools) [search]; [Project Gold Showcase Premiere Date (Blender Studio blog)](https://studio.blender.org/blog/project-gold-showcase-premiere-date/) [search]; [80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files) [search]
- [code-addon] **Brushstroke Tools** (Blender Studio) is a Geometry-Nodes add-on for creating, managing and editing layers of procedural 3D brushstrokes. Strokes can fill a whole mesh surface or be drawn directly onto it, with per-layer control of stroke shape and style. It requires Blender 4.2+ and is distributed on the Extensions platform. — [CG Channel, Nov 2024](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/) [search]; extension page [extensions.blender.org/add-ons/brushstroke-tools/](https://extensions.blender.org/add-ons/brushstroke-tools/) [2nd-hand URL, listed in naranyala/awesome-3d-blender-addons and in Nolavel/Hoarbound docs, which give the licence as GPL-3.0 and support as Blender 4.2+]
- [tutorial] Blender Studio training "Stylized Rendering with Brushstrokes – Get started using Brushstroke Tools" — [studio.blender.org training](https://studio.blender.org/training/stylized-rendering-with-brushstrokes/get-started-using-brushstroke-tools/) [2nd-hand URL, from Nolavel/Hoarbound]
- [documentation] Project Gold production material: "Brush Strokes: Tool Integration for Brush Flow Control" — [Blender Studio asset](https://studio.blender.org/projects/gold/3c7fb86d72b766/?asset=7110) [search]; [Production Log #58](https://studio.blender.org/projects/gold/production-log/281/) [search]

**Built-in Blender building blocks (verified in source)**
- [documentation] The **Shader to RGB** and **Color Ramp** shader nodes are still present in `main`. They remain the classic EEVEE-only toon recipe: the lit BSDF is converted to a color and then quantized. — [shader nodes directory](https://github.com/blender/blender/tree/main/source/blender/nodes/shader/nodes) (`node_shader_shader_to_rgb.cc`, `node_shader_color_ramp.cc`) [source]
- [documentation] The **Kuwahara** compositor node has two variations. "Classic" is the "Fast but less accurate variation". "Anisotropic" is the "Accurate but slower variation", with inputs Size (default 6), Uniformity, Sharpness and Eccentricity, and a High Precision option for Classic. The code cites Kyprianidis, Kang & Döllner 2009 ("Image and video abstraction by anisotropic Kuwahara filtering"), Kyprianidis et al. 2010 (polynomial weighting) and Kyprianidis 2011 (multi-scale). — [node_composite_kuwahara.cc](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/composite/nodes/node_composite_kuwahara.cc) [source]. Posterize, Pixelate, Glare and Filter compositor nodes also exist — [composite nodes dir](https://github.com/blender/blender/tree/main/source/blender/nodes/composite/nodes) [source]
- [documentation] The **Line Art** modifier code is still in `main` (`MOD_lineart.cc`, `intern/lineart/*`), and so is **Freestyle** (`source/blender/freestyle/FRS_freestyle.h`). — [GitHub mirror](https://github.com/blender/blender) [source, via code search]
- [documentation] EEVEE has **light linking** code in `main` (`eevee_light.cc`, `eevee_light_eval.bsl.hh`, `eevee_surf_deferred.bsl.hh`). — [GitHub mirror](https://github.com/blender/blender) [source, via code search; the version it first shipped in was not verified]

### Inferences
- In practice, the "Blender NPR engine" in Oct 2026 is regular EEVEE plus per-light material nodes in 5.3. Other prototype features (NPR tree, filter/screen-space stack, custom AOV access, Image Sample of render textures) are **not** in official Blender per the evidence found. They exist only in the archived prototype and in community forks (see Q2). Studios needing screen-space filters inside materials today must use a fork or Malt, or do the work in compositing.
- The 5.3 Light Evaluation and Shadow Raycast nodes are a cleaner substitute for Shader to RGB: they work per light, keep light color, support sharp shadows from area lights, and still feed the compositing passes. Expect tutorials to shift to them after the 5.3 release. Shader to RGB still works for 4.2–5.2 pipelines.
- Light linking plus per-light material evaluation makes "cheated" per-shot lighting (a rim light only on the hero, a key light that ignores the set) achievable inside EEVEE.

### Gaps
- The full text of the code.blender.org NPR posts (May 2025 and any 2026 follow-up) could not be read (domain blocked). Which prototype features beyond the lighting nodes are scheduled for 5.4+ (filters, NPR tree, screen-space sampling) remains unverified.
- No Blender Conference 2025 NPR talk page or 2026 NPR roadmap post could be verified.
- The exact Blender version in which EEVEE light linking first shipped, and the current Grease Pencil v3 / Line Art details, were not verified (docs blocked). Only source-code presence is confirmed.
- Workbench "tricks" for NPR: no source found.

---

## Q2. Which free/open-source repos and add-ons provide painterly or toon shading (name, function, license, URL, maintenance, compatibility)?

### Takeaway
For Blender, the main open options are **Goo Engine** (official build still 4.4, distributed via Patreon), its **community ports to 5.1/5.2** (bb-yi, NaMgAl-Studio), **Malt** (MIT, OpenGL 4.5, with a Blender-5.0 build but no pushes since Mar 2026), and Blender Studio's **Brushstroke Tools**. Outside Blender, **UTS3**, **lilToon** and the **NiloCat example** (Unity), **MooaToon** (UE5) and several Godot shaders are actively used. Research code (Hertzmann, MNPR, Kuwahara) is mostly frozen but is a useful reference.

### Cited Findings
Maintenance status below uses the GitHub `pushed_at` field as of 1–2 Oct 2026 [fetched via GitHub API].

**Blender forks / engines**
- [code-addon] **Goo Engine**: [dillongoostudios/goo-engine](https://github.com/dillongoostudios/goo-engine), "Custom build of blender with some extra NPR features" for anime/NPR. The README mentions "four custom Shader nodes we added to Eevee and Light Groups". Licence GPL-3 (Blender). Pre-built downloads are on Patreon and there are **no GitHub releases**. Last push 15 Sep 2026; 1.4k stars. [fetched]. The latest official release is **Goo Engine v4.4-release, based on Blender 4.4.x with legacy EEVEE** (stated in the NaMgAl port README) [fetched, secondary].
- [code-addon] **Unofficial Goo port to Blender 5.2.1 / EEVEE-Next**: [NaMgAl-Studio/goo-engine-5.2.0](https://github.com/NaMgAl-Studio/goo-engine-5.2.0) (created 29 Jul 2026, last push 12 Sep 2026). It ports 13 nodes: Shader Info, Screenspace Info, SDF Primitive, SDF Op, SDF Vector Op, SDF Noise, Set Depth, Curvature, Light Info, Hexagon Texture, Twirl, Water Ripples and OKLab Color Ramp. It also adds Light Groups and raises the forward-pipeline limit to 512 lights per fragment. It says "experimental, unofficial build… GPL without any warranty" and recommends the original Goo Engine 4.4 for production. [fetched]
- [code-addon] **NPR prototype + Goo port**: [bb-yi/blender](https://github.com/bb-yi/blender), "Porting Goo Engine and NPR prototype to Blender 5.1", now on a "Blender 5.2 NPR main" branch. Last push 28 Sep 2026; 142 stars; site bb-yi.github.io/blender. [fetched]. Its documented features ([blender-npr-features-and-usage.md](https://raw.githubusercontent.com/bb-yi/blender/main/blender-npr-features-and-usage.md) [fetched]):
  - Render Textures (Color/Depth/Normal) and Filter Materials (full-screen filter stack with Scene Color, Filter Object Info and Filter Mask nodes).
  - EEVEE screen-space Outline with an Outline Control node.
  - Nodes: Screen Derivative, Curvature, Bevel, GLSL Function (custom code), Image to Closure, OKLab Color Ramp, and the SDF suite.
  - The NPR Tree with NPR Input/Output, NPR Refraction, Image Sample and **For Each Light**.
  - Built-in groups: Cavity, Co-Planar Edge Detection, **Kuwahara**, Shading Models, Surface Curvature.
  - Stencil/ZTest render states and Lightgroup ID filtering.
  - Discussion thread: [Blender Artists](https://blenderartists.org/t/porting-goo-engine-and-npr-prototype-to-blender-5-1/1635806) [search]
- [code-addon] **Malt / BlenderMalt**: [bnpr/Malt](https://github.com/bnpr/Malt), a "fully customizable real-time rendering framework for animation and illustration". It offers GLSL pipelines with auto-generated nodes, a built-in NPR pipeline and VSCode hot-reload. It requires OpenGL 4.5 and Windows/Linux (no macOS), and the README says "MIT License" (the GitHub API shows NOASSERTION). Docs are at malt3d.com. Last push 29 Mar 2026; 1.1k stars. [fetched]. The [releases](https://github.com/bnpr/Malt/releases) include `Release-latest`, `blender-5.0-last-version`, `blender-4.5-last-version`, `blender-4.0-last-version` and older per-version tags. [fetched; the fetch tool reported some release years as 2024/2025, which conflicts with Blender 5.0 shipping in Nov 2025, so the "29 Mar" date is probably 2026 — unverified]
- [code-addon] **Blender NPR Prototype (archived)**: [pragma37/Blender-NPR-Prototype](https://github.com/pragma37/Blender-NPR-Prototype) [fetched]. Frozen at Blender 4.4.

**Blender add-ons, node groups and shaders**
- [code-addon] **Brushstroke Tools** (Blender Studio; GPL-3.0; Blender 4.2+) — see Q1. [extensions.blender.org](https://extensions.blender.org/add-ons/brushstroke-tools/) [2nd-hand URL]
- [code-addon] **LSCherry**: [lvoxx/LSCherry](https://github.com/lvoxx/LSCherry), a toon-shader framework for Blender "evolved from aVersionOfReality's Toon Shader". GPL-3.0; last push 17 Sep 2026. [fetched]
- [code-addon] **Blender-miHoYo-Shaders** (Genshin replication): [festivities/Blender-miHoYo-Shaders](https://github.com/festivities/Blender-miHoYo-Shaders), GPL-3.0, **archived** (last push May 2024). **Blender-StellarToon** (Honkai: Star Rail, built for Goo Engine): [festivities/Blender-StellarToon](https://github.com/festivities/Blender-StellarToon). Both target datamined game assets. [fetched]
- [code-addon] **EEVEEToon**: [kanzwataru/EEVEEToon](https://github.com/kanzwataru/EEVEEToon), base nodes and sample toon shaders. The README says it is "outdated and may not work with the latest Blender releases" (2.8 era). **Flag: abandoned.** [fetched]
- [code-addon] **btoon**: [yuki-koyama/btoon](https://github.com/yuki-koyama/btoon), a toon-rendering add-on. GPL-3.0; last push Jun 2020. **Flag: stale.** [fetched]
- [code-addon] **BNPR shaders collection** (EEVEE Comics Shader, Erisdraw3D, EEVEEToon) — [blendernpr.org/downloads](https://blendernpr.org/downloads/) [2nd-hand URL, from devanshutak25/3d-resources]
- [code-addon] Small new 2026 repos, unproven, tiny star counts:
  - [Angora-Shader](https://github.com/legralltitouan/Angora-Shader): geometry-based brushstroke NPR toolkit (Mar 2026).
  - [infinition/cymatics](https://github.com/infinition/cymatics): NPR surface shader with a 14-stage compositing chain (Aug 2026).
  - [ExtCan/Blender-Halcyon-Engine](https://github.com/ExtCan/Blender-Halcyon-Engine): from-scratch render engine for cel/ink/painted-backdrop looks (Jul 2026). [fetched]

**Unity**
- [code-addon] **Unity Toon Shader (UTS3)**: [Unity-Technologies/com.unity.toonshader](https://github.com/Unity-Technologies/com.unity.toonshader). Supports Built-in, URP and HDRP, and successor to UTS2. Licence: Unity Companion License. Docs: [docs.unity3d.com/Packages/com.unity.toonshader@latest](https://docs.unity3d.com/Packages/com.unity.toonshader@latest). Last push 4 Sep 2026; 1.6k stars. [fetched]. The legacy UTS2 manual is in [unity3d-jp/UnityChanToonShaderVer2_Project](https://github.com/unity3d-jp/UnityChanToonShaderVer2_Project) [found via code search].
- [code-addon] **lilToon**: [lilxyzw/lilToon](https://github.com/lilxyzw/lilToon), "Feature-rich shaders for avatars". MIT; last push 26 Jul 2026. Docs: [lilxyzw.github.io/lilToon](https://lilxyzw.github.io/lilToon/index.html#/en-us/) [fetched]
- [tutorial/code-addon] **UnityURPToonLitShaderExample** (NiloCat): [ColinLeung-NiloCat/UnityURPToonLitShaderExample](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample), a short, readable URP toon shader for learning. MIT; Unity 2021.3 LTS to Unity 6; 7.8k stars. The full NiloToonURP is closed-source. [fetched]
- [code-addon] Other Unity toon shaders:
  - Toon RP: [Delt06/toon-rp](https://github.com/Delt06/toon-rp), a full SRP for toon looks. MIT; last push Aug 2024.
  - [Delt06/urp-toon-shader](https://github.com/Delt06/urp-toon-shader): MIT; Nov 2023.
  - [Gaolingx/GenshinCelShaderURP](https://github.com/Gaolingx/GenshinCelShaderURP): MIT; Mar 2025. Ramp textures, SDF face shadows, rim light, outlines.
  - [stalomeow/StarRailNPRShader](https://github.com/stalomeow/StarRailNPRShader): GPL-3.0, **archived**.
  - [kayac/kamakura-shaders](https://github.com/kayac/kamakura-shaders): last push 2018, **stale**. [fetched]

**Unreal Engine**
- [code-addon] **MooaToon**: [JasonMa0012/MooaToon](https://github.com/JasonMa0012/MooaToon), "The Ultimate Solution for Cinematic Toon Rendering in UE5". It provides Lumen GI with intensity control, ray-traced shadows with self-shadow control, ramp maps, per-light screen-space rim light, face shadow maps, back-face and screen-space outlines, and Kajiya-Kay hair highlights. Licence terms are at [mooatoon.com/docs/Licence/](https://mooatoon.com/docs/Licence/); docs at [mooatoon.com](https://mooatoon.com/). Last push 18 Sep 2026; 747 stars. [fetched]
- [code-addon] **Kuwahara-Filter-Plugin**: [alicepm800/Kuwahara-Filter-Plugin](https://github.com/alicepm800/Kuwahara-Filter-Plugin), an HLSL Kuwahara implemented as a C++ global-shader plugin. Small project. [fetched]
- [code-addon] UE5 anime/toon/cel shading model by Envieous (forum post) — [Unreal forums](https://forums.unrealengine.com/t/ue5-anime-toon-cel-shading-model-works-with-launcher-engine-versions/544226) [2nd-hand URL, from devanshutak25/3d-resources]

**Godot**
- [code-addon] Godot toon shaders:
  - [EXPWorlds/Godot-Cel-Shader](https://github.com/EXPWorlds/Godot-Cel-Shader): MIT; last push Jun 2020. **Flag: likely Godot 3 era.**
  - [CaptainProton42/FlexibleToonShaderGD](https://github.com/CaptainProton42/FlexibleToonShaderGD): MIT; May 2021.
  - [nekotogd/Godot_BoTW_Toon_Shader](https://github.com/nekotogd/Godot_BoTW_Toon_Shader): BotW-style shader with multiple lights.
  - [EMBYRDEV/godot-toon-outline](https://github.com/EMBYRDEV/godot-toon-outline): post-process outline. MIT; 2023.
  - [frankschoeman/Godot-ComicShader](https://github.com/frankschoeman/Godot-ComicShader): Godot 4.x. [fetched]

**Maya / research frameworks**
- [code-addon] **MNPR**: [semontesdeoca/MNPR](https://github.com/semontesdeoca/MNPR), a real-time, filter-based stylization framework in Maya Viewport 2.0 with watercolor-style pigment, substrate, edge and abstraction effects. MIT ("MNPR is now open-sourced under the MIT-license"). Maya 2016.5+; v1.0 tested on Maya 2017–2018. Last push Jul 2019. **Flag: unmaintained.** The README directs production users to the commercial MNPRX ([artineering.io/projects/MNPRX/](https://artineering.io/projects/MNPRX/)). [fetched]

**Painterly / stroke-based research code**
- [code-addon/paper] **painterJava** (Aaron Hertzmann's original code for "Painterly Rendering with Curved Brush Strokes of Multiple Sizes", SIGGRAPH 98): [hertzmann/painterJava](https://github.com/hertzmann/painterJava). MIT. Project page: [mrl.cs.nyu.edu/publications/painterly98/](https://mrl.cs.nyu.edu/publications/painterly98/); paper: [ACM DOI 10.1145/280814.280951](https://dl.acm.org/doi/10.1145/280814.280951); video follow-up (NPAR 2000): [painterly-video](https://mrl.cs.nyu.edu/publications/painterly-video/). [fetched]
- [code-addon] Python ports: [pschaldenbrand/PyPainterly](https://github.com/pschaldenbrand/PyPainterly), [manuelladron/painterPython](https://github.com/manuelladron/painterPython); real-time WebGL version: [ScottTodd/PainterlyRendering](https://github.com/ScottTodd/PainterlyRendering). [fetched]
- [code-addon] Line and other NPR research code:
  - [SSARCandy/Coherent-Line-Drawing](https://github.com/SSARCandy/Coherent-Line-Drawing): coherent line drawing from images.
  - [lindemeier/PaintMixer](https://github.com/lindemeier/PaintMixer): Kubelka-Munk paint mixing. **Archived.**
  - [LuisaGroup/practical-stylized](https://github.com/LuisaGroup/practical-stylized): SIGGRAPH 2025 "Practical Stylized Nonlinear Monte Carlo Rendering". **Archived.**
  - [vpalos/Krbn](https://github.com/vpalos/Krbn): pencil-style SVG rendering. [fetched]
- [recreation] Style recreations:
  - [galloscript/GGXrdShading](https://github.com/galloscript/GGXrdShading): a WebGL demo of Guilty Gear Xrd techniques (vertex-color control, threshold shading, ILM/SSS textures, inverted-hull outlines, inner lines), with a [live demo](https://galloscript.github.io/GGXrdShading/index.html).
  - [adamb70/Spiderverse-Shader-Unity](https://github.com/adamb70/Spiderverse-Shader-Unity): halftone image effect.
  - [Databazator/Arcane-like-Stylized-Character-Shader](https://github.com/Databazator/Arcane-like-Stylized-Character-Shader): Unity, tiny. [fetched]

### Inferences
- For a Blender pipeline in late 2026, these are the safest choices:
  - **Official Blender 5.3 EEVEE**: lighting nodes, Shader to RGB, light linking, compositor Kuwahara.
  - **Brushstroke Tools** for painted stroke geometry.
  - **Goo Engine 4.4** only if you accept staying on 4.4 (Patreon builds).
- The 5.1/5.2 community ports are attractive but carry production risk: they are single-maintainer and unofficial. Malt is powerful for TDs who write GLSL, but there have been no pushes since Mar 2026 and there is no macOS support.
- Most Unity, Unreal and Godot repos are anime/game-oriented (Genshin/HSR replication). Their techniques (ramps, SDF face shadows, rim, outlines) transfer, but they are not painterly by default.

### Gaps
- Which Blender versions Malt's `Release-latest` supports (5.1/5.2) could not be confirmed because malt3d.com was blocked.
- The Goo Engine feature list and Patreon tier pricing on the official site were not verified (only README and third-party port statements).
- No GitHub mirror of Brushstroke Tools was found (it lives on projects.blender.org), so its exact repo, licence text and current version were not verified directly.

---

## Q3. What are the core shader/lighting techniques for an Arcane-like painterly look, and the best free tutorials for each?

### Takeaway
Arcane's look mostly comes from **painted assets** (Photoshop/Mari textures with light, shadow and bevels painted in), **projected matte-painted environments**, **2D FX at 12 fps over 24 fps animation**, and heavy **per-shot compositing in Nuke** ("each shot is a painting"). It is not a special renderer. Recreating it in open tools typically means:
1. Hand-painted albedo with baked value design.
2. Quantized or ramped light (Shader to RGB, or the 5.3 Light Evaluation nodes) with colored shadows.
3. Graphic rim and terminator lights, cheated via light linking.
4. Brushstroke geometry or masks to break CG edges (Brushstroke Tools).
5. Screen-space abstraction (Kuwahara or painterly filters) plus line work, finished with a per-shot comp grade.

### Cited Findings
**What Fortiche did (production sources).** All URLs in this block are 2nd-hand: they were collected in the GitHub research file [jethac/lucid-loop: arcane-fortiche-art-style.md](https://raw.githubusercontent.com/jethac/lucid-loop/main/research/arcane-fortiche-art-style.md) [fetched], and none was opened directly. Treat the claims as provisional.
- [talk/documentation] **Maya** was the 3D package (Maya 2018, maintained into Season 2), with Rec.709 colour, per the SIGGRAPH Asia 2024 Arcane S2 coverage. The same coverage notes that projected matte paintings limit camera movement. — [InCG: SIGGRAPH Asia 2024 Arcane S2](https://www.incgmedia.com/makingof/siggraph-asia-2024-arcane-season-2) [2nd-hand URL]
- [documentation] Textures were painted in **Photoshop**, with highlights and shadows painted into them rather than generated only by CG light. FX are hand-drawn at **12 fps over 24 fps** character animation. Compositing used **Nuke** (plus After Effects and Houdini), animation is keyframe-only, and the camera language is live-action. — [RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline) [2nd-hand URL]
- [talk] **Mari** painted look on hero assets: albedo-style painting plus extra passes (shadow, light, IDs) so lighting and comp can recompose. — [Foundry video](https://www.youtube.com/watch?v=gCJIJG6Lz84) [2nd-hand URL]; [Fortiche FMX 2025 Arcane S2 deep dive](https://forticheprod.com/blog/projects-events/fortiche-rocks-fmx-2025-with-arcane-season-2-deep-dive/) [2nd-hand URL]
- [tutorial] Environments use a 3D set first, then projected paint with freehand lines and traditional brushes — [80.lv: Arcane artists combine traditional art & 3D for backgrounds](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds) [2nd-hand URL]
- [talk] Compositing sets color and light intensity per shot: "On pense chaque plan comme une peinture" ("we think of each shot as a painting"). — [Fortiche compositing short](https://www.youtube.com/watch?v=dn87jqMKxuY) [2nd-hand URL]
- [documentation] Art direction: a raw, graphic, "everything painted" finish, with Piltover Art Nouveau/Deco and Zaun industrial greens and warm tones — [SyncSketch: Arcane / Fortiche](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) [2nd-hand URL]. Season 2 added charcoal, watercolor and comic-style sequences — [AWN](https://www.awn.com/animationworld/riot-games-and-fortiche-push-every-possible-boundary-arcane-season-2) [2nd-hand URL]. On the "Fortiche touch" (drawing + 2D painting + 3D) — [AnimationXpress](https://www.animationxpress.com/animation/talent-experimentation-originality-how-fortiche-revolutionised-animated-storytelling-with-arcane/) [2nd-hand URL]
- [documentation] Related Riot work (Worlds 2021 open, rendered with Arnold): specularity omitted and highlights painted into diffuse — [Autodesk community blog](https://forums.autodesk.com/t5/community-blog-m-e-english/arnold-s-powerhouse-rendering-for-riot-s-worlds-2021-show-open/ba-p/13901225) [2nd-hand URL]

**Recreations and tutorials, by technique**
- [recreation] **Fan breakdowns of Arcane lighting:** Noggi's fan reverse-engineering of a base / shadow / rim layered lighting structure — [YouTube](https://www.youtube.com/watch?v=gw6m2W5ja4o) [2nd-hand URL, labelled fan speculation]. A game-ready Arcane-style asset in Blender/UE5: diffuse map drives roughness and height, and the shader mixes unlit + PBR + rim + simulated front light for the terminator — [80.lv cannon breakdown](https://80.lv/articles/creating-a-game-ready-cannon-in-an-arcane-inspired-style) [2nd-hand URL]
- [code-addon/tutorial] **Painted stroke geometry and masks:** Brushstroke Tools and its Blender Studio training (see Q1). [2nd-hand URLs]
- [tutorial] **Ramp/threshold toon lighting basics:**
  - The lettier "3D Game Shaders for Beginners" chapters on [Cel Shading](https://github.com/lettier/3d-game-shaders-for-beginners/blob/master/sections/cel-shading.md), [Rim Lighting](https://github.com/lettier/3d-game-shaders-for-beginners/blob/master/sections/rim-lighting.md), [Fresnel Factor](https://github.com/lettier/3d-game-shaders-for-beginners/blob/master/sections/fresnel-factor.md), [Outlining](https://github.com/lettier/3d-game-shaders-for-beginners/blob/master/sections/outlining.md) and [Posterization](https://github.com/lettier/3d-game-shaders-for-beginners/blob/master/sections/posterization.md). Only the code is licensed; the text is not. [fetched README; chapter paths taken from the README table of contents]
  - "Making a NPR Shader in Blender" — [typhomnt.github.io](https://typhomnt.github.io/post/blender_npr/) [search]
- [tutorial] **Free video channels on toon/NPR shading** (all [2nd-hand URL], from devanshutak25/3d-resources):
  - [Lightning Boy Studio](https://www.youtube.com/channel/UCd9i2MKimSaKezat1xkn8-A/videos): toon/NPR shading for Blender.
  - [Chris Folea Makes Things](https://www.youtube.com/@CFMakesThings): comic-book shading in UE without post-processing.
  - [Your Sandbox](https://www.youtube.com/@YourSandbox): cel-shading playlist, UE with Lumen.
  - [Useless Game Dev](https://www.youtube.com/@uselessgamedev): Moebius-style rendering with Sobel on depth and crosshatching.
  - [Hepner Kamil](https://www.youtube.com/@HepnerKamil): manga/outline shaders.
  - [Pitchfork Academy](https://www.youtube.com/@PitchforkAcademy): advanced cel-shader breakdown.
- [tutorial] **Unity/URP shader learning** — [Cyanilux](https://www.cyanilux.com/contents/) [2nd-hand URL]; the NiloCat example repo [fetched]
- [documentation] **Screen-space painterly filter:** Blender's compositor Kuwahara (Classic and Anisotropic) [source]. A Kuwahara node group is also bundled in the bb-yi NPR fork's NPR tree [fetched].
- [paper/tutorial] **Painterly CG and lighting-design principles.** These were compiled in [Nolavel/Hoarbound LIGHT_AND_SHADOW_DIRECTION.md](https://raw.githubusercontent.com/Nolavel/Hoarbound/main/docs/art/LIGHT_AND_SHADOW_DIRECTION.md) [fetched]; the principles are that document's own synthesis:
  - Shadows take the hue of what fills them, e.g. blue sky-fill.
  - Cast shadows are sharp at contact and soften with distance; form shadows are softer.
  - Concentrate the sharpest edges at focal points.
  - Mass detail into broad shapes.
  - Fix strokes to world geometry, not the screen.
  - Use rim and value shifts to separate characters.
  - Use AO as grounding accents, and fog/gradients for depth.
- [paper/talk] Sources cited in the Hoarbound document (all [2nd-hand URL]):
  - Disney Animation, [Painterly CG Concepts (PDF)](https://media.disneyanimation.com/uploads/production/publication_asset/64/asset/painterlyCgConcepts.pdf)
  - Meier 1996, "Painterly rendering for animation" — [SIGGRAPH history](https://history.siggraph.org/?p=117028)
  - Mitchell et al. 2007, Illustrative Rendering in Team Fortress 2 — [course notes PDF](https://www.advances.realtimerendering.com/s2007/Mitchell-IllustrativeRenderingInTF2(Siggraph07%20Course%20Notes).pdf); also [NPAR07 PDF](https://steamcdn-a.akamaihd.net/apps/valve/2007/NPAR07_IllustrativeRenderingInTeamFortress2.pdf), cited in the GenshinCelShaderURP README [fetched]
  - [Proko: Intro to edges](https://www.proko.com/course-lesson/intro-to-edges)
  - [Creative Bloq: lost and found edges](https://creativebloq.com/illustration/theory-behind-lost-and-found-edges-explained-51620585)
  - Jane Ng, Firewatch, GDC 2015 — [GDC Vault](https://gdcvault.com/play/1022923/Making-the-World-of)
  - Disco Elysium render-to-paintover — [GameBanshee](https://www.gamebanshee.com/news/121823-disco-elysium-from-render-to-paintover.html)
- [asset] **Brushes and textures for painted maps** (all [2nd-hand URL], from Hoarbound):
  - David Revoy's CC0 Krita brushes — [davidrevoy.com](https://www.davidrevoy.com/article1060/krita-brushes-2025-01-bundle/)
  - CC0 stylized textures — [BlenderNation](https://www.blendernation.com/2025/11/04/cc0-stylized-textures/)
  - Hand-painted textures — [OpenGameArt](https://opengameart.org/content/8-handpainted-style-textures)

### Inferences
- Summary of the Arcane technique stack (a synthesis, not a Fortiche statement):
  - Albedo carries painted value and bevels.
  - Lighting is simplified into 2–3 graphic layers (base / shadow / rim).
  - Shadows are hue-shifted rather than darkened.
  - Specular is mostly painted rather than computed.
  - Edges are broken by strokes or abstraction.
  - Per-shot comp "paints" the final balance.
  - FX are hand-drawn 2D on twos.
- For Blender, the closest open pipeline is: painted textures (Krita/Blender texture paint) → EEVEE with Light Evaluation / Shadow Raycast or Shader to RGB ramps, light linking for rims → Brushstroke Tools on silhouettes and large forms → Grease Pencil / Line Art for selective lines → compositor (Kuwahara, per-shot grade).
- The "cheated shadows per shot" approach maps to light linking, the 5.3 Shadow Raycast offset and softness controls, and painted shadow masks in textures or comp.

### Gaps
- None of the Arcane production sources above could be opened directly (all blocked or found only 2nd-hand). Software claims such as "Maya 2018" should be re-verified before publication.
- No verified free Blender tutorial specifically recreating Arcane-style lighting was found.
- Lighting-specific talks (e.g. a Fortiche lighting lead's talk) were not found.

---

## Q4. How do Alberto Mielgo's films (The Witness, Jibaro, The Windshield Wiper) approach lighting and rendering — stated by him or crew vs. speculation?

### Takeaway
Here is what Mielgo and his crew have stated, as seen in interview snippets. He paints backgrounds by hand, grounded in the "physics of light". On *The Witness* there were **no 3D sets**: the paintings were the sets, and lighters matched CG character lighting to the light sources Mielgo described in each painting, then adjusted levels per shot. Characters are deliberately simplified and detail is removed. One snippet says *The Witness* combined Blender/Cycles sets with Maya/Arnold characters. Nothing verifiable was found on *The Windshield Wiper*'s pipeline.

### Cited Findings
- [talk/documentation] *Jibaro*: Mielgo's backgrounds are hand-painted, and he bases his painting on the physics of light: how light hits objects and gives correct colour, tone and shadow values. The characters look realistic because "the physics of light are correct", yet they are simpler than hyper-realistic 3D because he removes unnecessary detail. The paintings are built from strokes that turn abstract up close. — interview snippets from [SlashFilm](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/), [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/), [Game Rant](https://gamerant.com/interview-alberto-mielgo-love-death-and-robots-volume-3-jibaro-netflix/) and [AwardsDaily](https://www.awardsdaily.com/2022/06/26/alberto-mielgo-on-his-animated-short-jibaro-in-netflixs-love-death-robots/) [search; the snippets are a merged summary, so exact quotes and their attribution to individual articles are unverified]
- [talk] *The Witness* was made at Pinkman.TV (Madrid), and lighting "had a major role". Mielgo said that instead of lighting characters inside 3D sets "we didn't have 3D sets—we had paintings". He gave the paintings to the lighters, describing how he painted them and where the light source came from, and after each shot was rendered the team adjusted the levels. — [befores & afters (May 2019)](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/) [search snippet; page blocked]
- [talk] *The Witness* software: "Sets were modeled and rendered in Blender/Cycles, while characters were done in Maya and rendered with Arnold", and the team had to make character lighting, shadows and reflections interact convincingly with the environment. — snippet from a search covering the [BlenderNation interview with Vaughan Ling](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/) and [Zeno Pelgrims' project page](http://www.zenopelgrims.com/project-ldr-the-witness.html) [search; which page the sentence came from is uncertain]
- [documentation] Rendering services for *The Witness* were provided by SummuS Render — [SummuS Render blog](https://www.summus.es/en/blog/2019/04/11/summus-render-provides-rendering-services-to-the-short-the-witness-of-love-death-robots-series-by-netflix/) [search]. Street background paintings by Wardenlight Studio — [ArtStation](https://wardenlight.artstation.com/projects/mqPy8d) [search]
- [documentation] *Jibaro* was made by pinkman.tv, and Mielgo won the 2022 Oscar for Best Animated Short. That Oscar was for *The Windshield Wiper*; the search summary attached it to the Jibaro context, so check the attribution. — [search summary of ArtStation/LinkedIn results](https://www.artstation.com/artwork/8wLQkR) [search]. Third-party technique write-ups exist but are secondary: [Fox Renderfarm](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/) and [Peliplat](https://www.peliplat.com/en/article/10009911/behind-the-creation-of-jibaro-in-love-death-robots) [search]
- Speculation flag: a search summary linked a LinkedIn post about rethinking the 3D pipeline with Blender/Unreal/UE5 to Jibaro. That post is about Blender's open movie *CHARGE*, so it is **not** evidence about Jibaro's pipeline. — [LinkedIn post](https://www.linkedin.com/posts/jfsarazin_charge-blender-open-movie-activity-7009273901679562752-hE4k) [search]

### Inferences
- Mielgo's method is "lighting-first painting". The painted plate (or painted set) is the lighting reference, and CG characters are lit to match its stated key direction and colour, then graded per shot. In tool terms this is a painted-background + CG-character comp workflow: light linking / per-character light rigs, shadow catchers, and levels or curves per shot. It is not a single NPR shader.
- "Physically motivated but simplified" means a correct key/fill/bounce logic and colour temperature, with texture detail and specular complexity removed.

### Gaps
- No verified primary source was found on *The Windshield Wiper*'s rendering or lighting pipeline. Web search was exhausted, and the pages that were found were blocked.
- The software used on *Jibaro* (renderer, DCCs) was not confirmed by any accessible source.
- Exact verbatim quotes could not be checked because all interview pages were blocked.

---

## Q5. Which key reference papers and talks cover these techniques (Spider-Verse, Arcane, Puss in Boots, Guilty Gear Xrd, Genshin, Blender Conference)?

### Takeaway
The Guilty Gear Xrd GDC talk and the Hertzmann, Meier, Kyprianidis and TF2 papers are well anchored with URLs. Arcane talk coverage (SIGGRAPH Asia 2024, FMX 2025) was found only second-hand. **No URLs could be verified for the Spider-Verse or Puss in Boots SIGGRAPH talks, the Genshin/miHoYo talks, or Blender Conference NPR talks.**

### Cited Findings
- [talk] GDC: "GuiltyGearXrd's Art Style: The X Factor Between 2D and 3D" (Arc System Works). The techniques are demonstrated in the GGXrdShading repo: vertex-color control channels, threshold shading, ILM/SSS textures, inverted-hull outlines and inner lines. — [YouTube](https://www.youtube.com/watch?v=yhGjCzxJV3E) [2nd-hand URL, from the GGXrdShading README]; recreation: [galloscript/GGXrdShading](https://github.com/galloscript/GGXrdShading) [fetched]
- [paper] Hertzmann 1998, "Painterly Rendering with Curved Brush Strokes of Multiple Sizes" — [ACM DOI](https://dl.acm.org/doi/10.1145/280814.280951); [project page](https://mrl.cs.nyu.edu/publications/painterly98/) [2nd-hand URL, from the painterJava README]
- [paper] Meier 1996, "Painterly rendering for animation" (particles fixed to surfaces, the basis of world-space brushstrokes like Brushstroke Tools) — [history.siggraph.org](https://history.siggraph.org/?p=117028) [2nd-hand URL]
- [paper] Kyprianidis, Kang & Döllner 2009, anisotropic Kuwahara; Kyprianidis et al. 2010; Kyprianidis 2011 (multi-scale). These are cited in Blender's Kuwahara source [source]; no paper URLs were captured.
- [paper] Mitchell, Francke & Eng 2007, "Illustrative Rendering in Team Fortress 2" (NPAR) — [PDF (Valve)](https://steamcdn-a.akamaihd.net/apps/valve/2007/NPAR07_IllustrativeRenderingInTeamFortress2.pdf) [2nd-hand URL, from the GenshinCelShaderURP README]
- [paper] Montesdeoca et al., MNPR and real-time watercolor — [MNPR paper page](https://artineering.io/research/MNPR/); [watercolor thesis page](https://artineering.io/research/Real-time-watercolor-rendering-of-3D-objects-and-animation-with-enhanced-control/) [2nd-hand URL, from the MNPR README]
- [paper] Disney Animation, "Painterly CG Concepts" — [PDF](https://media.disneyanimation.com/uploads/production/publication_asset/64/asset/painterlyCgConcepts.pdf) [2nd-hand URL]
- [paper] SIGGRAPH 2025, "Practical Stylized Nonlinear Monte Carlo Rendering" (code archived) — [LuisaGroup/practical-stylized](https://github.com/LuisaGroup/practical-stylized) [fetched]
- [talk] Arcane S2 at SIGGRAPH Asia 2024 — [InCG](https://www.incgmedia.com/makingof/siggraph-asia-2024-arcane-season-2); FMX 2025 — [Fortiche blog](https://forticheprod.com/blog/projects-events/fortiche-rocks-fmx-2025-with-arcane-season-2-deep-dive/) [2nd-hand URLs]
- [tutorial] Chinese-language Genshin-style breakdowns cited by GenshinCelShaderURP: [Bilibili tutorial](https://www.bilibili.com/video/BV1t34y1H7jt/), [Bilibili ramp tool](https://www.bilibili.com/video/BV17h411b73u), [Zhihu article](https://zhuanlan.zhihu.com/p/547129280) [2nd-hand URLs]

### Inferences
- The Guilty Gear Xrd techniques (vertex-normal and threshold control, ILM maps, inverted-hull outlines) are the backbone of most anime toon repos listed in Q2. They suit clean anime looks more than Arcane's painted look, where painted textures and comp dominate.

### Gaps
- Spider-Verse SIGGRAPH talks (Sony Imageworks), Puss in Boots: The Last Wish painterly talks (DreamWorks), miHoYo/Genshin GDC or Unite talks, and Blender Conference 2024/2025 NPR talks: **no URLs were verified**. Search quota was exhausted and gdcvault, dl.acm.org and YouTube were blocked. These must be filled from another source.

---

## Q6. Paid tools/courses — one-line summary + link

### Takeaway
Only a few paid items could be verified with URLs: **Pencil+ 4** (PSOFT line rendering), **MNPRX** (Artineering), **MooaToon** (licence page), **NiloToonURP** (closed-source), and Superhive's **"Brushed Shading"**. Prices could not be verified. The Lightning Boy Shader, Flair, Arnold Toon docs, Komikaze and UE Marketplace/Fab toon shaders were **not** verified with URLs.

### Cited Findings
- [course(paid)/code-addon] **Pencil+ 4 Line for Blender** (PSOFT). The add-on works with the separate "PSOFT Pencil+ 4 Render App" to render Pencil+ 4 lines, configured in a node editor. Product page: [psoft.co.jp/en/product/pencil/blender/](https://psoft.co.jp/en/product/pencil/blender/); docs: [docs.psoft.co.jp/plb400w/en/latest](https://docs.psoft.co.jp/plb400w/en/latest/index.html). The add-on source is [psofthouse/Pencil-4-Line-for-Blender](https://github.com/psofthouse/Pencil-4-Line-for-Blender) [fetched]. There are also Unity variants: [Pencil-4-Line-for-Unity-HDRP](https://github.com/psofthouse/Pencil-4-Line-for-Unity-HDRP) and [Pencil-4-Line-for-Unity-PPS](https://github.com/psofthouse/Pencil-4-Line-for-Unity-PPS) [found via code search]. Listed as "Paid" by devanshutak25/3d-resources [fetched]; price not verified. Versions for 3ds Max and Maya exist (per the assignment brief) but were not verified.
- [code-addon, paid] **MNPRX** (Artineering), the production successor to open MNPR for Maya — [artineering.io/projects/MNPRX/](https://artineering.io/projects/MNPRX/) [2nd-hand URL, from the MNPR README]; price not verified.
- [code-addon] **MooaToon** (UE5): open repo; licence and commercial terms at [mooatoon.com/docs/Licence/](https://mooatoon.com/docs/Licence/) [fetched README]; terms not read.
- [code-addon, paid] **NiloToonURP** (Unity): the full version is closed-source and available on request via email, per the NiloCat README — [UnityURPToonLitShaderExample](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) [fetched]
- [code-addon, paid] **Brushed Shading** (Superhive Market NPR shader) — [superhivemarket.com/products/brushedshading](https://superhivemarket.com/products/brushedshading) [2nd-hand URL, from Hoarbound]; price not verified.
- [tutorial, free] **Lightning Boy Studio** YouTube channel (toon/NPR for Blender) — [YouTube](https://www.youtube.com/channel/UCd9i2MKimSaKezat1xkn8-A/videos) [2nd-hand URL]. The paid "Lightning Boy Shader" product page was not found.
- [code-addon] Also mentioned in the [agmmnn/awesome-blender](https://github.com/agmmnn/awesome-blender) list [fetched], but without captured URLs: **Komikaze** (paid toon shader with free sample materials) and **Erito's Toon Shader for EEVEE** (paid, ArtStation).

### Inferences
- The free stack (Blender 5.3, Brushstroke Tools, open forks, Malt) now covers most needs. Paid tools remain most valuable for **production line rendering** (Pencil+ 4 is cross-DCC and consistent with Max/Maya pipelines) and for **turnkey Maya stylization** (MNPRX).

### Gaps
- No verified URLs or prices for: Lightning Boy Shader (Superhive/Gumroad), Artineering **Flair**, Arnold **Toon** shader documentation (Autodesk help), Komikaze, Erito's Toon Shader, Unreal Fab/Marketplace toon shaders, or paid NPR courses (CG Cookie, Gumroad, Domestika, etc.). All were blocked or unsearchable in this session and should be filled by another pass.
