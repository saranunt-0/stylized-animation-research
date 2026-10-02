# VFX (Effects Animation) for Stylized / Painterly 3D — Arcane, Project Gold, Mielgo — Tools, Techniques, Resources (as of Oct 2026)

> **Method and verification legend (read first).** In this session, page fetches were blocked by the egress proxy for almost every non-GitHub domain (befores & afters, Art of VFX, VFX Voice, 3DVF, 80.lv, studio.blender.org, docs.blender.org, developer.blender.org, realtimevfx.com, sakugabooru, jangafx, sidefx, actionvfx, youtube, itch.io). The shared web-search budget also ran out partway through. Each claim is tagged:
> - **(F)**: I fetched and read the page this session (mostly GitHub).
> - **(S)**: the URL and claim come from a web-search result summary. I could not open the page, so treat exact wording as approximate.
> - **(K)**: prior knowledge that I could not verify this session. Only a root-domain URL is given, and the item is **UNVERIFIED**.
>
> Category tags used on entries: `documentation` / `tutorial` / `recreation` / `code-addon` / `asset` / `course(paid)` / `talk`.

---

## Q1. How were Arcane's 2D FX made and integrated with 3D? Did Mielgo's films use 2D FX or 3D sims? What does Project Gold do for FX?

### Takeaway
On Arcane, Fortiche's FX were mostly hand-drawn 2D: smoke, fire and explosions were treated as 2D effects. A dedicated 2DFX team animated them over the 3D renders, reportedly in Toon Boom Harmony, and the result was composited, reportedly in Nuke. FX were drawn on twos against the 3D characters. Season 2 moved to a "more hybrid" FX technique that mixes 2D and 3D. Mielgo's films are mainly 3D characters set into painted 2D backgrounds and painted "3D paintings", with "a lot of 2D in post". Jibaro's water was a real 3D simulation (Houdini is reported). Project Gold has no 2D-FX pipeline. Its FX are Geometry Nodes / Simulation Nodes setups (particle emission from cracks, motion-trail particles, "-fx" shot files) plus the Brushstroke Tools add-on.

### Cited Findings

