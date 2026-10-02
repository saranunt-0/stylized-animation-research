# Reference productions: Arcane (Fortiche), Blender Studio "Project Gold", Alberto Mielgo / Pinkman.tv, and related painterly-3D work

**How these notes were gathered (please read first; current as of 2026-10-02).** In this session WebFetch was blocked by the egress proxy for every domain tried (studio.blender.org, code.blender.org, extensions.blender.org, projects.blender.org, 80.lv, beforesandafters.com, animationmagazine.net, cartoonbrew.com, cgchannel.com, vfxvoice.com, creativebloq.com, blendernation.com, en.wikipedia.org). The shared WebSearch budget also ran out partway through. So every finding below comes from **search-engine extracts of the cited pages**, not from reading the full pages, plus GitHub API searches. Every URL was returned by a search tool in this session; no URL was made up. Exact quotes and numbers should be spot-checked against the page before publication. Evidence labels: **[PRIMARY]** = studio, crew or official channel; **[PRESS]** = trade or press reporting; **[AGG]** = low-quality SEO or aggregator site; **[FAN]** = community or fan work. Spider-Verse, Puss in Boots: The Last Wish, The Bad Guys and TMNT: Mutant Mayhem were **not researched** because the budget ran out (see Q4 Gaps).

---

## Q1. Arcane (Fortiche, S1 2021 / S2 2024): software, render engine, and how the painted look was achieved

### Takeaway
Fortiche's own published toolset is Maya, Houdini, Nuke, Mari and Mercenaries Engineering's **Guerilla Render** (Guerilla Station for lookdev, assembly, lighting and rendering), plus in-house tools. The renderer is confirmed only by Fortiche's FAQ list and by Guerilla's own channels. Several SEO sites guess "V-Ray/Arnold", and those guesses are wrong. The painted look comes from 3D characters and sets with **hand-painted textures**, shaders that suppress realistic CG cues, **hand-drawn 2D FX placed on cards in Houdini**, effects animated **on twos**, and art-directed lighting and colour scripts. All character animation on S1 was keyframed. S2 crowds used Golaem with Xsens mocap.