**Arcane / Fortiche: who did the FX and how**
- The Arcane episode "Oil and Water" won the 2022 Annie for Best FX (TV/Media). The FX team was Guillaume Degroote, Aurélien Ressencourt, Martin Touzé, Frédéric Macé and Jérôme Dupré (Fortiche). This confirms a named, dedicated FX unit. — (S) [Cartoon Brew Annie winners](https://www.cartoonbrew.com/awards/arcane-mitchells-vs-the-machines-dominate-the-annie-awards-analysis-full-winners-list-214196.html); (S) [Deadline 2022 Annie winners](https://deadline.com/2022/03/2022-annie-awards-winners-list-movies-tv-video-games-1234974570/)
- Season 2 won 7 Annies in Feb 2025, including Best FX. — (S) [Arcane official X post](https://x.com/arcaneshow/status/1888483561130315965); (S) [Fortiche blog: 2025 Annie Awards](https://forticheprod.com/blog/highlights/arcane-alongside-riot-games-french-animation-studio-fortiche-production-triumphs-at-the-2025-annie-awards/)
- Aurélien Ressencourt is "Lead 2DFX Animator" at Fortiche. His credits include Arcane, Imagine Dragons x J.I.D "Enemy" and Wakfu. — (S) [ArtStation portfolio](https://aurelien_ressencourt.artstation.com/projects); (S) [IMDb](https://www.imdb.com/name/nm8478310/)
- The 3DVF crew interview, conducted by Tom Kurcz (production coordinator), includes **Aurélien Ressencourt (lead 2DFX animator)** and **Yann Leroy (compositing supervisor)**. It is the most direct primary source on Arcane FX and compositing, but I could not fetch it, so its contents are not reproduced here. — (S) [3DVF: "Arcane: how does it feel to work on a major hit series?"](https://3dvf.com/en/arcane-how-does-it-feel-to-work-on-a-major-hit-series/) `talk`
- **Software:** "On Arcane, 2D FX was animated in Harmony on the renders which were then composited together." VFX Apprentice says its instructor Tom De Vis worked on Arcane. — (S) [VFX Apprentice: From VFX Apprentice to 2D FX Artist on Netflix's Arcane](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends) *(the strongest claim on FX software I found; it comes from an FX school's blog, and Fortiche itself did not confirm it in anything I retrieved)*
- **Conflicting/speculative:** a secondary SEO site says "tools like TVPaint or Adobe Animate were **likely** used". That is speculation and should not be cited as fact. The same site lists Maya, Photoshop and Nuke as the pipeline. — (S) [yelzkizi: What 3D software did Arcane use](https://yelzkizi.org/what-3d-program-did-arcane-use/) (low-quality secondary); contradicted by (S) [VFX Apprentice](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends) (Harmony)
- Alexis Wanneroy (Head of Character Animation) is summarized as saying that on the first Fortiche/Riot collaboration, "2D effects were done by hand, with 2D animators adding them on top of the 3D animation after the 3D animation was done". So FX were a downstream pass over finished 3D animation. — (S) [SyncSketch: The Making of Arcane, interview with Alexis Wanneroy](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) `talk`; related podcast (S) [iAnimate podcast with Alexis Wanneroy](https://ianimate.net/animationpodcast/arcane-magic-secrets-fortiche-lead-alexis-wanneroy-podcast) `talk`
- **Season 2:** at VIEW Conference (Turin), Pascal Charrue (co-founder) and Alexis Wanneroy described "a more hybrid technique for FX that combines 2D and 3D elements" as a development since S1. — (S) [3DVF: Fortiche shares the secrets behind Arcane S2 at VIEW](https://3dvf.com/en/fortiche-production-shares-the-secrets-behind-arcane-season-2-at-view-conference/) `talk`
- Julien Georgel (Art Director) on S2: "Because we use a mix of 2D and 3D techniques, our workflow is a little unusual." Basic FX relied on "the proven expertise of our long-standing 2D and 3D FX team". Smoke and fire were treated as 2D effects, and art direction focused on new Hexcore/Anomaly FX. — (S) [VFX Voice: Riot Games and Fortiche get revolutionary with Arcane S2](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/)
- Fortiche had about 450 artists at peak on S2, in the US and France. — (S) [VFX Voice S2 article](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/)
- **Team size and frame rate (secondary, lower confidence):** search summaries say most effects were made by "just four or five 2D artists working in digital painting software, animated 'on twos'". The same summaries say Fortiche animated these elements "at 12 fps … half the rate" so that Jinx's magic and explosions "stutter and spark at 12 fps" while character moments run at 24 fps. I could not trace these sentences to a named Fortiche crew member. They appear on secondary sites. — (S) [RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline); (S) [CraveFX](https://cravefx.com/blog/netflixs-arcane-lol-sheer-animated-style/); (S) [yelzkizi: Is Arcane 2D or 3D](https://yelzkizi.org/is-arcane-2d-or-3d/)
- Spider-Verse vs Arcane context: Sony's FX department built "a reusable library of 2D hand-drawn FX elements often animated on twos", combined with traditional 3D sims for explosions and fire. Arcane's painterly textures were hand-painted in Photoshop. — (S) [VFX Voice: The Return of Hand-Drawn and Stylized Effects Animation](https://vfxvoice.com/the-return-of-hand-drawn-and-stylized-effects-animation/)
- More breakdowns that I could not open: (S) [Art of VFX: Arcane](https://www.artofvfx.com/arcane/) and (S) [Art of VFX: Arcane Season 2](https://www.artofvfx.com/arcane-season-2/) `talk`; (S) [YouTube: "Arcane S2 texturing: Animating the hand-painted look"](https://www.youtube.com/watch?v=gCJIJG6Lz84) `talk`; (S) [Netflix Tudum: making of S2](https://www.netflix.com/tudum/features/arcane-season-two-behind-the-scenes); (S) [Creative Bloq on S2 animation](https://www.creativebloq.com/art/2d-animation/how-the-creative-team-behind-netflixs-arcane-pushed-the-animation-even-further-for-the-second-season); (S) [Autodesk: Fortiche, Golaem and crowds in S2](https://blogs.autodesk.com/media-and-entertainment/2025/03/26/crafting-crowds-fortiche-golaem-and-the-magic-of-arcane-season-2/)
- Visual reference for Arcane 2DFX: (S) [Art of Arcane tumblr: "various 2DFX showcase"](https://art-of-arcane.tumblr.com/post/677028964611571712/arcane-various-2dfx-showcase-twitter-gilad); (S) [Guillaume Degroote LinkedIn: "ARCANE ⚡ 2DFX"](https://by.linkedin.com/posts/guillaume-degroote-88494a11_arcane-2dfx-special-effects-animation-activity-6983038411464962048-BPmC); (S) [Aurélien Ressencourt LinkedIn 2dfx post](https://in.linkedin.com/posts/aurelien-ressencourt_2dfx-animation-vfx-activity-7028715244839411712-lGvi) `talk`
- `recreation`: Dmitry Sarkisov's "Arcane 2D FX Fan Art Collaboration". — (S) [ArtStation](https://www.artstation.com/artwork/DAYqde)
- One search summary attributes to "FX supervisor Julien Maunoury" the statement that Arcane's backgrounds are "100% digital paintings". I could not identify the originating page, so this is **unverified**. — (S) search summary referencing [3DVF interview](https://3dvf.com/en/arcane-how-does-it-feel-to-work-on-a-major-hit-series/)

**Alberto Mielgo (Pinkman.tv): The Witness, Jibaro, The Windshield Wiper**
- *The Windshield Wiper* (2021): Mielgo painted all backgrounds in Photoshop. The animation team led by Leo Sanchez Barbosa keyframe-animated 3D characters into the paintings, which Mielgo called "the old Disney technique … a 2D background with a 3D character on it". He paints exclusively in Photoshop and uses its integration with After Effects and Premiere. — (S) [AWN](https://www.awn.com/animationworld/windshield-wiper-reveals-many-sides-modern-love); (S) [IndieWire](https://www.indiewire.com/awards/industry/the-windshield-wiper-animated-short-alberto-mielgo-interview-1234693351/); (S) [befores & afters Q&A](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/) `talk`; (S) [Cartoon Brew interview](https://www.cartoonbrew.com/shorts/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html) `talk`
- On WW, many shots are painted because "from a distance they have the right amount of information about light and physics, but up close everything is loose". — (S) same group of WW interviews (originating page not isolated)
- *Jibaro* (LDR Vol. 3, 2022): Mielgo said "The underwater was very difficult … Simulating water that is on top and then underneath [required separate] textures, where the light reacts differently". He described simulating "water and splashes in contact with armor and jewelry" while everything collides. These are 3D sims, not 2D FX. He also said "A lot of the shots … are basically like a painting. Some others, we actually built a whole forest and we lighted it as we usually do in 3D. But there is a lot of 2D also in post-production". — (S) [IndieWire: Mielgo on Jibaro](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/) `talk`; also (S) [AWN](https://www.awn.com/animationworld/alberto-mielgo-tells-toxic-tale-sensuality-love-death-robots-volume-3), (S) [SlashFilm interview](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/)
- Jibaro toolset is reported as "Maya for animation and Houdini for other technical aspects". This is a secondary summary, so **lower confidence**. — (S) [Peliplat: Behind the creation of Jibaro](https://www.peliplat.com/en/article/10009911/behind-the-creation-of-jibaro-in-love-death-robots); see also (S) [80.lv: development process behind Jibaro](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro), (S) [Judit Navarro ArtStation: Jibaro](https://juditnavarro.artstation.com/projects/QnZ8Qr), (S) [Agora Studio: Jibaro](https://agora.studio/portfolio/706/jibaro)
- *The Witness* (LDR Vol. 1, 2019, produced with Blur, made by pinkman.tv): "3D paintings were used for shots that required a lot of camera movement, created using Blender". The team "decided to use a flat painting instead of a 3D modeled light". Levels were adjusted after each shot was composed and rendered. Everything was keyframed by hand, with no roto or mocap. — (S) [Zeno Pelgrims: LDR The Witness](http://www.zenopelgrims.com/project-ldr-the-witness.html); (S) [80.lv: Creating fantastic visuals in LDR](https://80.lv/articles/creating-fantastic-visuals-for-love-death-robots) *(the search summary blended these two pages, so I cannot say which sentence comes from which)*
- `recreation`: Aquib Hussain recreated a Jibaro water/dance scene in Houdini + Arnold. Splashes came from "collision VDBs", the splash layer was kept separate from the base flow, and the two were merged using light position transfer. — (S) [80.lv: Recreating a scene from LDR's Jibaro in Houdini and Arnold](https://80.lv/articles/recreating-a-scene-from-ldr-s-jibaro-in-houdini-and-arnold)
- `recreation`: (S) [80.lv: The Witness fan-art character](https://80.lv/articles/love-death-robots-fan-art-creating-the-character-from-the-witness); (S) [Sacha Veyrier: The Witness study (UE5)](https://lithium.artstation.com/projects/eJJlJG)

**Blender Studio Project Gold**
- Project Gold is Blender Studio's 16th open movie. It was released in Nov 2024 as "a technical showcase focused on stylized rendering" together with the free **Brushstroke Tools** add-on, and its project files target Blender 4.3. — (S) [Blender Studio: Project Gold](https://studio.blender.org/projects/gold/); (S) [Project Gold premiere blog](https://studio.blender.org/blog/project-gold-premiere/); (S) [Blender Studio X post](https://x.com/BlenderStudio_/status/1854560062036942921); (S) [CG Channel: free Brushstroke Tools](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/); (S) [Creative Bloq: how to watch Gold + get files](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools)
- Showcased techniques: light linking, **Simulation Nodes**, Geometry Nodes-based tools, viewport-compositor extensions, and art-directable NPR in Cycles. The project's aim was to push Blender's "2D/3D animation, using ongoing developments on Geometry Nodes, Grease Pencil and Cycles". It began as Jericca Cleland's short and was refocused into a showcase. — (S) [Project Gold page](https://studio.blender.org/projects/gold/); (S) [Announcing Project Gold](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/); (S) [Project Gold update](https://studio.blender.org/blog/project-gold-update/)
- **FX-specific Gold content:** the project's content list includes "Geometry Nodes Particle Emission from Cracks" and "Motion Trail - Particle FX". Shot files with the suffix "*-fx*" "contain simulation or setups to generate various effects within the shot". Only titles were retrievable, not the techniques themselves. — (S) [Production logs index](https://studio.blender.org/projects/gold/production-logs/); (S) [Shot production file example 265_0010](https://studio.blender.org/projects/gold/3d823d3a8c9db8/?asset=7530); (S) [Production Log 04](https://studio.blender.org/blog/gold-production-log-04/) `documentation`
- Watch: (S) [YouTube: Project Gold – Blender stylized rendering showcase](https://www.youtube.com/watch?v=nV_awXI9XJY) `talk`

### Inferences
- The Arcane FX recipe an indie team can copy is: lock the 3D animation and render it. Then draw FX on twos in a 2D package, using the rendered plate as underlay. Finally composite with glows/blur and texture overlays. Season 2 shows that a hybrid approach is acceptable: 3D sim or instanced elements rendered to look drawn, alongside hand-drawn FX.
- Mielgo's look comes from painting (backgrounds, projected "3D paintings", 2D post-paint) more than from FX drawing. Where physical interaction matters (Jibaro water), he used real 3D sims and stylized them through texturing and compositing. For a Mielgo-style project, put the effort into sim-plus-paint integration, not hand-drawn FX.
- Project Gold is the best free reference for procedural stylized FX in Blender (Simulation Nodes particles, motion trails). It is not a reference for hand-drawn FX.

### Gaps
- I could not retrieve the full text of the 3DVF crew interview (Ressencourt/Leroy), the Art of VFX Arcane interviews, or the VFX Apprentice Arcane article. So Harmony vs TVPaint, Nuke integration details, use of camera-projected FX cards, and FX frame rates are **not confirmed by a named Fortiche FX artist** in anything I read.
- The claims about "4–5 2D FX artists" and "12 fps vs 24 fps for Jinx" could not be traced to a primary source. Treat them as unverified.
- I found no Fortiche talk (SIGGRAPH, Annecy, etc.) dedicated to 2DFX with an accessible URL.
- I could not confirm which Jibaro water/FX elements were sims versus painted. "Houdini" is a secondary claim.
- The Gold production logs on "particle emission from cracks" and "motion trail" were not readable, so their methods are unknown.

---

## Q2. Which free/open-source tools and repos best support 2D-over-3D FX in an indie pipeline, and what are their limitations? (incl. integration techniques)

### Takeaway
**Blender Grease Pencil v3** (Blender 4.3+, current 5.x) is the strongest free option for 2D FX that live inside the 3D scene and camera. It has layer groups, Geometry Nodes access, and (since 5.0) motion blur. **OpenToonz 1.8 / Tahoma2D 1.6** give the closest free equivalent to Harmony's FX schematic for drawing over rendered plates. **Krita 5.3/6.0** is the best free raster "paint the FX" tool. Pencil2D is simple but limited, and Synfig is vector/tween oriented and a weak fit for frame-by-frame FX. Integration usually means either drawing GP strokes in camera space or rendering 2D FX as image sequences and placing them as cards or comp layers. Timing on 2s/3s is enforced by holding keys.

### Cited Findings

**Blender Grease Pencil (GPv3)** — `documentation`
- Blender 4.3 shipped the third-generation, rewritten Grease Pencil. It adds layer groups and Geometry Nodes integration, multi-threading, 2.5–3.4× smaller files, a rewritten curve-fitting smoother, and an eraser that cuts strokes. Brushes became assets. **Files saved in 4.3 are not backward-compatible** with older versions. — (S) [Blender 4.3 Grease Pencil release notes](https://developer.blender.org/docs/release_notes/4.3/grease_pencil/); (S) [Blender 4.3 release page](https://www.blender.org/download/releases/4-3/); (S) [CG Channel: 4.3 lets you control GP with Geometry Nodes](https://www.cgchannel.com/2024/10/blender-4-3-lets-you-control-grease-pencil-with-geometry-nodes/)
- Blender 5.0 Grease Pencil added **motion blur for GP** with adjustable "Motion Blur Steps", a Pen tool in edit mode, Bézier/Catmull-Rom interpolation, Sharp/Flat corner types, and SVG export of Bézier/Catmull-Rom/NURBS (uniform width only). — (S) [Blender 5.0: Grease Pencil release notes](https://developer.blender.org/docs/release_notes/5.0/grease_pencil/)
- Blender 5.1 was released in Mar 2026 with Geometry Nodes expansions. Grease Pencil release notes for **5.3** are being written in the developer docs, which means 5.3 is in development as of mid/late 2026. — (S) [AlternativeTo: Blender 5.1](https://alternativeto.net/news/2026/3/3d-software-blender-5-1-refines-key-workflows-boosts-performance-and-expands-geometry-nodes); (S) [blender-developer-docs commit: 5.3 GP notes](https://projects.blender.org/blender/blender-developer-docs/commit/916178295a39be08e7c18a52ba8991de718963c3); (S) [devtalk weekly 20 Apr 2026](https://devtalk.blender.org/t/20-april-2026/44972)
- The FLIP Fluids README lists compatibility with "Blender 4.5 through 5.2", which implies 5.2 is a shipped release. — (F) [rlguy/Blender-FLIP-Fluids](https://github.com/rlguy/Blender-FLIP-Fluids)
- Grease Pencil Tools by Samuel Bernou (Pullusb) is GPL-3. It provides box deform, canvas rotation, viewport timeline scrub, layer navigator and textured-brush-pack import. It "was bundled in Blender from version 2.91 to 4.1" and is now on the Extensions platform. — (F) [Pullusb/greasepencil_tools](https://github.com/Pullusb/greasepencil_tools) `code-addon`; version history (S) [extensions.blender.org: Grease Pencil Tools versions](https://extensions.blender.org/add-ons/grease-pencil-tools/versions/)

**Free Grease Pencil helper add-ons (GitHub; activity dates from GitHub search metadata)** — all `code-addon`. Stars and "updated" dates come from GitHub search (F). I did not verify GPv3 compatibility one by one unless noted.
- [Pullusb/GP_onion_peel](https://github.com/Pullusb/GP_onion_peel): custom onion skinning, updated 2026-09.
- [Pullusb/GP_clipboard](https://github.com/Pullusb/GP_clipboard): world-space copy/paste of strokes across layers and files.
- [Pullusb/Box_deform](https://github.com/Pullusb/Box_deform): last updated 2022 and superseded by the Grease Pencil Tools version, so likely **outdated** as a standalone.
- [Pullusb/GP_refine_strokes](https://github.com/Pullusb/GP_refine_strokes) and [Pullusb/GP_brush_fill](https://github.com/Pullusb/GP_brush_fill): stroke refinement and a pixel-style fill brush.
- [spikysaurus/Blender-SakugaGP](https://github.com/spikysaurus/Blender-SakugaGP): "Free Grease Pencil addon made by 2D Animator for 2D Animators", GPL-3, created Dec 2025. Feature list not retrieved. (F)
- [SietseB/GP-Tool-Wheel](https://github.com/SietseB/GP-Tool-Wheel): quick tool switching, updated 2026-09.
- [okuma10/RenderGPKeyframes](https://github.com/okuma10/RenderGPKeyframes): "render blender grease pencil keyframes only". Useful for exporting FX held on 2s/3s without duplicate frames.
- [mercuriousreign/Blender-BIS2GP](https://github.com/mercuriousreign/Blender-BIS2GP): batch image sequence to Grease Pencil. A route for bringing FX drawn in Krita/OpenToonz into GP.
- [bergamote/greaspencil_nudge_frames](https://github.com/bergamote/greaspencil_nudge_frames): nudge GP keyframes for timing.
- [Pullusb/Tesselate_texture_plane](https://github.com/Pullusb/Tesselate_texture_plane): triangulates a textured plane while discarding alpha zones. Good for tight FX cards and sprites in 3D.
- [Pullusb/reference_to_image_plane](https://github.com/Pullusb/reference_to_image_plane): converts image references into image planes.
- [Pullusb/storytools](https://github.com/Pullusb/storytools): GP storyboarding toolset.
- (F) awesome-blender also lists [ndee85/coa_tools](https://github.com/ndee85/coa_tools) (cutout 2D, **likely outdated**) and [doakey3/GreaseWriter](https://github.com/doakey3/GreaseWriter) via [agmmnn/awesome-blender](https://github.com/agmmnn/awesome-blender) (7.4k stars).

**OpenToonz / Tahoma2D** — `documentation` / `code-addon`
- OpenToonz is open-source 2D animation software based on Toonz Studio Ghibli Version, under a Modified BSD license (excluding thirdparty and MyPaint brushes), and "may be freely used or modified for business or personal purposes". — (F) [opentoonz/opentoonz](https://github.com/opentoonz/opentoonz)
- **OpenToonz V1.8** is the newest stable. The GitHub releases page lists "OpenToonz V1.8 – 19 Jun", after "V1.8 Release Candidate – 29 May" and V1.7.1. Its notes include new FX: "Smoother Fx Iwa", "Naru lazy brush fx", and "draggable cage controls to corner pin fx", plus OCA import. A search summary dates V1.8 to **June 20, 2026**. The GitHub page shows no year, and the fetch tool's own year inference (2024) conflicted with that, so the year is **unconfirmed**. Nightly builds are still published (tag "nightly build 2026-10-02"). — (F) [OpenToonz releases](https://github.com/opentoonz/opentoonz/releases); (F) [V1.8 tag](https://github.com/opentoonz/opentoonz/releases/tag/v1.8.0); (S) [OpenToonz fandom: Releases and Builds](https://opentoonz.fandom.com/wiki/Releases_and_Builds)
- DWANGO OpenToonz plugins (BSD-3) add 18 FX plugins, including LightBloom, LightGlare, LightIncident, CurlNoise, ChromaticAberration, Drip, PencilHatching and Waveglass. They require the OpenCV3 runtime and VC++ 2013 redist, and the prebuilt package targets "OpenToonz 1.0". This makes them **likely outdated or hard to install** on 1.8. — (F) [opentoonz/dwango_opentoonz_plugins](https://github.com/opentoonz/dwango_opentoonz_plugins); SDK (F-search) [opentoonz/plugin_sdk](https://github.com/opentoonz/plugin_sdk)
- Forks: **Tahoma2D** has active monthly fix releases (1.6 → 1.6.3) and a nightly dated 2026-09-24. Release years are not displayed. The **Morevna OpenToonz** edition is flagged **discontinued**. OTX is a macOS experimental build. — (F) [Tahoma2D releases](https://github.com/tahoma2d/tahoma2d/releases); (F) [Awesome-OpenToonz list](https://github.com/EthanBoiLol/Awesome-Opentoonz) (links [tahoma2d.org](https://tahoma2d.org/), [manongjohn/OTX](https://github.com/manongjohn/OTX))

**Krita** — `documentation`
- Krita 6.0 is a Qt6 port shipped alongside 5.3 (Qt5). Release-notes summaries describe animation playback reworked on the **MLT framework** to fix audio/video sync, video export that no longer needs a user-supplied FFmpeg, animation render on Android, and HDR metadata for animation renders. Point releases 5.3.4 / 6.0.4 were out by mid-2026. — (S) [Krita 5.3 and 6.0 release notes](https://krita.org/en/release-notes/krita-5-3-release-notes/); (S) [Linuxiac: Krita 5.3.4 and 6.0.4](https://linuxiac.com/krita-5-3-4-and-6-0-4-are-out-with-android-and-qt-6-updates/); (S) [Krita monthly report Aug 2026](https://krita.org/en/posts/2026/monthly-report-2608/); (S) [Ubuntuhandbook: Krita 6.0 beta](https://ubuntuhandbook.org/index.php/2026/02/krita-6-0-beta-qt6-wayland/) *(the exact 6.0 final date of "Feb 5, 2026" comes from a search summary and is unconfirmed; the Ubuntuhandbook URL refers to a Feb 2026 **beta**)*

**Pencil2D** — `documentation`
- Stable is **v0.7.2 (13 Mar 2026)**, a bug-fix/QoL release with 18 fixes. v0.7.0 shipped in Oct 2024. — (S) [Pencil2D v0.7.2](https://www.pencil2d.org/2026/03/pencil2d-0.7.2-release.html); (S) [Pencil2D v0.7.0](https://www.pencil2d.org/2024/10/pencil2d-0.7.0-release.html); (S) [GitHub releases](https://github.com/pencil2d/pencil/releases)

**Synfig** — `documentation`
- GitHub releases show "Release build (v1.5.5)" marked **Latest** ("16 Mar"), with v1.4.5 ("19 May") as the last 1.4.x. Wikipedia lists stable as **1.4.5 (May 19, 2024)**. The 1.5.x line is the development series. — (F) [synfig/synfig releases](https://github.com/synfig/synfig/releases); (S) [Wikipedia: Synfig](https://en.wikipedia.org/wiki/Synfig) *(conflict between the "Latest" label and the stable designation; check before recommending)*

**Integration techniques (2D FX + 3D)**
- Arcane: FX animated in Harmony "on the renders" and then composited. — (S) [VFX Apprentice](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends)
- Spider-Verse: a library of 2D hand-drawn FX on twos mixed with 3D sims. — (S) [VFX Voice](https://vfxvoice.com/the-return-of-hand-drawn-and-stylized-effects-animation/)
- The Witness: Blender-built "3D paintings" (painting projected onto geometry) for camera-moving shots. — (S) [Zeno Pelgrims](http://www.zenopelgrims.com/project-ldr-the-witness.html)
- GPv3 + Geometry Nodes (4.3+) lets procedural setups read and modify GP strokes. GP motion blur (5.0) helps hand-drawn FX sit with motion-blurred 3D renders. — (S) [4.3 GP notes](https://developer.blender.org/docs/release_notes/4.3/grease_pencil/); (S) [5.0 GP notes](https://developer.blender.org/docs/release_notes/5.0/grease_pencil/)

### Inferences
- **Recommended indie pipeline (free):**
  1. Block and lock the 3D, then render a playblast or plate.
  2. Draw FX either (a) as GPv3 objects parented to the camera or placed in world space, so they track with the 3D and get depth, lighting and motion blur, or (b) in OpenToonz/Tahoma2D or Krita over the plate, exported as PNG sequences with alpha.
  3. Bring sequences back as camera-facing image planes or cards. Use Tesselate_texture_plane / Images-as-Planes so the cards occlude correctly, or comp them in Blender's compositor or Natron.
  4. Hold drawings on 2s/3s through keyframe spacing. RenderGPKeyframes avoids rendering duplicate frames.
- **Limitations to flag:**
  - GP's FX toolset is thinner than Harmony's node FX: no built-in node "glow/tone/highlight" per drawing, so the glow must come from the compositor.
  - OpenToonz has a steep UX, and its legacy plugins are tied to old OpenCV builds.
  - Krita has no camera or 3D-plate awareness beyond a reference layer.
  - Pencil2D has minimal compositing.
  - Synfig is tween-centric.
  - GPv3 files saved in 4.3+ do not open in older Blender, which matters when add-ons lag behind.
- Many older GP add-ons (pre-2024) were written for GPv2's Python API. Expect breakage on 4.3+ unless the repo shows 2025–2026 updates. The Pullusb add-ons generally show 2026 updates (GitHub metadata).

### Gaps
- I could not open docs.blender.org to cite the Grease Pencil manual pages (2D Animation template, Time Offset modifier, layer/stroke placement, "Stroke Placement: Surface", and so on). (K) These features are expected in the manual at the root [docs.blender.org](https://docs.blender.org/), **UNVERIFIED this session**.
- I could not verify GPv3 compatibility for each small add-on, or confirm whether OpenToonz 1.8 still ships its built-in Particles FX unchanged. (K) OpenToonz has long shipped a "Particles" FX node, **UNVERIFIED this session**.
- No primary source confirmed whether Fortiche used camera-projected 2D FX cards.

---

## Q3. Which free Blender add-ons / node groups / repos (and Houdini/realtime tools) give stylized 3D FX? (name, function, license, URL, compatibility)

### Takeaway
Free stylized-3D-FX tooling for Blender is scattered. The most production-proven free pieces are:
- Blender's own Geometry/Simulation Nodes, used as Project Gold did.
- Blender Studio's **Brushstroke Tools** (Gold, Blender 4.3+).
- NPR renderers **Malt** (MIT) and **Goo Engine** (GPL fork; a community port exists for 5.1).
- Sprite-sheet/flipbook exporters (MIT) for realtime-style flipbook FX.
- **SideFX Labs** (free, open source) on the Houdini side.

There is **no widely adopted free "toon fire/smoke" add-on repo**. GitHub search turned up only tiny or new projects. Paid FLIP Fluids is GPL/MIT source-available.

### Cited Findings

**Blender: stylized/NPR rendering and FX-adjacent add-ons**
| Name | Function | License | Compat / status | URL | Cat. |
|---|---|---|---|---|---|
| Brushstroke Tools (Blender Studio) | GN-based procedural/manual 3D brushstrokes on surfaces (Project Gold look) | Free extension; license not verified (**K**: Blender extensions are GPL-compatible) | Released Nov 2024 with Gold for **4.3** | (S) [CG Channel](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/) | code-addon |
| Malt | Real-time NPR render framework as a Blender add-on; GLSL + Python pipelines, VSCode integration | **MIT** | "Latest Blender stable". Needs OpenGL 4.5, **Windows/Linux only**. Active (updated 2026-09-27) | (F) [bnpr/Malt](https://github.com/bnpr/Malt) | code-addon |
| Goo Engine | Blender fork with 4 custom EEVEE shader nodes + light groups for anime NPR | **GPL-3** | Builds distributed via Patreon. Base version not shown. Updated 2026-10-01 | (F) [dillongoostudios/goo-engine](https://github.com/dillongoostudios/goo-engine) | code-addon |
| bb-yi/blender | Community port of Goo Engine + NPR prototype to **Blender 5.1** | GPL-3 | Created Mar 2026, 142★ | (F) [bb-yi/blender](https://github.com/bb-yi/blender) | code-addon |
| FLIP Fluids | Liquid sim add-on (splashes, used for stylized water when re-shaded) | Add-on **GPL**, engine **MIT**; sold on Superhive, free demo | **Blender 4.5–5.2** | (F) [rlguy/Blender-FLIP-Fluids](https://github.com/rlguy/Blender-FLIP-Fluids) | code-addon (paid) |
| Molecular Script | Particle-collision sim add-on (granular/sticky particles) | Not shown on page | README mentions 3.1/3.2 testing. **4.x/5.x compat unverified** | (F) [scorpion81/Blender-Molecular-Script](https://github.com/scorpion81/Blender-Molecular-Script) | code-addon |
| Jet-Fluids | Jet fluid simulator integration | — | Listed on awesome-blender. **Likely outdated** (unverified) | (F-list) [PavelBlend/blender_jet_fluids_addon](https://github.com/PavelBlend/blender_jet_fluids_addon) | code-addon |
| RainGeneratorBlend | GN group that spawns rain instances for Mantaflow/FLIP | **CC BY 4.0** | Version not stated (2022) | (F) [NHodgesVFX/RainGeneratorBlend](https://github.com/NHodgesVFX/RainGeneratorBlend) | code-addon |
| SVFXT – Simple Toon VFX | One-click toon/anime VFX: Impact, Energy Ball, Swoosh, Dust, Electric, Beam, Wind | **License not stated** | New (Sep 2026), 0★. **Unvetted** | (F) [KomikusAdha/SVFXT…](https://github.com/KomikusAdha/SVFXT-Simple-Visual-Effects-Toon---Simple-Toon-VFX-for-Blender) | code-addon |
| Blender-Lightning-Generator | Lightning generator | — | Mar 2026, 0★. **Unvetted** | (F-search) [VAST-FRAME/Blender-Lightning-Generator](https://github.com/VAST-FRAME/Blender-Lightning-Generator) | code-addon |
| Geometry-Nodes-Simulation (legacy hack) | Pre-Simulation-Nodes trick for frame-to-frame GN sims | — | Blender 3.2. **Outdated**: Simulation Zones now built in | (F-search) [noblec04/Geometry-Nodes-Simulation](https://github.com/noblec04/Geometry-Nodes-Simulation) | code-addon |
| Free GN generator packs (Curtis Holt, Blenderesse "Melt", etc.) | Free GN generators, not FX-specific | Various (Gumroad) | — | (F-list) via [agmmnn/awesome-blender](https://github.com/agmmnn/awesome-blender), e.g. [blenderesse.gumroad.com](https://blenderesse.gumroad.com), [curtisjamesholt.gumroad.com](https://curtisjamesholt.gumroad.com) | asset |

**Flipbook / sprite-sheet tooling (realtime-VFX technique applied to film cards)** — `code-addon`
| Name | Function | License | Compat | URL |
|---|---|---|---|---|
| blender-spritesheets | Render animations to a sprite sheet + JSON. Unity/Godot importers | **MIT** | Developed on **2.81**. 4.x/5.x **unverified**. 268★, updated 2026-09 | (F) [theloneplant/blender-spritesheets](https://github.com/theloneplant/blender-spritesheets) |
| Spritify | Converts rendered frames into a sprite sheet after render (ImageMagick) | — | Updated 2025-12 | (F-search) [FreezingMoon/Spritify](https://github.com/FreezingMoon/Spritify) |
| blender-texture-atlas-generator | Build texture atlases (flipbooks) from image sequences | — | Updated 2026-05 | (F-search) [JackTheFoxOtter/blender-texture-atlas-generator](https://github.com/JackTheFoxOtter/blender-texture-atlas-generator) |
| SpriteSheetMaker | 3D anim → sprite sheet with toggleable pixelation | — | Nov 2025 | (F-search) [ManasMakde/SpriteSheetMaker](https://github.com/ManasMakde/SpriteSheetMaker) |
| flipbook-packer | CLI/Python: pack sequences into atlas, or "Stagger"/"Super" channel-packed flipbooks (up to 256 frames across RGBA) | **MIT** | Python 3.12 + Pillow | (F) [stylerhall/flipbook-packer](https://github.com/stylerhall/flipbook-packer) |
| TFlow (paid) | Motion-vector + motion-blur generation for smooth flipbook frame blending | Commercial (Unity Asset Store / UE Marketplace) | Unity/UE | (F) [Tuatara-VFX/TFlow](https://github.com/Tuatara-VFX/TFlow) |

**Houdini (free paths)**
- **SideFX Labs** is "a free, open-source, and artist-friendly toolset developed by SideFX" with "hundreds of HDAs", game-engine plugins and VEX functions. Its topics include real-time and VFX, and it has an examples repo. — (F) [sideeffects/SideFXLabs](https://github.com/sideeffects/SideFXLabs); (F-search) [sideeffects/SideFXLabsExamples](https://github.com/sideeffects/SideFXLabsExamples) `code-addon`
- Jibaro-style water recreation in Houdini (FLIP, collision VDBs, separate splash layer). — (S) [80.lv](https://80.lv/articles/recreating-a-scene-from-ldr-s-jibaro-in-houdini-and-arnold) `recreation`

### Inferences
- For Arcane-like stylized 3D FX in Blender without paid tools, the practical stack is:
  - Simulation Zones in Geometry Nodes for particle and trail behaviour, as in Gold's "particle emission from cracks" and "motion trail".
  - Instancing of hand-drawn sprite cards or GP strokes on particles. This gives a 2D look with 3D motion.
  - Toon-ramp shading (Shader-to-RGB + ColorRamp in EEVEE, or Malt / Goo Engine) on mesh-based smoke blobs, which avoids volumetrics.
  - Mantaflow or FLIP for splashes, re-meshed and toon-shaded, as in the Jibaro-like "sim then paint" approach.
- Realtime-VFX practice carries over to film directly. Flipbooks on cards, channel packing (flipbook-packer), and motion-vector frame blending (the TFlow concept) let one hand-drawn or simulated FX element be reused many times. This is the same idea as Sony's "library of 2D FX elements" ([VFX Voice](https://vfxvoice.com/the-return-of-hand-drawn-and-stylized-effects-animation/)).
- Most "sprite sheet" add-ons target game export and are older (2013–2020 origins). Test them on Blender 4.5/5.x before relying on them.

### Gaps
- I could not open extensions.blender.org or projects.blender.org, so the Brushstroke Tools license, version and 5.x compatibility are **unverified**.
- GitHub searches for "stylized fire geometry nodes", "toon smoke" and "explosion blender addon" returned **no relevant repos**. Popular free stylized-FX node groups seem to be distributed on Gumroad, Superhive or YouTube descriptions rather than GitHub, and I could not search those.
- realtimevfx.com (community forum with sketchbook/challenge threads) could not be fetched. (K) Root: [realtimevfx.com](https://realtimevfx.com/), **UNVERIFIED this session**.
- I could not confirm which SideFX Labs HDAs cover flipbooks, texture sheets or motion vectors. (K) Labs has long included a "Texture Sheets"/flipbook ROP and motion-vector tools, **UNVERIFIED**.
- Toon-shaded Mantaflow volumes in EEVEE Next (4.2+) or Cycles: I found no citable source this session.

---

## Q4. Best free learning resources for effects animation (2D and stylized 3D), incl. sakuga study and free FX asset libraries

### Takeaway
VFX Apprentice is the main hub for 2D FX training that names Arcane alumni. It has free Harmony intro lessons, a free 2D-FX asset opt-in, and paid courses. For timing study, Sakugabooru plus frame-stepping browser extensions are the standard free route. CC0 sprite and particle packs (Kenney, Brackeys VFX Bundle) cover flipbook-ready elements. Most deep "how Arcane did it" material is in talks and articles, not free tutorials.

### Cited Findings

**Tutorials / free training**
- VFX Apprentice free training hub. — (S) [Free VFX Training & Game Animation Courses](https://www.vfxapprentice.com/free-vfx-training) `tutorial`
- Free 5-part "Intro to Toon Boom Harmony" for 2D FX. It covers workspace setup, preferences, node-based glow/blur/transparency and exporting. — (S) [VFX Apprentice: Free Toon Boom Harmony tutorial](https://www.vfxapprentice.com/blog/intro-toon-boom-harmony-animation) `tutorial`
- "What is the Best Animation Software to Create 2D FX?" (VFX Apprentice blog; contents not retrieved). — (S) [link](https://www.vfxapprentice.com/blog/best-animation-software-2d-fx) `tutorial`
- Arcane alumni article (above), useful as a career and workflow reference. — (S) [VFX Apprentice: 2D FX Artist on Arcane](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends) `talk`

**Sakuga / timing study**
- Sakugabooru browser helpers: **Sakuga-Extended** ("previews on posts, frame control on videos") and **sakugaEnhancer** (refined search). Frame stepping is essential for counting 2s/3s in FX cuts. — (F-search) [ftLoic/Sakuga-Extended](https://github.com/ftLoic/Sakuga-Extended); (F-search) [Punyesh/sakugaEnhancer](https://github.com/Punyesh/sakugaEnhancer) `code-addon`
- Arcane 2DFX reels for frame-by-frame study. — (S) [Art of Arcane 2DFX showcase](https://art-of-arcane.tumblr.com/post/677028964611571712/arcane-various-2dfx-showcase-twitter-gilad); (S) [Ressencourt portfolio](https://aurelien_ressencourt.artstation.com/projects) `asset` (reference only)

**Stylized 3D FX learning**
- Project Gold production logs and shot files (including "-fx" files with sim setups) are downloadable from Blender Studio. They are the best free real-production reference for GN/Simulation-Nodes stylized FX. Some Blender Studio content is subscription-gated (**K**, unverified). — (S) [Gold production logs](https://studio.blender.org/projects/gold/production-logs/); (S) [shot file example](https://studio.blender.org/projects/gold/3d823d3a8c9db8/?asset=7530) `documentation`
- `recreation`: Jibaro-in-Houdini breakdown (S) [80.lv](https://80.lv/articles/recreating-a-scene-from-ldr-s-jibaro-in-houdini-and-arnold); Arcane 2D FX fan collab (S) [ArtStation](https://www.artstation.com/artwork/DAYqde)

**Free FX asset libraries (licenses as stated by the source; verify before use)** — `asset`
- **Kenney Particle Pack**: PNG/vector particle sprites, **CC0**. — via (F) [GameAssets curated index](https://github.com/JackLuguibin/GameAssets) → [kenney.nl/assets/particle-pack](https://kenney.nl/assets/particle-pack)
- **Brackeys VFX Bundle**: multi-author particle textures and flipbooks, "approximately CC0", and the index says to **check the itch page and in-pack notices**. — via (F) [GameAssets index](https://github.com/JackLuguibin/GameAssets) → [brackeysgames.itch.io/brackeys-vfx-bundle](https://brackeysgames.itch.io/brackeys-vfx-bundle) (page itself blocked)
- **OpenGameArt**: mixed licenses per item (search "particle", "vfx", "slash"). — via (F) [GameAssets index](https://github.com/JackLuguibin/GameAssets) → [opengameart.org](https://opengameart.org/)
- **Poly Haven / ambientCG / 3dtextures.me**: CC0 textures, useful as noise and breakup maps for painterly FX shaders, not FX sequences. — via (F) [GameAssets index](https://github.com/JackLuguibin/GameAssets) → [polyhaven.com](https://polyhaven.com/), [ambientcg.com](https://ambientcg.com/), [3dtextures.me](https://3dtextures.me/)
- **VFX Apprentice 2D FX Assets** (free with email opt-in; license **not verified**). — (S) [Opt-in: 2D FX Assets](https://www.vfxapprentice.com/opt-in-2DFX-Assets)
- **OpenToonz sample files**. — (F-list) [opentoonz/opentoonz_sample](https://github.com/opentoonz/opentoonz_sample)
- **ActionVFX free packs**: (K) free stock-footage elements (explosions, smoke, muzzle flashes) from [actionvfx.com](https://www.actionvfx.com/). **UNVERIFIED this session** (site blocked; license terms not checked). Photoreal stock needs heavy stylization (posterize, edge-detect, paint-over) to fit an Arcane-like look.

### Inferences
- Learning path:
  1. Elemental FX theory (Gilland's books, paid) and VFX Apprentice free lessons.
  2. Sakuga timing study with frame stepping.
  3. Rebuild the same element (fire loop, smoke puff, explosion) in GP or OpenToonz on 2s.
  4. Port it to 3D as a flipbook card or GN-instanced sprites.
  5. Study the Gold "-fx" files for procedural stylization.
- CC0 sprite packs are a fast way to prototype FX cards, but they look "game-y". For Arcane or Mielgo fidelity, expect to hand-draw or paint over them.

### Gaps
- I could not search YouTube (blocked), so I cannot give verified URLs for free 2D-FX channels. (K) Commonly cited creators include VFX Apprentice's own YouTube channel and Joseph Gilland, **UNVERIFIED this session; no URLs given**.
- sakugabooru.com could not be fetched to cite tag pages (e.g. "effects", "fire", "smoke", "explosions", "liquid"). (K) Root: [sakugabooru.com](https://www.sakugabooru.com/), **UNVERIFIED this session**.
- **Joseph Gilland, *Elemental Magic* Vol. I (2009) & Vol. II (2011)**: (K) the classic paid books on hand-drawn FX (fire, water, smoke, explosions, magic), published by Focal Press/Routledge. **No URL found this session; UNVERIFIED.**
- I could not verify ActionVFX free-pack or JangaFX free-asset license terms.

---

## Q5. Paid tools / courses: one-line summaries + links

### Takeaway
On the paid side, Toon Boom Harmony is the tool with a credible Arcane link (via VFX Apprentice). TVPaint is the classic raster 2D-FX tool. EmberGen (JangaFX) is real-time volumetrics with flipbook export. Houdini Apprentice is free for non-commercial use, with Indie as the low-cost commercial tier. VFX Apprentice sells the most relevant 2D-FX courses. Prices could not be verified this session.

### Cited Findings
- **Toon Boom Harmony**: industry 2D package with node-based FX (glow, blur, transparency). Reported as the tool Arcane's 2D FX were animated in, over renders. — (S) [VFX Apprentice Arcane article](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends); vendor (K) [toonboom.com](https://www.toonboom.com/) **UNVERIFIED** (price not checked). `documentation`
- **TVPaint Animation**: (K) bitmap frame-by-frame 2D software popular for hand-drawn FX in European studios, perpetual license. [tvpaint.com](https://www.tvpaint.com/) **UNVERIFIED**. A secondary site only *speculated* that Arcane used it. — (S) [yelzkizi](https://yelzkizi.org/what-3d-program-did-arcane-use/)
- **Adobe Animate**: (K) vector/timeline 2D tool (Creative Cloud subscription). (K) Adobe announced plans in early 2026 to discontinue Animate and then said it would keep it available in a maintenance-only state. **UNVERIFIED this session; check before recommending.** [adobe.com](https://www.adobe.com/) `documentation`
- **EmberGen (JangaFX)**: (K) real-time GPU fire/smoke/explosion simulator that exports VDB and image-sequence/flipbook output, popular with realtime-VFX artists and usable for stylized film FX plates. [jangafx.com](https://jangafx.com/) **UNVERIFIED** (pricing not checked).
- **Houdini Apprentice / Indie (SideFX)**: (K) Apprentice is free and non-commercial (watermarked, render-resolution-capped, non-commercial file format). Indie is the low-cost commercial tier for small revenue. [sidefx.com](https://www.sidefx.com/) **UNVERIFIED** (limits and price not checked). Free SideFX Labs works on top: (F) [SideFXLabs](https://github.com/sideeffects/SideFXLabs).
- **FLIP Fluids** (Blender liquid add-on): sold on Superhive (formerly Blender Market), free demo, Blender 4.5–5.2. — (F) [GitHub README](https://github.com/rlguy/Blender-FLIP-Fluids)
- **Goo Engine builds**: distributed through DillonGoo Studios' Patreon. Source is GPL-3 on GitHub. — (F) [goo-engine](https://github.com/dillongoostudios/goo-engine)
- **TFlow**: paid motion-vector flipbook tool (Unity/UE). — (F) [Tuatara-VFX/TFlow](https://github.com/Tuatara-VFX/TFlow)
- **VFX Apprentice paid courses** (all `course(paid)`; prices not retrieved):
  - [Tradigital 2D FX](https://www.vfxapprentice.com/tradigital-2d-fx) (S)
  - [Applied Foundations – FX Animations](https://www.vfxapprentice.com/courses/applied-foundations-animations) (S)
  - [Intro to Toon Boom Harmony](https://www.vfxapprentice.com/courses/intro-toon-boom-harmony) (S)
  - [FX Design Principles](https://www.vfxapprentice.com/courses/fx-design-principles) (S)
  - [Masters of Motion](https://www.vfxapprentice.com/masters-of-motion) (S)
- ***Elemental Magic* Vols. I–II (Joseph Gilland)**: (K) paid books, the standard reference for hand-drawn FX design and timing. **No verified URL.**

### Inferences
- For an indie team trying to match Arcane, one Harmony seat (or TVPaint) for the lead FX artist plus free Blender GPv3 for in-scene FX is the likely sweet spot. Everything else (Krita, OpenToonz, Blender compositor) can stay free.
- EmberGen or Houdini only make sense if the style moves toward Jibaro-like simulated water/smoke that is then painted over.

### Gaps
- No vendor page (Toon Boom, TVPaint, Adobe, JangaFX, SideFX, ActionVFX) could be fetched, and the search budget ran out before vendor searches. **All prices and current license terms for paid tools are unverified.** The report writer should state "price not verified" or omit prices.
- The status of Adobe Animate (discontinuation or maintenance) needs confirmation from Adobe's own announcement.