### Cited Findings
**Software and render engine**
- [PRIMARY] Fortiche's official FAQ lists its DCCs as Autodesk Maya, SideFX Houdini, Foundry Nuke, Foundry Mari and "Mercenaries Guerilla", plus in-house tools that extend these DCCs. — [Fortiche FAQ](https://forticheprod.com/faq/)
- [PRIMARY, vendor] On 2019-10-18 (decoded from the post ID), Guerilla Render's official X account posted the Arcane trailer: "Animation handled by the amazing #fortichecrew in Paris … #GuerillaRender inside ;)". — [Guerilla Render on X](https://x.com/guerillarender/status/1185231595197882368?lang=en)
- [PRIMARY, vendor] Guerilla's site lists Arcane and Arcane 2 (Fortiche) as using Guerilla Station/Guerilla Render for lookdev, assembly, lighting and rendering. A search extract also says S2 lookdev managed "multiple AOVs (skin, metal, clothing, hair)" for rendering in Guerilla. The exact page was not read, so treat the AOV detail as unverified. — [guerillarender.com](http://guerillarender.com/)
- [AGG, contradicted] yelzkizi.org states that Arcane's "longer render times suggest they used realistic offline rendering with V-Ray, Arnold or similar" and that Photoshop was used for texture painting and Nuke for compositing. This is speculation, and the V-Ray/Arnold claim is contradicted by Fortiche's FAQ and Guerilla. — [yelzkizi.org](https://yelzkizi.org/what-3d-program-did-arcane-use/); compare [ExpertBeacon](https://expertbeacon.com/what-software-did-arcane-use/) [AGG]
- [PRIMARY, vendor blog with Fortiche crew] **Arcane S2 crowds** (Autodesk M&E blog, 2025-03-26, Crowd Supervisor Michael Etienne):
  - Golaem for Maya was used across 9 episodes, for **313 crowd shots** ranging from 3 to 600+ characters, built from **~500 animation cycles**.
  - A constraint system linked the Golaem rig to Fortiche's main character rigs.
  - Mocap sessions used **Xsens**, with a custom IK-based retargeting of Xsens FBX onto Fortiche rig controllers.
  - Yeti grooms were converted to Golaem fur.
  — [Autodesk blog](https://blogs.autodesk.com/media-and-entertainment/2025/03/26/crafting-crowds-fortiche-golaem-and-the-magic-of-arcane-season-2/)

**Animation approach**
- [PRIMARY, crew interview] Alexis Wanneroy (Head of Character Animation, Fortiche) is interviewed by SyncSketch (Dec 2021). The search extract says Fortiche has "real-time rigs that are very efficient", so animators can play them without constant playblasts, and that there was "no mocap on the show – everything has been keyframed" (S1 principal animation). — [SyncSketch blog](https://blog.syncsketch.com/creator-stories/arcane-fortiche/); [SyncSketch on X, 2021-12-29](https://x.com/SyncSketch/status/1475995112459100160)
- [PRESS, attribution uncertain] The studio "initially employed around 15 people and grew to about 300" during Arcane and produced "five hours of … animation within two years". The search extract did not make clear whether this came from RedShark News or SyncSketch. — [RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline)
- [PRESS, unverified attribution] Effects are animated "on twos" for a graphic feel. Production reportedly used contrasting frame rates: "unstable" elements at 12 fps, intimate character moments smoother at 24. Most effects are said to have been made by "just four or five 2D artists working in digital painting software". The search extract did not say which page made these claims; the candidates are AnimationXpress and Dork. — [AnimationXpress](https://www.animationxpress.com/animation/talent-experimentation-originality-how-fortiche-revolutionised-animated-storytelling-with-arcane/); [Dork](https://readdork.com/film/how-arcane-visual-style-strengthens-character-storytelling-6ffb231c5a)

**Painted look and 2D FX**
- [PRESS, crew-sourced] **VFX Voice on S2:**
  - S2 mixes 2D and 3D in an "unusual workflow".
  - Hand-drawn elements are placed in **Houdini on cards** and combined with art-directed procedural rays.
  - 2D elements are split into tones of colour, including smoke layers, with particles and debris added "to make things look hand-created".
  - Fire and smoke are done in 2D.
  - Colour palettes and lighting schemes come from intuition plus references selected with the directors, deliberately alternating darker moments with high-contrast sequences.
  - Riot's team under Arnaud Baudry collaborated with Fortiche on character powers and VFX.
  — [VFX Voice, "Riot Games and Fortiche get revolutionary with Arcane Season 2"](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/)
- [PRIMARY, official video] Fortiche released a YouTube breakdown on how S2 texturing achieves the "hand-painted look". The channel name was not verified. — [Arcane S2 texturing: Animating the hand-painted look (YouTube)](https://www.youtube.com/watch?v=gCJIJG6Lz84)
- [AGG] Further aggregator claims:
  - Hand-painted textures on 3D models, plus "custom shaders to preserve the hand-painted aesthetic under lighting, reducing realistic CG effects like specular highlights".
  - Smoke, explosions and Jinx's scribbles are hand-drawn 2D layered over 3D.
  - Julien Georgel is named as Art Director.
  These claims are consistent with the primary sources but come from an SEO site, so treat the Georgel credit as unverified. — [yelzkizi.org "Is Arcane 2D or 3D"](https://yelzkizi.org/is-arcane-2d-or-3d/)

**Official talks and docs**
- [PRIMARY] **SIGGRAPH 2023 Production Session "Fortiche: Crafting the Bridge"**:
  - Speakers: Hervé Dupont (Producer, Fortiche), Rémy Terreaux (Animation Supervisor), Philippe Llerena (CTO) and Arnaud Baudry (Production Designer, Riot).
  - Topics: the Arcane production story, pipeline and organisation challenges, designs, adapting game visuals to a series, animation, and Season 2 questions.
  - Production sessions are typically not recorded publicly. The ACM DL entry is an abstract.
  — [SIGGRAPH History](https://history.siggraph.org/learning/fortiche-crafting-the-bridge-by-llerena-dupont-baudry-and-terreaux/); [ACM DL](https://dl.acm.org/doi/10.1145/3577023.3585274); [abstract PDF](https://dl.acm.org/doi/pdf/10.1145/3577023.3585274); [s2023 programme](https://s2023.siggraph.org/presentation/?id=pros_126&sess=sess301)
- [PRIMARY] **"Arcane: Bridging the Rift"** (Riot, 2022):
  - Five episodes of about 30 minutes, free on the League of Legends YouTube channel, weekly on Thursdays from Aug 4 to Sep 1, 2022.
  - Ep. 3, "Killstreaks Meet Keyframes", covers Fortiche's process and how it developed the visual aesthetic.
  - Ep. 5 notes "six years of development" before S1.
  — [ONE Esports episode guide](https://www.oneesports.gg/league-of-legends/arcane-bridging-the-rift/); [Cartoon Brew](https://www.cartoonbrew.com/documentary-2/arcane-docuseries-releases-first-episode-219574.html); [80.lv on Ep. 3](https://80.lv/articles/arcane-documentary-the-third-episode-released); [Games Press release](https://www.gamespress.com/en-US/ARCANE-THE-FIRST-EPISODE-OF-BRIDGING-THE-RIFT-IS-NOW-AVAILABLE)
- [PRESS] Annecy appearances:
  - 2022: "Fortiche: Our Talents Talk About their Career Stories" session, and a making-of look at Arcane. — [Annecy 2022 archive](https://www.annecyfestival.com/about/archives/2022/programme/2022-programme-index:rdv-200001502766); [80.lv](https://80.lv/articles/fortiche-to-share-a-making-of-look-at-arcane-tv-series-during-annecy-festival)
  - 2024: Studio Focus on June 11 with Christian Linke, Amanda Overton and Arnaud Baudry (Riot), and Bart Maunoury (director) and Christine Ponzevera (producer) from Fortiche. — [Animation Magazine, May 2024](https://www.animationmagazine.net/2024/05/fortiche-heads-to-annecy-with-arcane-bts-new-content-plans/)
- [PRESS] IAMAG Master Classes 25 (Paris, 2025-03-07) included "Creating Arcane by Fortiche Production". This was a ticketed event. — [Swapcard listing](https://app.swapcard.com/event/iamag-master-classes-2025/planning/UGxhbm5pbmdfMjUzMTc0MQ==); [3DVF](https://3dvf.com/en/iamag-master-classes-25-arcane-avatar-2-and-more-this-march-in-paris/)

### Inferences
- The practical recipe that can be reconstructed from primary sources has four parts:
  - Painted albedo textures in Mari or Photoshop (Mari is in the FAQ; Photoshop is only reported by aggregators).
  - Lookdev in Guerilla that suppresses physically based specular and noise.
  - FX drawn by hand, put on cards in Houdini, and timed on twos.
  - Heavy compositing in Nuke with per-material AOVs for the final paint-over feel.
- The mocap note in the S2 Golaem article covers **crowds only**. It does not contradict the "no mocap" statement for S1 hero animation. Whether S2 hero animation used any mocap was not established.

### Gaps
- No primary source was found giving the S1 vs S2 render-engine split, frame-rate rules per shot type, team size for S2, or the S2 budget. The 12 fps vs 24 fps claim is unattributed press reporting.
- The YouTube channel and upload date of the "Arcane S2 texturing" video were not verified (YouTube pages could not be fetched).
- A Gamerant article discusses a possible **S2 making-of documentary** ([Gamerant](https://gamerant.com/arcane-season-2-behind-the-scene-documentary-update/)). Whether one was released by Oct 2026 is **unknown**.
- No Fortiche-run **courses** (paid or free) were found. The IAMAG masterclass is the closest paid item.

---

## Q2. Blender Studio "Project Gold": what it is, the look, tools built, logs, released assets, status as of Oct 2026

### Takeaway
"Blender Gold" is **Blender Studio's Project Gold**, the 16th Blender Open Movie. It was announced in May 2023 and directed by Jericca Cleland, with an impressionistic oil-painting look. It was **refocused from a short film into a technical showcase**, premiered at Blender Conference 2024 and was released online on **2024-11-07**. Its key tech is the Geometry-Nodes-based **Brushstroke Tools** extension plus Cycles light linking and the (viewport) compositor. Gold does **not** use the separate EEVEE "NPR prototype/NPR Project" that Blender developers started in July 2024. A follow-up painterly project, **Singularity**, has been reported as nearing completion, and Blender Studio has announced a feature film, **OVERGROWN**.

### Cited Findings
**What it is**
- [PRIMARY] Announcement blog (May 2023):
  - Director: Jericca Cleland.
  - Aim: "push for highly art-directable NPR and stylization tools in Blender, notably via light linking in Cycles, the viewport compositor, and much more".
  - Look: "impressionistic, stylized … visual poetry, a new territory for Blender Studio".
  - Story: "a metaphorical journey into the depths of human experience … fragility of life … resilience and inner transformation".
  — [Blender Studio announcement](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/); [BlenderNation, 2023-05-23](https://www.blendernation.com/2023/05/23/project-gold-new-blender-open-movie-announced/)
- [PRESS] Project Gold is "Blender's 16th Open Movie". Wing It! is the 15th. — [80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files); [Wing It! project page](https://studio.blender.org/projects/wing-it/)
- [PRIMARY/PRESS] Production was "refocused to a showcase for the new tools and technologies developed to achieve the distinctive painterly look". It premiered at Blender Conference 2024 (October) and was released online on Thursday 7 November 2024, together with "a number of production files" and the Brushstroke Tools add-on on the Extensions platform. — [80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files); [Blender Studio "Project Gold Premiere"](https://studio.blender.org/blog/project-gold-premiere/); [premiere-date post](https://studio.blender.org/blog/project-gold-showcase-premiere-date/); [Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools)
- [PRIMARY] Blender Studio's X post (2024-11-07) calls it "a technical showcase focused on stylized rendering, along with an add-on designed to achieve a painterly look". — [Blender Studio on X](https://x.com/BlenderStudio_/status/1854560062036942921)
- [PRESS] Features showcased: light linking, Simulation Nodes, Geometry-Nodes-based tools, "extending the viewport compositor and interactive image processing", and "art-directable, stylized, non-photorealistic rendering with **Cycles**". The film can be watched on Blender's YouTube channel. — [Creative Bloq (Yahoo syndication)](https://www.yahoo.com/tech/heres-watch-blender-studios-beautiful-040000770.html)

**Tools built**
- [PRIMARY] **Brushstroke Tools**:
  - "A Geometry Nodes-based toolset useful for creating a variety of stylized looks in asset production, specifically developed for Project Gold."
  - The add-on provides an interface to create, manage and edit **layers of procedurally generated 3D brushstrokes**.
  - It is free on extensions.blender.org. A search extract says it was published on 2024-11-04 at v1.2.3; it is unclear whether that is the first or the latest version, so check the version history page.
  — [Extensions: Brushstroke Tools](https://extensions.blender.org/add-ons/brushstroke-tools/); [version history](https://extensions.blender.org/add-ons/brushstroke-tools/versions/); [CG Channel, Nov 2024](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/)
- [PRESS] Simon Thommes was technical artist (shading and FX) and led a workshop on using the Brushstroke Tools that includes all characters, environments and other production files. Jericca Cleland is reportedly "still working on the short film, aiming to … bring it to completion". The date of that statement is unknown. — [80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files); [Credits page](https://studio.blender.org/projects/gold/pages/credits/)

**Talks and production logs**
- [PRIMARY] Blender Conference 2024 talk **"Procedural Oil Painting for Film Production"**: how Blender Studio arrived at its approach to stylized rendering for Gold's oil-painting look. Speakers were not verified. — [BCON 2024 presentation page](https://conference.blender.org/2024/presentations/3925/)
- [PRIMARY] Production logs and blog:
  - [Production Logs index](https://studio.blender.org/projects/gold/production-logs/) (at least 11 pages, see [page 11](https://studio.blender.org/projects/gold/production-logs/?page=11))
  - [Production Log #5](https://studio.blender.org/projects/gold/production-log/246/)
  - [Production Log #62](https://studio.blender.org/projects/gold/production-log/285/)
  - [Production Log 01 video on video.blender.org](https://video.blender.org/videos/watch/c948ed21-75b7-4b7c-8d96-3cec7dabb51b)
  - ["Production Recap: Story Development for Gold"](https://studio.blender.org/blog/production-recap-gold-story-development/)

**Separate Blender NPR engine work (not Gold)**
- [PRIMARY] code.blender.org, "NPR Project" (May 2025):
  - The NPR project "officially started in July 2024, with a workshop with **Dillon Goo Studio** and Blender developers".
  - The prototype covered filter support, custom shading and AOV access.
  - Some features become EEVEE nodes; others become per-material/object compositing nodes. EEVEE comes first.
  - Planned in-engine features: Ray Queries, Portal BSDF, Custom Shading and Depth Offset, with development starting after Blender 5.0 (planned for Nov 2025).
  — [NPR Project blog](https://code.blender.org/2025/05/npr-project/); [Projects Update Q2 2025](https://code.blender.org/2025/05/projects-update-q2-2025/)
- [PRIMARY] Developer artifacts:
  - [NPR Design task #120403](https://projects.blender.org/blender/blender/issues/120403)
  - [NPR-Prototype initial implementation PR #127258](https://projects.blender.org/blender/blender/pulls/127258). It adds a geometry-based EEVEE pipeline for the "NPR step", which has its own node tree where BSDF nodes are forbidden and is chosen from the Material Output node.
  - [NPR Prototype To-Dos #127354](https://projects.blender.org/blender/blender/issues/127354)
  - [EEVEE NPR Prototype feedback thread (devtalk)](https://devtalk.blender.org/t/eevee-npr-prototype-feedback/37098)

**Follow-ups and status by Oct 2026**
- [PRESS] **Singularity**:
  - A "painterly space adventure set in a universe before the beginning of our time".
  - Described as a **follow-up to Project Gold** that tests painterly and NPR tools, with brush-stroke style packs, textures and shading setups.
  - Reported "at the finishing line for shading and lighting". The article date and the release status were not verified.
  — [80.lv "New Blender Studio's Open Movie Enters Final Production Stage"](https://80.lv/articles/new-blender-studio-s-open-movie-nears-completion)
- [PRIMARY] **OVERGROWN** is Blender Studio's announced feature film. It is co-directed by Hjalti Hjálmarsson and Rik Schutte and set in a post-human world reclaimed by nature. — [Blender Studio announcement](https://studio.blender.org/blog/overgrown-announcement/); [80.lv](https://80.lv/articles/blender-studio-announces-ambitious-feature-film-project); [Creative Bloq](https://www.creativebloq.com/art/animation/blender-wants-to-make-its-first-feature-length-movie-and-share-the-process-for-free)
- [PRIMARY] Blender marked 20 years of Open Movies with a frame-by-frame installation at Blender Conference 2026. — [blender.org press](https://www.blender.org/press/20-years-open-movies/)
- [PRIMARY] **Wing It!** (15th open movie) is a stylized cat-and-dog cartoon whose stated goals include pushing 2D/3D animation and "NPR and stylized rendering workflows". — [Wing It! project page](https://studio.blender.org/projects/wing-it/)
- [FAN/PRESS, secondary write-ups] [intoanimation.com](https://www.intoanimation.com/articles/project-gold); [CRUDO](https://crudo.dev/posts/blender-studio-project-gold/); [Patreon post "Project Gold for Blender is Here! (Along with a free addon)"](https://www.patreon.com/posts/project-gold-for-115660793)

### Inferences
- Gold is the right match for "Blender Gold". It is the only Blender Studio project with that name, and it targets an oil-painting or impressionist look.
- Gold's look appears to come from **geometry, not a shader**: Geometry Nodes generate instanced 3D brushstroke cards or curves over surfaces, rendered in Cycles. Light linking provides per-object art-directed lighting, and compositor passes do the image processing. This makes it a geometric stroke-instancing approach rather than a screen-space paint filter. This is an inference; the BCON talk should be checked to confirm the mechanism.
- The EEVEE NPR Project was triggered by a Goo Engine/Dillon Goo collaboration, not by Gold. Readers should not credit Gold with "the new NPR engine".

### Gaps
- **License of Gold's film and assets was not verified.** Blender open movies are typically CC-BY, but this was not confirmed for Gold.
- It is unclear whether the production files and workshop are free or need a Blender Studio subscription (the Creative Bloq headline implies they are downloadable). Pages could not be fetched.
- Singularity's release date and status as of Oct 2026 are unverified. So is whether Cleland's full Gold short has resumed or been released.
- Which NPR Project features shipped in Blender 5.x by Oct 2026 is unknown; my 2026 search failed because the budget ran out.
- Sprite Fright (2021) and Charge (2022) were not researched. No sources were gathered on their look or tools.

---

## Q3. Alberto Mielgo / Pinkman.tv: The Witness (2019), Jibaro (2022), The Windshield Wiper (2021)

### Takeaway
Across all three films, Mielgo's method is **painted 2D environments, often arranged in 3D space for camera moves, with keyframed (never mocap or roto) 3D characters lit to match the paintings**, followed by heavy 2D post and "camera" grading. Stated tools by film:
- The Witness: Blender/Cycles for the "3D paintings" (Vaughan Ling), Maya and Arnold for characters, Marvelous Designer for cloth.
- The Windshield Wiper: Photoshop backgrounds, Maya animation and After Effects compositing.
- Jibaro: hand-keyed animation by Agora Studio from multi-camera dancer reference. The software is not named in the sources found.

### Cited Findings
**The Witness (LDR Vol. 1, 2019)**
- [PRIMARY, director via press] befores & afters, 2019-05-06:
  - Keyframed, not live action or mocap.
  - 2D painterly backgrounds, and **Marvelous Designer** for cloth sims.
  - The paintings "look rich but are extremely simplified when seen up close".
  - Surfacing artist **Zeno Pelgrims** created graphic-but-realistic, impressionistic clothing shading.
  - Mielgo worked with paintings rather than 3D sets and had to match realistic light so characters sit inside the painted environments.
  - After rendering, Mielgo "manually played with levels and colors to make the camera feel alive", reacting like a real camera with overexposure.
  — [befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/); [b&a tag page](https://beforesandafters.com/tag/the-witness/)
- [PRIMARY, crew interview] BlenderNation, 2019-11-18, with **Vaughan Ling**:
  - Ling made "3D paintings" in **Blender** for shots with a lot of camera movement.
  - About **80% of what is on screen is straight painting arranged in 3D space**; the other 20% is reflections, shadows, CG elements and **FX cards**.
  - These were modelled and rendered in **Blender/Cycles**, while **characters were done in Maya and rendered with Arnold**, which needed creative solutions to combine.
  - Ling moved from MODO to Blender while doing vis-dev on Into the Spider-Verse.
  - Note: one search summary wrongly attributed the Blender 3D paintings to Mielgo himself. Per BlenderNation it was Ling.
  — [BlenderNation interview](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/); [CG Talks podcast with Ling](https://www.blendernation.com/2021/04/10/cg-talks-podcast-s03e04-spiders-heavier-than-paint-interview-with-vaughan-ling-heavypoly/)

**Jibaro (LDR Vol. 3, May 2022)**
- [PRIMARY, director via press] Mielgo began with "the visual of a siren singing" and built the story around it. The film uses a hybrid of 2D painted backgrounds and 3D characters. Some shots involved building and lighting a whole forest in 3D, with "a lot of 2D work in post-production". Characters are simplified but read as real "because the physics of light are correct in terms of painting and rendering". — Search extract across [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/), [SlashFilm](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/) and [80.lv](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro); the per-outlet attribution is unverified.
- [PRESS] Reference shoot and crew:
  - Choreographer **Sara Silkins** and her dancers were photographed with multiple cameras for about a week after rehearsals; the edited footage went to Pinkman.tv's animation team as reference.
  - Mielgo took a **three-week road trip** (Northern California, Washington, Oregon) for forest video reference, and shot underwater video reference for textures and lighting.
  - **Crew of 72 including 20 animators**, with about 2 years of preparation.
  — [Fox Renderfarm (secondary)](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/); [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/)
- [PRIMARY, vendor/crew] **Agora Studio provided all rigging and animation.** All character animation was hand-keyed. Agora's animation supervisor **Mathieu Di Muro** said they tried an **Xsens** mocap suit, but it was "too clean and too perfect"; keyframing from video reference gave the right exaggeration and imperfection. — [Agora Studio on LinkedIn](https://www.linkedin.com/posts/agora-vfx_this-is-surprising-for-many-jibaros-character-activity-6933808243391561728-ot8f); [Agora portfolio: Jibaro](https://agora.studio/portfolio/706/jibaro); fan echo [X post, 2022-05-24](https://twitter.com/guzzu_0/status/1529051335244812289) [FAN]
- [PRIMARY, director via press] On 80.lv, Mielgo gave an in-depth breakdown of the 3D workflow: animation setup, how the knight and siren were modelled, textured and rigged, and the environment inspirations. Software was not captured in the extract. — [80.lv development process](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro); [80.lv "Mielgo talks specifics of creating LDR short episodes"](https://80.lv/articles/alberto-mielgo-talks-specifics-of-creating-love-death-robots-short-episodes)
- [PRESS] Most armour sounds were recorded in the forest or at Mielgo's house using kitchen utensils. — [80.lv](https://80.lv/articles/sounds-of-armor-for-jibaro-were-recorded-using-kitchen-utensils)
- Other Jibaro interviews:
  - [PRESS] [GameRant](https://gamerant.com/interview-alberto-mielgo-love-death-and-robots-volume-3-jibaro-netflix/), [ScreenRant interview](https://screenrant.com/love-death-robots-vol-3-alberto-mielgo/), [ScreenRant "Was Jibaro animated or live action?"](https://screenrant.com/was-jibaro-animated-live-action-love-death-robots/), [ComicBook.com](https://comicbook.com/anime/news/love-death-robots-season-3-netflix-alberto-mielgo-jibaro-interview/)
  - [befores & afters, "how exactly does someone pitch an episode of LDR", 2022-05-23](https://beforesandafters.com/2022/05/23/so-how-exactly-does-someone-pitch-an-episode-of-love-death-robots/)

**The Windshield Wiper (2021; won Best Animated Short at the 94th Academy Awards)**
- [PRIMARY, director via press] Production:
  - Self-produced independently over about **six years**; the team paused for paying jobs.
  - **Mielgo painted all backgrounds in Photoshop** and did the character designs.
  - The animation team, led by **Leo Sánchez Barbosa (Leo Sánchez Studio)**, keyframed **3D characters** into the scenes.
  - **Maya** was used for 3D animation and **After Effects** for final compositing.
  - Crew gave up normal salaries and worked evenings and weekends ("Indie filmmaking in animation is truly utopian").
  - Getting CG tools to produce the "very original, flat stylized look" was one of the hardest parts.
  — Search extract across [Animation Magazine, Dec 2021](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/) and [befores & afters Q&A, 2021-12-15](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/); the per-outlet attribution is unverified.
- [PRIMARY, headline quote] The befores & afters Q&A headline, a Mielgo quote, reflects a deliberately limited-animation approach: "Sometimes the characters, they are still and they basically breathe a little bit, and that's good enough". — [befores & afters](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/)
- [PRESS] Further interviews and pages: [Variety (Cannes)](https://variety.com/2021/artisans/markets-festivals/alberto-mielgo-windshield-wiper-1235017864/); [Hollywood Reporter](https://www.hollywoodreporter.com/movies/movie-features/oscars-the-windshield-wiper-alberto-mielgo-1235106097/); [Short of the Week](https://www.shortoftheweek.com/2022/01/19/the-windshield-wiper/); official page [albertomielgo.com](https://www.albertomielgo.com/the-windshield-wiper-1); trailers [Vimeo 2021](https://vimeo.com/568179562), [Vimeo 2019](https://vimeo.com/347225885)

**Studio and background**
- [PRESS] Pinkman.tv is Mielgo's studio. The search extract says it is based in **Madrid** (unverified). Motionographer (2010) described its philosophy as "a laboratory to explore 2D animation through fine art and traditional methods … less emphasis on computers". — [Motionographer 2010](https://motionographer.com/2010/02/24/modern-rebel-alberto-mielgo-pinkman-tv/); [Pinkman.tv LinkedIn](https://www.linkedin.com/company/pinkman-tv); [Instagram](https://www.instagram.com/pinkman.tv.animation.studio/); [2010 reel on Vimeo](https://vimeo.com/8918898)
- [PRIMARY + secondary] In 2015 Mielgo was Production Designer/Art Director on Sony's *Into the Spider-Verse* and made an early animation test. He was let go before main production and is credited as "Visual Consultant". The claim that his four test shots "determined the visual language" is secondary or fan commentary and **unverified**. — [Mielgo's own Spider-Verse page](https://www.albertomielgo.com/spiderverse); [Wikipedia](https://en.wikipedia.org/wiki/Alberto_Mielgo); [Medium essay [FAN]](https://medium.com/@lou_lotus/the-art-of-alberto-mielgo-fba33b8cb10e)

### Inferences
- The Witness pipeline is a classic **camera-projection / 2.5D matte-painting** workflow: painted plates on simple geometry in Blender, with CG characters lit to match. Jibaro scaled this up with fully lit 3D forest shots, and The Windshield Wiper went flatter, with painted backplates and minimal animation.
- Jibaro's animation software is probably Maya, since Agora's public tools and rigs are Maya-based ([Agora Maya tools](https://agora.community/content/agora-studio-maya-tools)). This is **unverified** for Jibaro specifically.

### Gaps
- No source found names the Jibaro renderer, the compositing package, or frame-rate and stepping choices for any Mielgo film.
- No Mielgo-taught course or paid talk was found. No official Pinkman.tv website could be confirmed; only social pages turned up.

---

## Q4. Closely related painterly-3D productions (brief)

### Takeaway
The budget ran out before Spider-Verse, Puss in Boots: The Last Wish, The Bad Guys and TMNT: Mutant Mayhem could be researched. Only incidental connections were captured: Mielgo's and Vaughan Ling's Spider-Verse vis-dev roles, and VFX Voice features on hand-drawn and stylized effects and on *Entergalactic*.

### Cited Findings
- [PRESS] VFX Voice feature "The Return of Hand-Drawn and Stylized Effects Animation". It surfaced in an Arcane search; its content beyond the title was not read. — [VFX Voice](https://vfxvoice.com/the-return-of-hand-drawn-and-stylized-effects-animation/)
- [PRESS] VFX Voice "Animating to the Rhythm of Entergalactic" (Netflix, painterly-3D series). Content not read. — [VFX Voice](https://vfxvoice.com/animating-to-the-rhythm-of-entergalactic/)
- [PRIMARY] Vaughan Ling (The Witness 3D paintings) was a vis-dev artist on Into the Spider-Verse, and Mielgo was its early production designer. This is a direct personnel link between the Mielgo look and the Spider-Verse look. — [BlenderNation](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/); [albertomielgo.com/spiderverse](https://www.albertomielgo.com/spiderverse)
- [FAN] Other Love, Death & Robots painterly work: 80.lv "Creating Fantastic Visuals in Love, Death & Robots" (episode not verified). — [80.lv](https://80.lv/articles/creating-fantastic-visuals-for-love-death-robots)

### Inferences
- None beyond the personnel link above.

### Gaps
- No sources were gathered on Spider-Verse SIGGRAPH talks, Puss in Boots (DreamWorks) painterly pipeline talks, The Bad Guys, or TMNT: Mutant Mayhem (Mikros/Cinesite). The report writer should rely on other researchers' notes or flag these as not covered.

---

## Q5. Free public recreations and tutorials that target the Arcane, Mielgo or Gold looks

### Takeaway
Free recreation material is mostly **80.lv / BlenderNation shot-recreation write-ups** for Jibaro, a few YouTube hand-painted-texture videos for Arcane, and very thin GitHub coverage. GitHub has no mature "Arcane shader" or "Gold brushstroke" repos; the closest is a 2026 Unity "Arcane-like" shader with 1 star. For the Gold look, the free **Brushstroke Tools** extension from Blender Studio is itself the canonical "recreation kit".

### Cited Findings
| Item | Target look | Type / tool | One-line evaluation | Link |
|---|---|---|---|---|
| Brushstroke Tools (Blender Studio) | Gold | Free Blender extension, Geometry Nodes | The official tool used on Gold; the best starting point for oil-paint stroke instancing. [PRIMARY] | [extensions.blender.org](https://extensions.blender.org/add-ons/brushstroke-tools/) |
| "Procedural Oil Painting for Film Production" (BCON 2024) | Gold | Conference talk (free) | The official explanation of Gold's method; watch before using the add-on. [PRIMARY] | [conference.blender.org](https://conference.blender.org/2024/presentations/3925/) |
| Arcane S2 texturing: Animating the hand-painted look | Arcane | YouTube (reported as Fortiche-official) | The only official Arcane texturing breakdown found; channel not verified. | [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84) |
| HANDPAINTED EKKO TEXTURE (ARCANE) | Arcane | YouTube fan tutorial | Fan hand-painted texture demo; quality and tools not verified. [FAN] | [YouTube](https://www.youtube.com/watch?v=Zzk3fsBFz8I) |
| The SECRET Behind Arcane Season 2 Mind-Blowing Visuals | Arcane | YouTube analysis | Unofficial explainer; treat its claims as commentary. [FAN] | [YouTube](https://www.youtube.com/watch?v=e8NaGcNDbb0) |
| agrimart "arcane" (Gumroad) | Arcane | Gumroad product | Surfaced in an Arcane-texturing search; content and price not verified. [FAN] | [Gumroad](https://agrimart.gumroad.com/l/arcane) |
| Jon Gilleland – Ekko's Stopwatch | Arcane | itch.io asset pack | Downloadable Arcane prop asset; pricing not verified. [FAN] | [itch.io](https://jongilleland.itch.io/jon-gilleland-ekkos-stopwatch) |
| Arcane-like Stylized Character Shader | Arcane | GitHub, Unity ShaderLab | Created May 2026, 1 star; an early hobby shader, low maturity. [FAN] | [GitHub](https://github.com/Databazator/Arcane-like-Stylized-Character-Shader) |
| Jibaro shot remade in Blender + Substance | Mielgo/Jibaro | BlenderNation / 80.lv article | A free, Blender-based write-up of a full shot recreation; the most directly useful Mielgo-look reference found. [FAN] | [BlenderNation](https://www.blendernation.com/2022/07/30/jibaro-from-love-death-robots-shot-remade-using-blender-and-substance/); [80.lv](https://80.lv/articles/a-scene-from-ldr-s-jibaro-episode-recreated-with-blender-substance) |
| Recreating a Jibaro scene in Houdini & Arnold (Aquib Hussain) | Jibaro | 80.lv breakdown | Covers the water setup, dancing animation and Arnold rendering; FX-focused rather than paint-focused. [FAN] | [80.lv](https://80.lv/articles/recreating-a-scene-from-ldr-s-jibaro-in-houdini-and-arnold) |
| Golden Woman scene recreated in Blender & UE5 | Jibaro | 80.lv breakdown | A real-time (UE5) take on the Jibaro siren look. [FAN] | [80.lv](https://80.lv/articles/golden-woman-scene-from-jibaro-recreated-in-blender-ue5) |
| Ashli: Making a Mielgo-style character in 3ds Max & V-Ray | Mielgo | 80.lv breakdown | A character-only Mielgo-style study in non-Blender tools. [FAN] | [80.lv](https://80.lv/articles/ashli-making-a-mielgo-style-character-in-3ds-max-v-ray) |
| Spiderverse-Shader-Unity | Spider-Verse | GitHub, Unity C# image effect | 43 stars, from 2019; a simple post-process halftone/offset effect. [FAN] | [GitHub](https://github.com/adamb70/Spiderverse-Shader-Unity) |
| inkwell | Spider-Verse / hand-painted comic | GitHub, three.js + R3F | Created June 2026, 0 stars; web NPR toolkit, experimental. [FAN] | [GitHub](https://github.com/VelkinaStudio/inkwell) |
| cymatics | Generic painterly concept-art | GitHub Blender extension (EEVEE NPR shader + 14-stage comp chain) | Created Aug 2026, 2 stars; not a reference-show recreation, but a painterly comp-chain example. [FAN] | [GitHub](https://github.com/infinition/cymatics) |
| Malt (BNPR) | Generic NPR | GitHub, Blender NPR render framework | 1.1k stars, maintained; a general NPR framework, not a recreation of any show. [FAN/community] | [GitHub](https://github.com/bnpr/Malt) |

### Inferences
- No public, maintained "Arcane look" toolkit exists on GitHub as of Oct 2026, based on GitHub API searches for "arcane shader", "arcane style npr" and "painterly npr blender". Practical Arcane-look recreation relies on hand-painted textures, toon or limited shading, and comp, using generic NPR tools.

### Gaps
- YouTube, Gumroad and Blender Market listings could not be searched further after the budget ran out. Well-known free Arcane-style Blender tutorials on YouTube therefore **could not be catalogued or verified** here.

---

## Q6. Catalog of breakdown material: FREE vs PAID

### Takeaway
The free primary material is strongest for Arcane (Bridging the Rift, the S2 texturing video, the Autodesk crowd article, crew interviews and podcasts) and Gold (BCON talk, Brushstroke Tools, production logs, NPR dev blog). For Mielgo, the best free material is press interviews (befores & afters, BlenderNation, 80.lv). Paid material found is limited to *The Art of Arcane* and a ticketed IAMAG masterclass.

### Cited Findings
**FREE**
| Item | Production | Type | Date | One-line summary | Link |
|---|---|---|---|---|---|
| Arcane: Bridging the Rift (5 eps) | Arcane S1 | Official docuseries, YouTube | Aug–Sep 2022 | Riot/Fortiche making-of; Ep. 3 "Killstreaks Meet Keyframes" covers the visual style. | [ONE Esports guide](https://www.oneesports.gg/league-of-legends/arcane-bridging-the-rift/) |
| Arcane S2 texturing: Animating the hand-painted look | Arcane S2 | YouTube (reported Fortiche) | ~2024–25 (unverified) | Official texturing breakdown. | [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84) |
| Crafting Crowds: Fortiche, Golaem… | Arcane S2 | Vendor blog with crew | 2025-03-26 | Crowd pipeline numbers, Golaem + Xsens + Yeti. | [Autodesk blog](https://blogs.autodesk.com/media-and-entertainment/2025/03/26/crafting-crowds-fortiche-golaem-and-the-magic-of-arcane-season-2/) |
| Fortiche: Crafting the Bridge | Arcane | SIGGRAPH 2023 production session (abstract free; session not public) | 2023 | Pipeline and organisation, game-to-series design. | [ACM DL](https://dl.acm.org/doi/10.1145/3577023.3585274) |
| Making of Arcane — Alexis Wanneroy | Arcane S1 | SyncSketch interview | Dec 2021 | Keyframe-only, real-time rigs. | [SyncSketch](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) |
| iAnimate podcast #90 — Wanneroy | Arcane | Podcast / YouTube | ~2022 | Animation-lead perspective. | [iAnimate](https://ianimate.net/animationpodcast/arcane-magic-secrets-fortiche-lead-alexis-wanneroy-podcast); [YouTube](https://www.youtube.com/watch?v=4nTtManGqbw) |
| 80.lv podcast with Fortiche lead animator | Arcane | Podcast write-up | n/d | Animation secrets. | [80.lv](https://80.lv/articles/a-podcast-with-fortiche-s-lead-animator-on-arcane-s-secret-to-success) |
| VFX Voice — Arcane S2 | Arcane S2 | Trade article | ~2024–25 | 2D FX on Houdini cards, colour scripting. | [VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/) |
| RedShark News — Fortiche pipeline | Arcane | Trade article | ~2021–22 | Pipeline ramp-up overview. | [RedShark](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline) |
| 3DVF Fortiche interview | Fortiche | Trade interview | n/d | Studio ambitions, feature film, AI stance (content not read). | [3DVF](https://3dvf.com/en/fortiche-arcane-interview-upcoming-animated-feature-ambitions-ai-and-more/) |
| Florian Pasquier — "Arcane Act II" | Arcane S2 | ArtStation | n/d | Crew-artist portfolio post (content not read). | [ArtStation](https://florianpasquier.artstation.com/projects/qQ9Xby) |
| Project Gold film | Gold | Open movie (Blender YouTube) | 2024-11-07 | The showcase itself. | [Blender Studio premiere post](https://studio.blender.org/blog/project-gold-premiere/) |
| Procedural Oil Painting for Film Production | Gold | BCON 2024 talk | Oct 2024 | How the oil-paint look was built. | [conference.blender.org](https://conference.blender.org/2024/presentations/3925/) |
| Brushstroke Tools | Gold | Free extension | Nov 2024 onward | Geometry Nodes brushstroke layers. | [extensions.blender.org](https://extensions.blender.org/add-ons/brushstroke-tools/) |
| Gold production logs and blog | Gold | Studio logs (some may be subscriber-only, unverified) | 2023–24 | Weekly logs and story recap. | [Logs index](https://studio.blender.org/projects/gold/production-logs/); [Log 01 video](https://video.blender.org/videos/watch/c948ed21-75b7-4b7c-8d96-3cec7dabb51b) |
| NPR Project blog and design tasks | Blender NPR | Dev blog / tracker | 2024–25 | EEVEE NPR roadmap (separate from Gold). | [code.blender.org](https://code.blender.org/2025/05/npr-project/); [#120403](https://projects.blender.org/blender/blender/issues/120403) |
| The Witness — Mielgo interview | The Witness | befores & afters | 2019-05-06 | Painted sets, Marvelous cloth, camera grading. | [b&a](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/) |
| The Witness — Vaughan Ling interview | The Witness | BlenderNation | 2019-11-18 | Blender/Cycles 3D paintings + Maya/Arnold characters. | [BlenderNation](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/) |
| Jibaro development process | Jibaro | 80.lv | 2022 | Modelling, texturing, rigging, environment refs. | [80.lv](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro) |
| Agora Studio on Jibaro | Jibaro | Vendor LinkedIn + portfolio | May 2022 | All hand-keyed; mocap rejected. | [LinkedIn](https://www.linkedin.com/posts/agora-vfx_this-is-surprising-for-many-jibaros-character-activity-6933808243391561728-ot8f); [portfolio](https://agora.studio/portfolio/706/jibaro) |
| IndieWire / SlashFilm on Jibaro | Jibaro | Press interviews | May 2022 | Siren-first concept, hybrid 2D/3D, dancers. | [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/); [SlashFilm](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/) |
| Windshield Wiper Q&A | Windshield Wiper | befores & afters | 2021-12-15 | Limited animation and process. | [b&a](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/) |
| Windshield Wiper — Animation Magazine | Windshield Wiper | Trade article | Dec 2021 | Photoshop backgrounds, Maya, AE, six-year indie production. | [Animation Magazine](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/) |

**PAID**
| Item | Production | One-line summary | Approx. price | Link |
|---|---|---|---|---|
| *The Art of Arcane* (Elisabeth Vincentelli, Titan Books) | Arcane | 224-page hardcover art book (2024; listed elsewhere as *The Art and Making of Arcane*). | ~£45 / ~US$66 / ~€39 | [AbeBooks](https://www.abebooks.com/Art-Arcane-Hardcover-Elisabeth-Vincentelli-Titan/32138595134/bd); [Collins Books](https://www.collinsbooks.com.au/p/the-art-of-arcane) |
| *The Art of Arcane* — Limited Portfolio Edition | Arcane | Limited deluxe edition of the same book. | ~£150 | [Forbidden Planet](https://forbiddenplanet.com/431354-the-art-of-arcane-portfolio-edition-hardcover/); [GeekNative](https://www.geeknative.com/167615/titan-confirm-limited-portfolio-edition-of-the-art-of-the-arcane/) |
| IAMAG Master Classes 25 — "Creating Arcane by Fortiche Production" | Arcane | Ticketed in-person masterclass, Paris, 2025-03-07. | not verified | [Swapcard](https://app.swapcard.com/event/iamag-master-classes-2025/planning/UGxhbm5pbmdfMjUzMTc0MQ==) |
| Blender Studio subscription (Gold workshop and production files) | Gold | Simon Thommes' Brushstroke Tools workshop with Gold production files; it is unverified whether this needs a subscription. | not verified | [80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files) |

### Inferences
- The highest-value free sources for a technical reader are the Fortiche S2 texturing video, the VFX Voice S2 article, the BCON 2024 Gold talk with Brushstroke Tools, and the BlenderNation Ling interview for The Witness.

### Gaps
- The publication date of *The Art of Arcane* is listed as "09/12/2024", which is ambiguous (DD/MM vs MM/DD).
- No paid courses by Fortiche or Mielgo crew were found. A broader course search could not be run once the budget ran out.

---

## Q7. Common principles unifying these looks

### Takeaway
All three reference productions **author the image as a painting first and use 3D as the scaffold**. The shared moves are:
- painted textures or painted plates instead of physically based surfaces;
- **hand-drawn or card-based 2D FX** over 3D;
- **keyframed, often stepped or limited, animation** rather than mocap;
- **lighting and colour treated as art direction**: per-object light linking, colour scripts, painted light;
- a heavy final **2D/comp pass** that adds "camera" imperfections.

### Cited Findings
- Painted surfaces and plates:
  - Arcane uses hand-painted textures with Mari in the toolset. — [Fortiche FAQ](https://forticheprod.com/faq/); [YouTube S2 texturing](https://www.youtube.com/watch?v=gCJIJG6Lz84)
  - About 80% of The Witness on screen is painting arranged in 3D. — [BlenderNation](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/)
  - The Windshield Wiper backgrounds were painted in Photoshop. — [Animation Magazine](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/)
  - Gold uses 3D brushstrokes generated by Geometry Nodes. — [Extensions](https://extensions.blender.org/add-ons/brushstroke-tools/)
- 2D FX on cards: Arcane S2 places hand-drawn elements on Houdini cards ([VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/)), and The Witness uses FX cards ([BlenderNation](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/)).
- Keyframe over mocap:
  - Arcane S1. — [SyncSketch](https://blog.syncsketch.com/creator-stories/arcane-fortiche/)
  - The Witness. — [befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/)
  - Jibaro, where Xsens was tried and rejected. — [Agora](https://www.linkedin.com/posts/agora-vfx_this-is-surprising-for-many-jibaros-character-activity-6933808243391561728-ot8f)
  - The exception is Arcane S2 crowds, which used Xsens. — [Autodesk](https://blogs.autodesk.com/media-and-entertainment/2025/03/26/crafting-crowds-fortiche-golaem-and-the-magic-of-arcane-season-2/)
- Stepped or limited timing:
  - Arcane FX on twos, with a 12 vs 24 fps contrast (press, unverified). — [AnimationXpress](https://www.animationxpress.com/animation/talent-experimentation-originality-how-fortiche-revolutionised-animated-storytelling-with-arcane/)
  - Mielgo: characters "basically breathe a little bit, and that's good enough". — [befores & afters](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/)
- Lighting as art direction:
  - Arcane colour scripts alternate dark and high-contrast sequences. — [VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/)
  - Gold's stated focus is Cycles light linking. — [Blender Studio](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/)
  - The Witness matches CG light to painted light. — [befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/)
- Post and comp as a "camera":
  - Mielgo hand-grades levels and colours to simulate camera exposure. — [befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/)
  - Jibaro has "a lot of 2D work in post". — [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/)
  - The Windshield Wiper was composited in After Effects. — [Animation Magazine](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/)
  - Gold uses the viewport compositor and image processing. — [Creative Bloq](https://www.yahoo.com/tech/heres-watch-blender-studios-beautiful-040000770.html)
- Reference-driven realism under stylization:
  - Jibaro used multi-camera dancer reference and forest and underwater reference trips. — [Fox Renderfarm](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/)
  - Mielgo: characters read as real because "the physics of light are correct". — [IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/)

### Inferences
- **Camera-aware shading** in these shows mostly takes the form of **camera projection** of paintings (The Witness, Jibaro) and screen-aligned 2D FX cards (Arcane), rather than custom view-dependent shaders. Gold's brushstrokes are world-space geometry, which is the opposite approach and is more stable under camera motion.
- A small-team recipe can be derived from these productions: paint key frames or plates first, project them onto simple geometry, keyframe characters on 2s with held poses, light per object to the paintings, hand-draw or card-instance FX, and finish with an aggressive grade.

### Gaps
- No primary source gives explicit frame-rate or stepping rules for Gold or Jibaro.
- The "camera-aware shading" principle is my inference; no crew quote states it directly.
