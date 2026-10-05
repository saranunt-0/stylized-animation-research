# Paint first: a free toolkit for painterly 3D animation

An indie creator can reproduce the core methods behind Arcane, Blender Studio's Project Gold and Alberto Mielgo's films almost entirely with free software, because none of these looks depends on a special renderer: all three **paint the image first and use 3D as scaffolding**. Arcane layers hand-painted textures, projected matte paintings, hand-drawn 2D FX and per-shot compositing over keyframed 3D; Mielgo sets keyframed 3D characters into painted backgrounds and grades every shot like an overexposed camera; Gold grows procedural 3D brushstrokes over simple forms with Blender Studio's free **Brushstroke Tools** and renders them in Cycles. The free stack that maps onto those methods centres on **Blender 5.2 LTS**, with Krita and Ucupaint for painting, CloudRig, the Stepped F-Curve modifier and SMEAR for animation, Grease Pencil v3 for 2D FX, the compositor's Kuwahara, Glare and Convert to Display nodes for finishing, Kitsu and Flamenco for pipeline, and Audacity plus Ardour for sound. Blender 5.3 (in alpha on 2 October 2026) adds the first official piece of Blender's NPR effort, per-light **Material Lighting nodes**, while the standalone EEVEE NPR prototype has been discontinued, so screen-space filter tricks still belong in compositing or in community forks. Paid tools such as Nuke, Toon Boom Harmony, Substance 3D Painter and Auto-Rig Pro buy speed and studio interchange, not the look. The real risk for a small team is maintenance rather than price: many popular add-ons are abandoned, pinned to older Blender versions or licensed for non-commercial use only, and section 10 lists them. Evidence quality is uneven, because open-source tool facts were read directly from GitHub while most production-process claims come from search-engine summaries, so every entry below carries an evidence tag.

## How to read this reference: blocked sites and tagged evidence

This reference was compiled on **2 October 2026** under two hard constraints that shape everything in it. First, the research environment's network proxy **blocked page fetches from almost every non-GitHub domain**, including studio.blender.org, docs.blender.org, extensions.blender.org, projects.blender.org, 80.lv, befores & afters, YouTube, Wikipedia and most vendor sites, so only GitHub pages, GitHub API metadata and Blender's source code on its GitHub mirror could be read in full. Second, the **shared web-search budget was capped and ran out partway through every topic**, which left some planned checks undone. As a result, license, release and maintenance data for open-source repositories are the most reliable entries here; claims about how Arcane, Gold and Mielgo's films were made rest mostly on search-engine summaries of interviews; and almost **no prices were verified on vendor pages**. Several areas were not researched at all: Spider-Verse rendering talks, *Puss in Boots: The Last Wish*, *The Bad Guys* and *TMNT: Mutant Mayhem*; YouTube tutorial channels beyond a handful; paid courses outside Blender Studio; and the Blender 5.x compatibility of many add-ons distributed on the Extensions platform.

| Tag | Meaning | How much to trust it |
|---|---|---|
| **R** | Read directly this session: a GitHub repo, README, release or tag page, GitHub API metadata (stars, licence, last push), or Blender source code on the [github.com/blender/blender](https://github.com/blender/blender) mirror | High for what the page says. Repo activity dates are as of 1–2 Oct 2026 |
| **S** | From a search-engine summary of the linked page. The URL is real (returned by search), but the page was not opened | Medium. Wording, numbers and which outlet said what need a spot check |
| **L** | Link found inside a document that was read (a curated list such as [awesome-blender](https://github.com/agmmnn/awesome-blender), a README, or a third-party research file). Neither the target page nor the claim was opened | Low to medium. A pointer, not a confirmation |
| **U** | Unverified: prior knowledge, aggregator or SEO speculation, or a claim that could not be tied to a single source | Low. Check before relying on it |

Production claims in section 1 also carry a **source tier**: *Primary* (the studio, its crew, or the vendor whose tool was used), *Press* (trade or press reporting), *Aggregator* (low-quality SEO sites, which contradict primary sources at least once, for example by guessing V-Ray or Arnold for Arcane) and *Fan* (community work). Version context: Blender **5.2 LTS** (released 14 July 2026 per press summaries, supported to July 2028) is the current long-term release, and Blender's main branch reports **5.3 alpha** ([BKE_blender_version.h](https://raw.githubusercontent.com/blender/blender/main/source/blender/blenkernel/BKE_blender_version.h), R). Paid items get one line and a link; prices quoted come from search snippets and must be checked on the vendor's page.

**Contents:** [1. Reference productions](#1-reference-productions-paint-the-image-first-and-use-3d-as-scaffolding) · [2. Pre-production and pipeline](#2-pre-production-and-pipeline-copy-blender-studios-conventions-before-its-servers) · [3. Modeling and sculpting](#3-modeling-and-sculpting-simple-forms-controlled-normals-detail-in-paint) · [4. Texturing](#4-texturing-pairs-uv-painted-albedo-with-camera-projected-paint-overs) · [5. NPR shading, lighting and rendering](#5-npr-shading-lighting-and-rendering-blender-53-lighting-nodes-replace-a-dead-prototype) · [6. Animation and rigging](#6-animation-and-rigging-keyframe-from-reference-step-per-shot-rig-with-cloudrig) · [7. VFX](#7-vfx-draw-on-twos-over-locked-3d-or-simulate-and-repaint) · [8. Compositing and color](#8-compositing-and-color-finish-the-painting-rather-than-create-it) · [9. Sound design and music](#9-sound-design-and-music-start-from-cheap-organic-recordings) · [10. Tools to avoid](#10-abandoned-outdated-and-license-restricted-tools-to-avoid) · [11. Recommended free starter stack](#11-recommended-free-starter-stack-blender-52-lts-plus-a-dozen-free-tools) · [12. Where to start](#12-where-to-start-six-tests-before-building-the-film) · [Conclusion](#conclusion)

## 1. Reference productions paint the image first and use 3D as scaffolding

### Arcane layers painted textures, projections and drawn FX over keyframed 3D

Fortiche's own FAQ lists its toolset as **Autodesk Maya, SideFX Houdini, Foundry Nuke, Foundry Mari and Mercenaries' Guerilla Render**, extended by in-house tools ([Fortiche FAQ](https://forticheprod.com/faq/), S, Primary), and Guerilla Render's official account posted the 2019 Arcane trailer with "#GuerillaRender inside" ([Guerilla Render on X](https://x.com/guerillarender/status/1185231595197882368?lang=en), S, Primary). SEO sites that name V-Ray or Arnold are guessing and are contradicted by both ([yelzkizi.org](https://yelzkizi.org/what-3d-program-did-arcane-use/), Aggregator). The painted look is built upstream of the renderer. Concept paintings of Piltover and Zaun became binding references for modelers and texture artists, who **hand-painted textures and projected paint onto 3D sets with traditional-style brushes, deliberately keeping freehand lines shaky** ([80.lv on Arcane backgrounds](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds), S; [Arcane S2 texturing video](https://www.youtube.com/watch?v=gCJIJG6Lz84), S, publisher unverified: one summary calls it Fortiche's, a third-party research file calls it a Foundry video). Hand-drawn 2D FX were added **on top of finished 3D animation** ([SyncSketch interview with Alexis Wanneroy](https://blog.syncsketch.com/creator-stories/arcane-fortiche/), S, Primary), reportedly in Toon Boom Harmony ([VFX Apprentice](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends), S, Press). In Season 2, hand-drawn elements were **placed on cards in Houdini** next to art-directed procedural rays ([VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/), S, Press), and some Houdini or Maya simulations were **repainted frame by frame** to match the painterly look ([Creative Bloq](https://www.creativebloq.com/art/2d-animation/how-the-creative-team-behind-netflixs-arcane-pushed-the-animation-even-further-for-the-second-season), S, Press). A compositing department led by Yann Leroy produced the final images, handling "lighting, effects, and artistic rendering" ([3DVF](https://3dvf.com/en/arcane-how-does-it-feel-to-work-on-a-major-hit-series/), S, Press).

Season 1 character animation was **keyframed with no motion capture**, using live-action reference the animators shot or found ([SyncSketch](https://blog.syncsketch.com/creator-stories/arcane-fortiche/), S; [Arcane on X](https://x.com/arcaneshow/status/1564401767772991488), S, Primary). The one documented exception is Season 2 crowds: **313 crowd shots built from about 500 animation cycles in Golaem, with Xsens mocap retargeted onto Fortiche's rigs** ([Autodesk blog](https://blogs.autodesk.com/media-and-entertainment/2025/03/26/crafting-crowds-fortiche-golaem-and-the-magic-of-arcane-season-2/), S, Primary vendor). Scale matters when you calibrate expectations: the studio reportedly grew from about 15 to about 300 people for Season 1 ([RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline), S, attribution uncertain) and peaked around **450 artists** on Season 2 ([VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/), S). Two widely repeated details, that FX ran at **12 fps against 24 fps characters** and that "four or five 2D artists" made most effects, trace only to press and aggregator pages without a named Fortiche source, so treat both as unverified.

### Project Gold grows its brushstrokes as geometry

**Project Gold** is Blender Studio's 16th open movie, announced in May 2023 with director Jericca Cleland and a stated aim to "push for highly art-directable NPR and stylization tools in Blender, notably via light linking in Cycles, the viewport compositor" ([Blender Studio announcement](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/), S, Primary). It was refocused from a short film into a **technical showcase**, premiered at Blender Conference 2024 and was released online on **7 November 2024** together with production files and the free **Brushstroke Tools** extension ([80.lv](https://80.lv/articles/blender-studio-s-stylized-tech-demo-released-with-project-files), S; [premiere post](https://studio.blender.org/blog/project-gold-premiere/), S, Primary). The look is geometric rather than a post filter: Geometry Nodes generate **layers of procedural 3D brushstrokes** that either fill a mesh surface or are drawn onto it, rendered in Cycles with light linking and compositor work ([CG Channel](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/), S). The mechanism is explained in the free Blender Conference 2024 talk "Procedural Oil Painting for Film Production" ([BCON 2024](https://conference.blender.org/2024/presentations/3925/), S, Primary). Gold did **not** use the separate EEVEE NPR prototype, which began with a July 2024 workshop between Blender developers and Dillon Goo Studio ([NPR Project blog](https://code.blender.org/2025/05/npr-project/), S) and has since been discontinued (section 5).

One press summary says Gold's project files and the add-on are public while the production logs and the Brushstroke Tools workshop are for subscribers ([Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools), S). The licence of Gold's files was not verified, although Blender Studio content is generally CC-BY with per-asset exceptions ([Blender Studio remixing page](https://studio.blender.org/remixing/), S). A painterly follow-up, *Singularity*, was reported "at the finishing line for shading and lighting" ([80.lv](https://80.lv/articles/new-blender-studio-s-open-movie-nears-completion), S, release status unverified), and Blender Studio's announced feature film *OVERGROWN* promises more open pipeline tools for larger productions ([Blender Studio](https://studio.blender.org/blog/overgrown-announcement/), S).

### Mielgo puts keyframed characters inside paintings

Alberto Mielgo's three films share one move: **painted environments, keyframed 3D characters lit to match the paint, and a heavy 2D finishing pass**. On *The Witness* (2019), Vaughan Ling built "3D paintings" in **Blender/Cycles** for camera-heavy shots; about **80% of what is on screen is straight painting arranged in 3D space**, the rest being reflections, shadows, CG elements and FX cards, while characters were done in **Maya and rendered in Arnold** ([BlenderNation interview with Vaughan Ling](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/), S, Primary crew). Mielgo told the lighters where the light came from in each painting, used Marvelous Designer for cloth, kept animation fully keyframed ("NO Mocap, NO rotoscope"), and then "played with the levels" so each shot reacted like an overexposing camera ([befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/), S, Primary director).

*The Windshield Wiper* (2021, Oscar for Best Animated Short) was self-produced over about **six years**: Mielgo painted every background in **Photoshop**, Leo Sánchez Barbosa's team keyframed 3D characters in **Maya**, and the film was composited in **After Effects**. Mielgo calls it "a 2D background with a 3D character on it", with deliberately limited motion where characters "basically breathe a little bit, and that's good enough" ([Animation Magazine](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/), S; [befores & afters Q&A](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/), S; [AWN](https://www.awn.com/animationworld/windshield-wiper-reveals-many-sides-modern-love), S; which outlet carries which quote is unverified). *Jibaro* (2022) is "essentially a 3D film" in which many shots are painted, some forests were fully built and lit in 3D, and "a lot of 2D" happened in post ([IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/), S). **Agora Studio rigged and hand-keyed every character** from a week of multi-camera footage of choreographer Sara Silkins' dancers, after testing an Xsens suit and finding it "too clean and too perfect" ([Agora Studio on LinkedIn](https://www.linkedin.com/posts/agora-vfx_this-is-surprising-for-many-jibaros-character-activity-6933808243391561728-ot8f), S, Primary vendor); the crew reportedly numbered about 72, including 20 animators ([Fox Renderfarm](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/), S, secondary). Maya, Houdini and Arnold are named for Jibaro only in search summaries ([Game Rant](https://gamerant.com/interview-alberto-mielgo-love-death-and-robots-volume-3-jibaro-netflix/), S), and no source found names its compositing package or frame-stepping choices.

Read together, the productions suggest a small-team recipe: paint keys or plates first, project them onto simple geometry or grow strokes on it, keyframe characters from shot reference with held poses, light per object to match the paint, draw or card-instance the FX, and finish with an aggressive grade. The Spider-Verse lineage is directly connected: Mielgo was an early production designer on *Into the Spider-Verse* and is credited as visual consultant ([albertomielgo.com](https://www.albertomielgo.com/spiderverse), S), and Ling did vis-dev on it ([BlenderNation](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/), S). Its stepped-timing philosophy is covered in section 6.

### At a glance: where the "paint" lives in each production

| Production | Where the painted look comes from | Stated tools (evidence) | Closest free route |
|---|---|---|---|
| Arcane S1–S2 (Fortiche) | Hand-painted textures; projected matte-painted sets; hand-drawn FX; per-shot compositing | Maya, Houdini, Nuke, Mari, Guerilla Render (S, Primary); Harmony for 2D FX (S, Press); Photoshop (S, Press/Aggregator) | Krita + Ucupaint textures, Blender Quick Edit projection, Grease Pencil v3 FX, Blender compositor |
| Project Gold (Blender Studio) | Procedural 3D brushstroke geometry over simple forms; light linking; compositor | Blender, Geometry Nodes, Cycles (S, Primary) | Brushstroke Tools in Blender, directly |
| The Witness (2019) | Paintings arranged in 3D (about 80% of the frame); FX cards; per-shot level grading | Blender/Cycles sets, Maya/Arnold characters, Marvelous Designer (S, Primary crew) | Krita paintings camera-projected in Blender + CloudRig characters |
| The Windshield Wiper (2021) | Photoshop backgrounds under keyframed 3D characters; limited animation | Photoshop, Maya, After Effects (S, Press) | Krita plates + Blender characters + Blender compositor |
| Jibaro (2022) | Mix of painted shots, lit 3D forest, 3D water sims, 2D post | Maya/Houdini/Arnold reported (S, unconfirmed); Agora hand-keyed animation (S, Primary) | Blender + Simulation Nodes or FLIP Fluids (paid) + paint-over in comp |

### Free breakdowns, talks and documents

| Resource | Production | Type | Ev. / tier | Link |
|---|---|---|---|---|
| Arcane: Bridging the Rift (5 episodes; Ep. 3 "Killstreaks Meet Keyframes" covers the visual style) | Arcane S1 | Official docuseries, free on YouTube | S, Primary | [Episode guide](https://www.oneesports.gg/league-of-legends/arcane-bridging-the-rift/) |
| Arcane S2 texturing: Animating the hand-painted look | Arcane S2 | Talk video | S (publisher unverified) | [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84) |
| Fortiche at FMX 2025: Arcane Season 2 deep dive | Arcane S2 | Studio blog | L | [forticheprod.com](https://forticheprod.com/blog/projects-events/fortiche-rocks-fmx-2025-with-arcane-season-2-deep-dive/) |
| SIGGRAPH Asia 2024 Arcane S2 coverage (Maya, Rec.709, limits of projected mattes) | Arcane S2 | Event write-up | L | [InCG](https://www.incgmedia.com/makingof/siggraph-asia-2024-arcane-season-2) |
| "Fortiche: Crafting the Bridge", SIGGRAPH 2023 production session (abstract only; session not public) | Arcane | Talk abstract | S, Primary | [ACM DL](https://dl.acm.org/doi/10.1145/3577023.3585274) |
| Crafting Crowds: Fortiche, Golaem and Arcane S2 | Arcane S2 | Vendor blog with crew | S, Primary | [Autodesk](https://blogs.autodesk.com/media-and-entertainment/2025/03/26/crafting-crowds-fortiche-golaem-and-the-magic-of-arcane-season-2/) |
| The Making of Arcane (Alexis Wanneroy) | Arcane S1 | Interview | S, Primary | [SyncSketch](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) |
| iAnimate podcast with Alexis Wanneroy | Arcane | Podcast | S, Primary | [iAnimate](https://ianimate.net/animationpodcast/arcane-magic-secrets-fortiche-lead-alexis-wanneroy-podcast) |
| Riot Games and Fortiche get revolutionary with Arcane S2 | Arcane S2 | Trade article | S, Press | [VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/) |
| A Closer Look at Texturing in Arcane, Parts 1–2 | Arcane | Article with production models | S, Press | [Part 1](https://80.lv/articles/a-closer-look-at-texturing-in-arcane) · [Part 2](https://80.lv/articles/a-closer-look-at-texturing-in-arcane-part-2) |
| How traditional art and 3D combine for Arcane backgrounds | Arcane S2 | Article | S, Press | [80.lv](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds) |
| Project Gold film and premiere post | Gold | Open movie | S, Primary | [Blender Studio](https://studio.blender.org/blog/project-gold-premiere/) · [YouTube](https://www.youtube.com/watch?v=nV_awXI9XJY) |
| Procedural Oil Painting for Film Production (BCON 2024) | Gold | Conference talk | S, Primary | [conference.blender.org](https://conference.blender.org/2024/presentations/3925/) |
| Gold production logs (some may be subscriber-only) | Gold | Production logs | S, Primary | [Logs index](https://studio.blender.org/projects/gold/production-logs/) · [Log 01 video](https://video.blender.org/videos/watch/c948ed21-75b7-4b7c-8d96-3cec7dabb51b) |
| Director Alberto Mielgo on The Witness | The Witness | Interview | S, Primary | [befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/) |
| Interview with Vaughan Ling | The Witness | Interview | S, Primary | [BlenderNation](https://www.blendernation.com/2019/11/18/interview-with-vaughan-ling-of-love-death-robots-the-witness/) |
| The development process behind Jibaro | Jibaro | Director breakdown via press | S, Press | [80.lv](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro) |
| Agora Studio on Jibaro's hand-keyed animation | Jibaro | Vendor post and portfolio | S, Primary | [LinkedIn](https://www.linkedin.com/posts/agora-vfx_this-is-surprising-for-many-jibaros-character-activity-6933808243391561728-ot8f) · [Portfolio](https://agora.studio/portfolio/706/jibaro) |
| Official Making of Jibaro clip | Jibaro | Video | S, Primary | [YouTube](https://www.youtube.com/watch?v=R4fkHC0-Pyw) |
| Mielgo Q&A on The Windshield Wiper | Windshield Wiper | Interview | S, Primary | [befores & afters](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/) |
| Impressions of 21st-century love | Windshield Wiper | Trade article | S, Press | [Animation Magazine](https://www.animationmagazine.net/2021/12/impressions-of-21st-century-love-alberto-mielgo-on-the-windshield-wiper/) |

### Free recreations of the looks

| Recreation | Target | Tools | Ev. / tier | Link |
|---|---|---|---|---|
| Jibaro shot remade in Blender and Substance (the most directly useful Mielgo-look recreation found) | Jibaro | Blender, Substance | S, Fan | [BlenderNation](https://www.blendernation.com/2022/07/30/jibaro-from-love-death-robots-shot-remade-using-blender-and-substance/) · [80.lv](https://80.lv/articles/a-scene-from-ldr-s-jibaro-episode-recreated-with-blender-substance) |
| Recreating a Jibaro scene (water, dance, collision VDB splashes) | Jibaro | Houdini, Arnold | S, Fan | [80.lv](https://80.lv/articles/recreating-a-scene-from-ldr-s-jibaro-in-houdini-and-arnold) |
| Golden Woman scene | Jibaro | Blender, UE5 | S, Fan | [80.lv](https://80.lv/articles/golden-woman-scene-from-jibaro-recreated-in-blender-ue5) |
| Ashli: a Mielgo-style character | Mielgo | 3ds Max, V-Ray | S, Fan | [80.lv](https://80.lv/articles/ashli-making-a-mielgo-style-character-in-3ds-max-v-ray) |
| The Witness character fan art | The Witness | not captured | S, Fan | [80.lv](https://80.lv/articles/love-death-robots-fan-art-creating-the-character-from-the-witness) |
| Ekko recreated with Substance 3D and Blender | Arcane | Substance 3D Painter, Blender | S, Fan | [80.lv](https://80.lv/articles/3d-artist-recreates-arcane-s-ekko-with-substance-3d-blender) |
| Arcane Art Study: Piltover Citizen | Arcane | not captured | S, Fan | [The Rookies](https://www.therookies.co/entries/39954) |
| Arcane 2D FX fan art collaboration | Arcane FX | 2D | S, Fan | [ArtStation](https://www.artstation.com/artwork/DAYqde) |
| Arcane-like Stylized Character Shader (1 star, created May 2026, hobby-level) | Arcane | Unity ShaderLab | R, Fan | [GitHub](https://github.com/Databazator/Arcane-like-Stylized-Character-Shader) |
| Spiderverse-Shader-Unity (43 stars, 2019, halftone post effect) | Spider-Verse | Unity | R, Fan | [GitHub](https://github.com/adamb70/Spiderverse-Shader-Unity) |
| Recreating Into the Spider-Verse's camera | Spider-Verse | Blender | S, Fan | [BlenderNation](https://www.blendernation.com/2019/08/17/blender-breakdown-recreating-into-the-spiderverses-camera/) |

GitHub API searches for "arcane shader", "arcane style npr" and "painterly npr blender" found **no maintained "Arcane look" toolkit**, so Arcane-style work relies on generic NPR tools plus painting. For Gold, Brushstroke Tools itself is the canonical recreation kit.

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| *The Art of Arcane* (Titan Books) | 224-page art book; about £45 / US$66 per listings (S) | [AbeBooks](https://www.abebooks.com/Art-Arcane-Hardcover-Elisabeth-Vincentelli-Titan/32138595134/bd) |
| *The Art of Arcane*, Limited Portfolio Edition | Deluxe edition of the same book, about £150 (S) | [Forbidden Planet](https://forbiddenplanet.com/431354-the-art-of-arcane-portfolio-edition-hardcover/) |
| IAMAG Master Classes 25, "Creating Arcane by Fortiche Production" | Ticketed in-person masterclass, Paris, 7 March 2025 (S) | [Swapcard](https://app.swapcard.com/event/iamag-master-classes-2025/planning/UGxhbm5pbmdfMjUzMTc0MQ==) |
| Blender Studio subscription | Gold production logs, files and the "Stylized Rendering with Brushstrokes" workshop; about €11.50/month per one snippet, a conflicting $17 figure also appears (S) | [studio.blender.org/join](https://studio.blender.org/join/) |

## 2. Pre-production and pipeline: copy Blender Studio's conventions before its servers

Both reference studios front-load decisions. Fortiche spent **about a year of visual development on Piltover alone** (shape language, color, materials), with development artist Anne-Laure To on color script and color keys ([Playgrounds speaker page](https://weareplaygrounds.nl/slot/fortiche-anne-laure-to/), S). It built palettes from director-selected mood boards into a deliberate alternation of darker moments and high-contrast sequences across episodes ([VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/), S), and locked story heavily at the storyboard stage with every department in-house ([SyncSketch](https://blog.syncsketch.com/creator-stories/arcane-fortiche/), S). Mielgo works as a painter-director: he painted all *Windshield Wiper* backgrounds himself so the 3D characters would sit inside them ([AWN](https://www.awn.com/animationworld/windshield-wiper-reveals-many-sides-modern-love), S), and on *Jibaro* he reportedly drew storyboard drafts on paper, scanned them into After Effects, colored them and placed them in the matching 3D scenes ([Fox Renderfarm](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/), S, secondary). The transferable rules for an indie team are to make painted color keys **binding references** for modeling and texturing, and to decide **per shot** whether a set is a full 3D painterly build or a single painted plate with 3D characters composited in; the second is far cheaper on locked-off shots.

Blender Studio's open pipeline is the best-documented Blender-only production setup. It consists of add-ons (**Blender Kitsu** with its built-in Shot Builder, **Asset Pipeline**, **Blender SVN**, **Render Review**, **Contact Sheet**, plus animation and utility tools) on top of three services: **Kitsu** for tracking, **SVN or Git LFS** for versioning and **Flamenco** for rendering ([Pipeline setup docs](https://studio.blender.org/tools/pipeline-overview/quick-start/setup), S). Shot Builder creates one file per task type from Kitsu data, links output collections between layout, animation, FX and lighting files, and loads the editorial cut into each shot's sequencer ([Blender Kitsu docs](https://studio.blender.org/tools/addons/blender_kitsu), S). The canonical code lives on projects.blender.org; a GitHub mirror listing 14 tools was **archived on 1 July 2026** ([paulgolter/blender-studio-tools](https://github.com/paulgolter/blender-studio-tools), R). The setup assumes someone who can host Kitsu, SVN and Flamenco, and the third-party OpenStudioHub wrapper exists because its author found "a brutal technical learning curve" ([OpenStudioHub](https://github.com/3dvm/openstudiohub), R). For one to three people, copy the **conventions** first: `local`, `shared` and `svn` project roots; an SVN tree of `pro`, `pre`, `dev`, `edit` and `tools`; and shot files at `svn/pro/shots/<sequence>/<shot>/<shot>-<task>.blend` ([folder structure](https://studio.blender.org/tools/td-guide/folder_structure_overview), S; [naming conventions](https://studio.blender.org/tools/naming-conventions/introduction), S). Add Kitsu and Flamenco next, and Shot Builder hooks and Asset Pipeline once the shot count justifies them. Expect the toolset to change again: *OVERGROWN* is promised to bring "open source tools for larger animated productions" ([Digital Production](https://digitalproduction.com/2026/07/09/overgrown-targets-an-open-feature-pipeline-for-blender/), S).

Two pre-production staples have decayed. **Storyboarder** has had no stable release since v2.1.0 (September 2023), only a v3.0.0 pre-release in February 2024, and a June 2026 issue asking whether it is still maintained has no maintainer reply ([releases](https://github.com/wonderunit/storyboarder/releases), R; [issue #2665](https://github.com/wonderunit/storyboarder/issues/2665), R). Blender's **Storypencil** add-on has user reports of breakage with Grease Pencil 3 in Blender 4.3+ ([Extensions reviews](https://extensions.blender.org/add-ons/storypencil-storyboard-tools/reviews/), S). Gold itself was storyboarded inside Blender ([Storyboarding in Blender](https://studio.blender.org/blog/project-gold-storyboarding-in-blender/), S), which keeps boards, animatic and layout in one file lineage. Kitsu, by contrast, shipped five releases in the last week of September 2026 ([Kitsu releases](https://github.com/cgwire/kitsu/releases), R). For rendering, Flamenco runs on your own machines (stable 3.9.3; [Flamenco download](https://flamenco.blender.org/download/), S). SheepIt is a free community farm that "does not lay any claim to generated images" but renders on volunteers' machines, so keep confidential or pre-release work off it ([SheepIt FAQ](https://www.sheepit-renderfarm.com/faq), S). Blender Studio assets are generally reusable commercially under CC-BY with attribution, but check every asset's licence line: the Agent 327 film file, for example, is CC-BY-ND ([Agent 327 post](https://studio.blender.org/blog/agent-327-film-file-released-as-cc-by-nd/), S).

### Free tools for script, boards, tracking, versioning, render and review

| Tool | Stage and use | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Story Architect (STARC) | Script; imports and exports Fountain, Final Draft, Celtx, Trelby, PDF | GPL-3.0 (optional paid cloud features) | Active, 3,450 commits | R | [GitHub](https://github.com/story-apps/starc) |
| Trelby | Script | GPL-2.0 | Maintained; Python 3 port merged | R | [GitHub](https://github.com/trelby/trelby) |
| Fountain | Plain-text screenplay format that diffs cleanly in Git or SVN | Open format | Supported by Story Architect and Trelby | S | [fountain.io](https://fountain.io/2023/05/30/trelby/) |
| Krita | Visdev, color keys, color scripts, painted plates | GPL-3 | Active; 6.0.0 released 19 Mar 2026, 6.0.4.1 on 1 Oct 2026 | R | [Tags](https://github.com/KDE/krita/tags) · [Manual](https://docs.krita.org/en/user_manual.html) |
| Blender Grease Pencil + Video Sequencer | Boards and animatic in the same file lineage as layout | GPL | Built-in; used to storyboard Gold | S | [Blender Studio post](https://studio.blender.org/blog/project-gold-storyboarding-in-blender/) |
| storytools (Pullusb) | Grease Pencil storyboarding toolset | not checked | Listed on GitHub; activity not checked | R | [GitHub](https://github.com/Pullusb/storytools) |
| greasy-boarding-blender | Grease Pencil storyboarding add-on | not checked | Maintenance not checked | S | [GitHub](https://github.com/marikodes/greasy-boarding-blender) |
| Kdenlive | External editor | GPL-3.0 | Very active (24k+ commits) | R | [GitHub](https://github.com/KDE/kdenlive) |
| Shotcut | External editor | GPLv3 | Active | R | [GitHub](https://github.com/mltframework/shotcut) |
| OpenTimelineIO | Editorial interchange; FCP XML, AAF and EDL adapters are now separate plugins | Apache-2.0 | v0.18.1 latest seen (release dates on the page are inconsistent) | R | [GitHub](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) |
| Kitsu (with Zou API and Gazu client) | Production tracking and review | AGPL-3.0 | Very active: v1.0.64 to v1.0.68 shipped 22–29 Sept | R | [Releases](https://github.com/cgwire/kitsu/releases) · [Zou](https://github.com/cgwire/zou) |
| Blender Kitsu add-on with Shot Builder | Kitsu inside Blender; builds per-task shot files and links them | not verified | Maintained by Blender Studio | S | [Docs](https://studio.blender.org/tools/addons/blender_kitsu) |
| Asset Pipeline | Task-layer asset files (modeling, rigging, shading) with builder and updater | not verified | Maintained by Blender Studio | S | [Docs](https://studio.blender.org/tools/addons/asset_pipeline) |
| Blender SVN | Subversion UI inside Blender | not verified | Maintained by Blender Studio | S | [Docs](https://studio.blender.org/tools/addons/blender_svn) |
| Contact Sheet / Render Review | Grid contact sheets and Flamenco render review in the VSE | not verified | Whether still separate add-ons is unverified | S | [Contact Sheet](https://studio.blender.org/tools/addons/contactsheet) · [Usage](https://studio.blender.org/tools/pipeline-overview/quick-start/usage) |
| Prism Pipeline 2 | Lighter, file-based pipeline; free tier covers Blender, Houdini, Maya, Nuke and more "in commercial and non-commercial projects" | LGPL-3.0 | Active; USD, Unreal and ZBrush plugins are paid | R / S | [GitHub](https://github.com/PrismPipeline/Prism) · [Licensing](https://prism-pipeline.com/docs/latest/general/licensing/) |
| AYON + ayon-blender | Full pipeline platform; heavy for a short | Integrations Apache-2.0; server moving to Functional Source License | Active | R / S | [ayon-blender](https://github.com/ynput/ayon-blender) · [Licence post](https://ayon.app/blog/ayon-server-is-adopting-fair-source) |
| Git LFS | Large-file versioning for .blend files and textures, with locking | open source | Active | R | [GitHub](https://github.com/git-lfs/git-lfs) |
| Perforce P4 (free tier) | Version control, free for up to 5 users and 20 workspaces | Proprietary | Current | S | [perforce.com](https://www.perforce.com/products/helix-core/free-version-control) |
| Anchorpoint Personal | Git with file locking for artists; free tier is single-user, non-commercial | Proprietary | Current | S | [anchorpoint.app](https://www.anchorpoint.app/blog-topics/version-control) |
| Diversion Indie | Cloud version control; free tier reportedly up to 10 users and 100 GB | Proprietary | Limits unverified | S | [diversion.dev](https://www.diversion.dev/) |
| Flamenco | Render manager (add-on, Manager web UI, Workers) on your own machines | open source | Stable 3.9.3; 3.10-beta1 not for production | S | [flamenco.blender.org](https://flamenco.blender.org/) |
| SheepIt | Free community render farm for Blender; 3 projects rendering at once; no NSFW | Service | Current; confidentiality risk is inherent | S | [FAQ](https://www.sheepit-renderfarm.com/faq) · [Terms](https://www.sheepit-renderfarm.com/termsofuse) |
| CrowdRender | Peer-to-peer rendering across about 2–20 machines, no server | Free add-on | **At risk**: Blender 5.0 support "in development" | S | [crowd-render.com](https://www.crowd-render.com/single-post/october-update-for-our-3d-rendering-distributed-rendering-plugin-for-blender) |
| Open RV | Professional review player | open source | Build from source only | R | [GitHub](https://github.com/AcademySoftwareFoundation/OpenRV) |
| xSTUDIO (DNEG) | Review player for VFX and feature animation | Apache-2.0 | v1.3.0; build guides, no prebuilt binaries evident | R | [GitHub](https://github.com/AcademySoftwareFoundation/xstudio) |
| OpenStudioHub | Per-project sandbox that wraps Blender Studio tools, Kitsu SSO and SVN | GPL-3.0 | Tiny (111 commits, 2 stars) | R | [GitHub](https://github.com/3dvm/openstudiohub) |

### Free documents and guides

| Resource | What you get | Ev. | Link |
|---|---|---|---|
| Blender Studio pipeline Quick Start | Setup and day-to-day usage of the full open pipeline | S | [Setup](https://studio.blender.org/tools/pipeline-overview/quick-start/setup) · [Usage](https://studio.blender.org/tools/pipeline-overview/quick-start/usage) |
| Folder structure, SVN tree and naming conventions | Copyable project layout and file naming | S | [Folders](https://studio.blender.org/tools/td-guide/folder_structure_overview) · [SVN tree](https://studio.blender.org/tools/naming-conventions/svn-folder-structure) · [Naming](https://studio.blender.org/tools/naming-conventions/introduction) |
| Shot Assembly spec | How layout, animation, FX and lighting files link to each other | S | [Shot Assembly](https://studio.blender.org/tools/pipeline-overview/shot-production/shot-assembly) |
| Storypencil demo | Storyboarding with Grease Pencil and the VSE (check GPv3 compatibility first) | S | [video.blender.org](https://video.blender.org/w/nmfHw6DoKztuA8WFKbp5B2) |
| Self-Hosting a Blender Render Farm Using Flamenco in 2026 | Step-by-step Flamenco setup | S | [CGWire blog](https://blog.cg-wire.com/self-hosted-blender-render-farm/) |
| Blender Studio remixing and licensing | What CC-BY reuse of Blender Studio assets requires | S | [Remixing](https://studio.blender.org/remixing/) |
| Production Recap: Story Development for Gold | How Gold's story was developed | S | [Blender Studio](https://studio.blender.org/blog/production-recap-gold-story-development/) |
| "Building a Blender pipeline in 30 Minutes" | ACM entry, probably a SIGGRAPH 2025 talk; authorship and content unverified | S | [ACM DL](https://dl.acm.org/doi/10.1145/3721251.3742867) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Blender Studio subscription | Production files, logs and training from Gold and other open movies; about €11.50/month per one snippet, conflicting figures exist | [studio.blender.org/join](https://studio.blender.org/join/) |
| Toon Boom Storyboard Pro | Industry storyboarding app; about $90/month or $776/year per snippet | [Toon Boom shop](https://shop.toonboom.com/en/subscriptions/storyboard-pro) |
| Autodesk Flow Production Tracking (ex-ShotGrid) | Enterprise tracker with RV; about $45–50 per user per month per listings | [Capterra](https://capterra.com/p/150447/Shotgun/) |
| ftrack Studio | Tracking, scheduling and review; about $25–30 per user per month | [G2 pricing](https://www.g2.com/products/ftrack/pricing) |
| Prism Plus / Pro | Paid USD, Unreal and ZBrush plugins; €19 or €45 per user per month | [CG Channel](https://www.cgchannel.com/2023/11/prism-2-0/) |
| Perforce P4 Cloud | Hosted P4, about $39 per user per month per snippet | [perforce.com](https://www.perforce.com/products/helix-core/free-version-control) |
| Anchorpoint Team | Git plus locking for teams, about €20 per user per month with an indie discount (third-party figure) | [Comparison](https://www.itechguides.com/compare/anchorpoint-game-version-control-system-vs-git/) |
| Diversion Pro | Cloud version control from $25 per user per month | [diversion.dev](https://www.diversion.dev/) |
| Storyboard & Animatic (Ed White) | Blender add-on for Grease Pencil boards and animatics; price not captured | [Gumroad](https://edwhite3d.gumroad.com/l/StoryboardAnimatic) |
| Story Architect premium | Optional cloud and pro features on top of the GPL app | [starc.app](https://starc.app) |

## 3. Modeling and sculpting: simple forms, controlled normals, detail in paint

None of the three productions wins on modeled detail. Arcane artists reportedly painted highlights and shadows into textures, with forms that are "not symmetrical, angles are super defined, and brushstrokes are visible but not noisy" ([RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline), S, attribution within the summary uncertain). Gold's character Mikassa went through sculpt refinement and production retopology before rigging tests ([Gold production logs, Nov 2023](https://studio.blender.org/projects/gold/production-logs/2023/nov/), S). Mielgo describes a "very simplified" character look in which he "intentionally removed details they didn't need" ([SlashFilm](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/), S). The modeling brief is therefore **graphic, often asymmetric silhouettes; clean, deformation-ready topology; and surface detail pushed into paint, strokes or comp**. Arcane's own modeling software is not established: aggregator lists naming ZBrush and 3ds Max conflict with each other and cite no primary source. The closest fully free and documented analogue is Julien Kaspar's **Stylized Character Workflow** (sculpt, clean retopology, rig-ready mesh), hosted on Blender Studio and built for Blender 2.8, with a free 30-minute YouTube overview ([course](https://studio.blender.org/training/stylized-character-workflow/), S; [overview](https://www.youtube.com/watch?v=f-mx-Jfx9lA), S), combined with Brushstroke Tools.

Shading control on faces is the main modeling-side NPR skill, and Blender changed underneath it. **Blender 4.1 removed Auto Smooth**: smoothing became a "Smooth by Angle" modifier and custom normals no longer require Auto Smooth, so any tutorial that tells you to enable it is out of date ([PR #108014](https://projects.blender.org/blender/blender/pulls/108014), S). The standard soft-falloff technique is **proxy normal transfer**: a Data Transfer modifier copies Custom Normals (Face Corner Data, mapping "Nearest Corner and Best Matching Face Normal") from a smooth sphere or ellipsoid onto the face ([VRC Library](https://vrclibrary.com/wiki/books/random-assorted-tips-with-trixxed/page/normals-data-transfer-normals-for-cel-shading), S). Hand-edited normals descend from Arc System Works' GDC 2015 talk on *Guilty Gear Xrd*, whose team "shunned mathematical accuracy to create perfectly consistent cel shading" ([GDC Vault](https://www.gdcvault.com/play/1022031/GuiltyGearXrd-s-Art-Style-The), S). In Blender that work is done with the MIT-licensed **Abnormal** add-on, whose latest release (v1.1.6, November 2025) targets Blender 4.5 and does not mention 5.x ([Abnormal releases](https://github.com/bnpr/Abnormal/releases), R). Since **Blender 4.5 the Set Mesh Normal geometry node** edits custom normals procedurally: its Tangent Space mode survives deformation and suits rigged characters, while Free mode is faster but static ([4.5 release notes](https://developer.blender.org/docs/release_notes/4.5/geometry_nodes/), S). For a painterly rather than anime look, proxy transfer is usually enough, because its soft, simplified light falloff is what painterly shading wants; **SDF face-shadow threshold maps** matter mainly for hard two-tone cel shading under a moving key light. Keep the transfer as a live modifier above the Armature modifier (or rig the proxy with the head) so normals survive facial deformation; that is general practice rather than a sourced rule.

Two free tools bring 2D-style per-shot distortion into 3D. Blender Studio's **Lattice Magic** has a Camera Lattice that works "essentially like Liquify, except it's operating on vertices instead of pixels" and manages shape keys so the cheat can be animated ([Blender Studio docs](https://studio.blender.org/tools/addons/lattice_magic), S). **PersPress**, a 2026 Geometry-Nodes-and-drivers setup, remaps camera-space depth so a face reads as if shot on a telephoto lens while the body and background keep wide-angle perspective; it needs Blender 5.2+ and is very new ([GitHub](https://github.com/a2d4f3s1/perspress), R). For environments, Brushstroke Tools covers painterly surfaces and free Geometry Nodes generators cover stylized trees and scatter. The free retopology route is RetopoFlow's GPL source on GitHub, actively updated and at v3.4.0 for Blender 3.6+ ([GitHub](https://github.com/CGCookie/retopoflow), R).

### Free tools for normals, camera cheats, retopology and stylized sets

| Tool | What it does for this look | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Data Transfer modifier + Smooth by Angle | Proxy normal transfer for soft, simplified face shading | GPL (Blender) | Built-in; Auto Smooth removed in 4.1 | S | [PR #108014](https://projects.blender.org/blender/blender/pulls/108014) |
| Set Mesh Normal node | Procedural or rig-driven custom normals; Tangent Space for deforming meshes | GPL (Blender) | Built-in since 4.5 | S | [Manual](https://docs.blender.org/manual/en/latest/modeling/geometry_nodes/mesh/write/set_mesh_normal.html) |
| Abnormal | Hand-sculpt vertex normals: mirror, sphereize, rotate gizmo, copy and paste | MIT | v1.1.6 (Nov 2025) for 4.5; no 5.x note; about 492 stars | R | [GitHub](https://github.com/bnpr/Abnormal) · [Wiki](https://bnpr.gitbook.io/abnormal-wiki) |
| Lattice Magic (Camera Lattice) | Liquify-style, animatable camera-space cheats | not verified | On the Extensions platform; 5.x unverified | S | [Docs](https://studio.blender.org/tools/addons/lattice_magic) · [Extensions](https://extensions.blender.org/add-ons/latticemagic/) |
| PersPress | Telephoto-face, wide-body perspective correction; keeps original normals and depth as AOVs | GPL-3.0+ | Blender 5.2+; created July 2026; very low adoption | R | [GitHub](https://github.com/a2d4f3s1/perspress) |
| Anime SDF Gen | Hand-author face-shadow threshold maps with editable Bézier boundaries | GPL-3.0+ | Blender 5.2+; v0.14.0; created Sept 2026; about 1 star | R | [GitHub](https://github.com/xht8723/Anime-SDF-Gen) |
| sdf_shadow_threshold_map | Interpolate a folder of shadow masks into an SDF threshold map (standalone) | MIT | Last push July 2025; about 128 stars | R | [GitHub](https://github.com/akasaki1211/sdf_shadow_threshold_map) |
| blender-sdf-face-shadow-baker | Bakes light-sweep shadow masks in Cycles for the tool above | MIT | Tested on 4.5.2 LTS; created July 2026 | R | [GitHub](https://github.com/ReefSnax/blender-sdf-face-shadow-baker) |
| RetopoFlow | Sketch-based retopology that snaps to the high-poly sculpt | GPL-3.0 (code; paid build funds it) | v3.4.0, Blender 3.6+; active Oct 2026; about 3.3k stars | R | [GitHub](https://github.com/CGCookie/retopoflow) |
| Brushstroke Tools | Procedural or drawn layers of 3D brushstrokes on surfaces | GPL-3.0 (per third-party docs) | v1.2.3 (Nov 2024 per snippet); Blender 4.2+; 5.x unverified | S / L | [Extensions](https://extensions.blender.org/add-ons/brushstroke-tools/) |
| Greasepencil Tools (Pullusb) | Drawing helpers for Grease Pencil in 3D space | GPL-3 | Updated Sept 2026 | R | [GitHub](https://github.com/Pullusb/greasepencil_tools) |
| Hair cards from curves (Daniel Bystedt) | Geometry Nodes setup that turns curve hair into cards | Free | Blender 3.6+ | S | [CG Channel](https://www.cgchannel.com/2024/03/daniel-bystedts-free-blender-add-on-creates-hair-cards-from-curves/) |
| GeometryNodes-Stylized-Scene-Generator (IRCSS) | Procedural stylized trees, rocks, rivers, houses, fences, smoke | **No licence stated** | Tested on Blender 3.4.1 | R | [GitHub](https://github.com/IRCSS/GeometryNodes-Stylized-Scene-Generator) |
| Stylized Fantasy Tree Generator (RC12) | Free procedural Geometry Nodes tree | Free (terms unverified) | 2024 release | S | [Gumroad](https://rc12.gumroad.com/l/fantasytree) |
| Easy Tree | Geometry Nodes procedural trees | not verified | On the Extensions platform | S | [Extensions](https://extensions.blender.org/add-ons/easy-tree/) |
| MTree (modular_tree) | Function-based tree generator | GPLv3 add-on, MIT core | 4.x/5.x support unconfirmed; 117 open issues | R | [GitHub](https://github.com/MaximeHerpin/modular_tree) |
| Free 4.3 brush-asset pack (Dots, Noise, Line, Rock, Voronoi) | Sculpt brushes set up as Blender 4.3+ assets | Free for personal and commercial use | 4.3+ | S | [Fab](https://www.fab.com/listings/3c8a71eb-76d6-4680-a16b-8f05c7e7bc7c) |
| SculptWolf-Essentials | Stylized chisel and VDM sculpt brushes | not stated | Created Jan 2026; about 2 stars | R | [GitHub](https://github.com/CamouForge/SculptWolf-Essentials) |
| batch_import_images_to_brushes | Batch-import alphas as sculpt or paint brushes | not stated | Blender 4.4+ | R | [GitHub](https://github.com/raja-muda/batch_import_images_to_brushes) |

### Free assets and production files to study

| Source | What it offers | Licence | Ev. | Link |
|---|---|---|---|---|
| Project Gold production files | Real painterly production files with Brushstroke Tools setups | Not verified (Blender Studio content is usually CC-BY) | S | [Project page](https://studio.blender.org/projects/gold/) |
| Blender Studio character rigs | Stylized open-movie characters (see section 6) | CC-BY | S | [Sprite Fright characters](https://studio.blender.org/projects/sprite-fright/characters/) |
| Poly Haven models + polyhavenassets add-on | Mostly realistic models for blockout and set dressing, in the asset browser | CC0 | L / R | [Models](https://polyhaven.com/models) · [Add-on](https://github.com/Poly-Haven/polyhavenassets) |
| Quaternius | Stylized low-poly models | Commonly CC0, not verified | L | [quaternius.com](http://quaternius.com/index.html) |
| Kenney | Game-style assets | Commonly CC0, not verified | L | [kenney.nl](http://kenney.nl/) |
| Sketchfab (downloadable filter) | Community models | Per-model CC licences | L | [Search](https://sketchfab.com/search?features=downloadable&sort_by=-pertinence&type=models) |
| TheBaseMesh | 600+ real-world-scale, unwrapped base meshes | not captured | S | [thebasemesh.com](https://thebasemesh.com/model-library) |
| Smithsonian Open Access | Scans as reference or remodeling bases | Open access | S | [si.edu/openaccess](https://www.si.edu/openaccess) |
| Blender Geometry Nodes demo files | Official procedural building and terrain examples | Blender demo files | L | [blender.org](https://www.blender.org/download/demo-files/#geometry-nodes) |

### Free tutorials, talks and references

| Resource | What you learn | Ev. | Link |
|---|---|---|---|
| Stylized Character Workflow (Julien Kaspar) | Film-production stylized character: blocking, wrinkles and folds, clean retopology (Blender 2.8 era; access tier unverified) | S | [Course](https://studio.blender.org/training/stylized-character-workflow/) · [Free overview](https://www.youtube.com/watch?v=f-mx-Jfx9lA) · [Blog](https://julienkaspar.artstation.com/blog/X4ar/stylized-character-workflow-blender-2-8-tutorial) |
| Live Retopology at BCON22 | Deformation-ready topology | S | [Blender Studio](https://studio.blender.org/blog/live-retopology-at-bcon22/) |
| GuiltyGearXrd's Art Style (GDC 2015) | Hand-edited normals and consistent cel shading | S | [GDC Vault](https://www.gdcvault.com/play/1022031/GuiltyGearXrd-s-Art-Style-The) |
| Data Transfer normals for cel shading | Exact modifier settings for proxy transfer | S | [VRC Library](https://vrclibrary.com/wiki/books/random-assorted-tips-with-trixxed/page/normals-data-transfer-normals-for-cel-shading) · [Yarsa DevBlog](https://blog.yarsalabs.com/normal-transfer-in-blender/) |
| Editing normals for shading anime (Blender 3.3) | Abnormal plus Data Transfer on face and hair (skip its Auto Smooth step on 4.1+) | S | [YouTube](https://www.youtube.com/watch?v=1puHJSkZy24) |
| Set Mesh Normal node in 4.5 | Blending normals procedurally | S | [80.lv](https://80.lv/articles/see-what-you-can-do-with-new-set-mesh-normal-node-in-blender-4-5) |
| SDF transition blending for shadow threshold maps (Japanese) | The algorithm behind the SDF face-map tools | L | [Nagakagachi blog](https://nagakagachi.hatenablog.com/entry/2024/03/02/140704) |
| Face Shadow Map creation and baking workflow (Unity product, free to read) | Step-by-step face-map authoring | L | [EricHu33 doc](https://github.com/EricHu33/AnimeShadingPlus-Anime-Toon-Shader/blob/main/Anime%20Shading%20Plus%28+%29%20User%20Manual%20e9875988ae1e41caa5198370d9cc963d/Face%20Shadow%20Map-%20Creation%20&%20Baking%20Workflow%20d3b8769021e04683a2f2ae4cf16ac810.md) |
| Stylized Environments with Blender 4 Geometry Nodes (companion code) | Free code from a paid Packt book | R | [GitHub](https://github.com/PacktPublishing/Stylized-Environments-with-Blender-4-Geometry-Nodes) |
| Blender anime foliage pipeline | Stylized foliage workflow | S | [Substack](https://trungduyng.substack.com/p/tutorial-blender-anime-foliage-pipeline) |
| Jinx modeled and textured in ZBrush; Arcane-inspired hand-painted character | Arcane-style character recreations | S | [80.lv Jinx](https://80.lv/articles/how-to-model-texture-jinx-from-arcane-with-zbrush) · [80.lv character](https://80.lv/articles/have-a-look-at-this-amazing-arcane-inspired-hand-painted-3d-character) |
| awesome-blender and 3d-resources | Curated meta-lists of add-ons, assets and tutorials | R | [awesome-blender](https://github.com/agmmnn/awesome-blender) · [3d-resources](https://github.com/devanshutak25/3d-resources) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| ZBrush (Maxon) | Industry-standard sculpting, common in Arcane-style recreations; price not captured | [maxon.net](https://www.maxon.net/en/zbrush-1) |
| 3000+ Blender Sculpting Brushes | Large brush-asset library for the Blender asset browser | [Superhive](https://superhivemarket.com/products/600-blender-sculpting-brushes) |
| 600+ Blender Sculpting Brushes | Brush-asset pack on ArtStation | [ArtStation](https://www.artstation.com/marketplace/p/AYpmb/600-blender-sculpting-brushes-assets-browser) |
| Stylized Hair PRO (Dean Zarkov) | Geometry Nodes procedural stylized hairstyles | [Gumroad](https://deanzarkov.gumroad.com/l/stylized_hair_pro) |
| Fondant Tools (Anime Face Proxy System) | Stylized-character tools sold as an alternative to fiddly proxy normal transfer | [Gumroad](https://fondanttools.gumroad.com/) |
| RetopoFlow (paid build) | Same GPL tool, packaged; purchases fund development | [Superhive](https://blendermarket.com/products/retopoflow) |
| Blendatlas hair packs | Hair Card Node Pack and curves-to-cards converter | [Blendatlas](https://blendatlas.com/products/a-hair-card-node-pack) |
| SetMeshNormal node setup (ditagdesign) | Third-party Set Mesh Normal setup; price and licence not captured | [Gumroad](https://ditagdesign.gumroad.com/l/SetMeshNormal) |
| Tradigital | Storefront of painterly Blender tools; contents not inspected | [Gumroad](https://tradigital.gumroad.com/) |
| Albero (David Cescatti) | Geometry Nodes tree generator with presets; pricing not captured | [80.lv](https://80.lv/articles/geometry-nodes-powered-tree-generator-for-blender) |

## 4. Texturing pairs UV-painted albedo with camera-projected paint-overs

Across the references, painted surface comes from three places: **UV-painted albedo** (Arcane's characters), **camera-projected paint-overs** (Arcane Season 2 sets and all three Mielgo films) and **procedural brushstroke geometry** (Gold). Arcane had a dedicated texturing department under Texturing Supervisor **Candice Theuillon**, whose Vi, Caitlyn and Silco breakdowns, along with 80.lv's two-part "A Closer Look at Texturing in Arcane", are the best free views of production textures ([80.lv Part 1](https://80.lv/articles/a-closer-look-at-texturing-in-arcane), S; [Theuillon: Vi](https://candicetheuillon.artstation.com/projects/b505vm), S). Which painting application Fortiche's texture artists used is not settled by any source read: Mari is on Fortiche's FAQ, Photoshop is named by press and aggregators, and Substance Painter appears only as "may have been used" speculation ([yelzkizi.org](https://yelzkizi.org/what-3d-program-did-arcane-use/), Aggregator). A third-party research file describes the Season 2 texturing video as showing Mari-painted albedo plus extra shadow, light and ID passes so lighting and comp can recompose the image ([lucid-loop research notes](https://raw.githubusercontent.com/jethac/lucid-loop/main/research/arcane-fortiche-art-style.md), file R, claim L). Arcane's background artists add detail selectively where characters interact ([80.lv backgrounds](https://80.lv/articles/arcane-artists-show-how-they-combine-traditional-art-3d-for-backgrounds), S).

Game-style hand-painted texturing and film painterly texturing differ in where the light lives. Game work typically **bakes lighting, AO and highlights into a small diffuse map**, because real-time budgets demand it; film painterly work **paints albedo-like color and brush texture that is then lit in the shot** with simplified, low-specular shaders, with shot-specific projections layered on top. That distinction is an inference from the sources rather than a published rule, but it matters when you pick tutorials, because many 80.lv "Arcane-style" recreations are explicitly game-ready ([80.lv cannon](https://80.lv/articles/creating-a-game-ready-cannon-in-an-arcane-inspired-style), S). Mielgo's "more impressionism than realism", with no pores or deep skin detail ([IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/), S), argues for **large-shape, low-frequency painted textures** rather than high-frequency PBR smart materials.

A complete free chain exists. Blender's texture paint includes **Quick Edit**, which sends a viewport capture to an external editor such as Krita, and **Apply**, which re-projects the painted result onto the mesh from that view, along with stencil masks and clone-from-paint-slot ([Blender source: space_view3d_toolbar.py](https://raw.githubusercontent.com/blender/blender/main/scripts/startup/bl_ui/space_view3d_toolbar.py), R). That round trip is the free analogue of Arcane's projected paint-overs. Blender has no native paint-layer stack, so **Ucupaint** fills the gap: GPL-3, about 2.2k stars, compatibility from Blender 2.76 to 5.2 in v2.4.9, new curvature, thickness and wireframe bake types, and September 2026 commits that fix Blender 5.3 issues ([Ucupaint releases](https://github.com/ucupumar/ucupaint/releases), R). Krita 6 does the brushwork, and the **blender-krita-link** plugin overlays UVs on the Krita canvas and live-updates the texture in Blender, although its author calls it "highly experimental" and its compatibility with Krita 6 is unverified ([GitHub](https://github.com/heisenshark/blender-krita-link-plugin), R). For a standalone 3D painter, **ArmorPaint**'s source is zlib-licensed and active, but prebuilt binaries are paid and the free route means compiling it ([armortools](https://github.com/armory3d/armortools), R); **Material Maker** (MIT) is the free procedural-plus-paint alternative ([GitHub](https://github.com/RodZill4/material-maker), R). Texture-space and object-space paint stays attached to surfaces in motion, while screen-space filters such as Kuwahara are cheap and global but can swim, so use filters to unify an image rather than to create the look.

### Free tools for painting, layers, baking and UVs

| Tool | What it does for this look | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Blender Texture Paint (Quick Edit / Apply, stencil, clone) | Paint in UV space or project shot-specific paint-overs from camera | GPL | Built-in; no native layer stack | R | [Source](https://raw.githubusercontent.com/blender/blender/main/scripts/startup/bl_ui/space_view3d_toolbar.py) |
| Ucupaint | Layer and mask stack for EEVEE and Cycles; bakes (AO, curvature, thickness), UDIM | GPL-3 | Active: v2.4.9 supports 2.76–5.2; 5.3 fixes in Sept 2026; PSD layers in paid "Plus" | R | [GitHub](https://github.com/ucupumar/ucupaint) · [Releases](https://github.com/ucupumar/ucupaint/releases) |
| Krita | Painterly brushwork, texture cleanup, painted plates | GPL-3 | Active; 6.0.4.1 on 1 Oct 2026 | R | [Tags](https://github.com/KDE/krita/tags) |
| blender-krita-link-plugin | Edit Blender images in Krita with UV overlay and live update | GPL-3 | "Highly experimental"; Blender 4.2+ install notes; weak on macOS; Krita 6 untested | R | [GitHub](https://github.com/heisenshark/blender-krita-link-plugin) |
| BlenderLayer | Streams the Blender viewport into Krita as a layer for paint-over | GPL-3 | Painting back to 3D is only proof of concept | R | [GitHub](https://github.com/Yuntokon/BlenderLayer) |
| ArmorPaint (armortools) | Standalone 3D PBR texture painter | zlib (source); binaries paid | Active, commits 1 Oct 2026; repo "may not be stable" | R | [GitHub](https://github.com/armory3d/armortools) |
| Material Maker | Node-based procedural textures plus 3D painting (Godot-based) | MIT | Active, about 6k stars | R | [GitHub](https://github.com/RodZill4/material-maker) |
| MyPaint / libmypaint | Tablet painting app and the brush engine other apps use | open source | Repos current | R | [MyPaint](https://github.com/mypaint/mypaint) · [libmypaint](https://github.com/mypaint/libmypaint) |
| GIMP | Flat UV-space painting and cleanup; hosts G'MIC filters | GPL | Current | L | [gimp.org](http://www.gimp.org/) |
| Camera Projection Painter | Clone paint from photos onto photogrammetry meshes (photo-oriented) | GPL-3 | v4.0.0 | R | [GitHub](https://github.com/BlenderHQ/camera_projection_painter) |
| Layer Painter | Substance-like layer workflow inside Blender | GPL-3 | v2.0.1; supported Blender version not stated, possibly stale | R | [GitHub](https://github.com/joshuaKnauber/layer_painter) |
| RyMat | Layered material UI, mesh-map baking, projection decals | GPL-3 | Blender 4.0+; self-described "Unstable" beta | R | [GitHub](https://github.com/LoganFairbairn/RyMat) |
| TexTools | UV tools, texel density and bake modes | Open source (licence type not confirmed) | **Stale**: 1.6.1 (Mar 2024), last commit Dec 2024; unproven 5.x fork exists | R | [GitHub](https://github.com/franMarz/TexTools-Blender) · [5.x fork](https://github.com/hieult0806/TexTools-Blender5) |
| Bake Wrangler | Node-based baking with curvature and cavity | Docs repo GPL-3; free or paid status unverified | Thread mentions b0.9.4 | L / R | [Thread](https://blenderartists.org/t/bake-wrangler-node-based-baking-tool-set-ver-b0-9-4-curvycavity/1187732) · [Docs](https://github.com/netherby/bakewrangler-doc) |
| DreamUV | Viewport UV manipulation | not checked | not checked | L | [GitHub](https://github.com/leukbaars/DreamUV) |
| UV-Packer | Free automatic UV packing | Free | not checked | L | [uv-packer.com](https://www.uv-packer.com/blender/) |
| Texel Density Checker | Consistent texel density across assets | not checked | not checked | L | [GitHub](https://github.com/mrven/Blender-Texel-Density-Checker) |
| Magic UV | UV utilities (formerly bundled with Blender) | not checked | README still lists Blender 2.7x/2.8; 4.2+ status unverified | R | [GitHub](https://github.com/nutti/Magic-UV) |
| Flow Map Painter | Paint flow maps to steer stroke direction in shaders or Geometry Nodes | GPL-3 | **"Deprecated in Blender version 5.0.0"**; refactor in progress | R | [GitHub](https://github.com/ClemensBeute/flow_map_painter) |
| threejs-stylized-paint-shader | Port of Gabriel de Laubier's paint shader: surface-anchored triplanar strokes that foreshorten, broken outlines, eroded shadows | MIT | Reference code to port to Blender | R | [GitHub](https://github.com/SeloSlav/threejs-stylized-paint-shader) |
| Stylized Neural Painting | Generates oil, watercolor or marker stroke parameters from an image | **CC BY-NC-SA 4.0 (non-commercial)** | CVPR 2021 research code | R | [GitHub](https://github.com/jiupinjia/stylized-neural-painting) |
| PyPainterly | Python version of Hertzmann's painterly stroke algorithm, for generating painted source images | not checked | Research code | R | [GitHub](https://github.com/pschaldenbrand/PyPainterly) |

### Free textures and brushes

| Source | What it offers | Licence | Ev. | Link |
|---|---|---|---|---|
| Poly Haven textures | Scanned textures for breakup and noise | CC0 | L | [polyhaven.com/textures](https://polyhaven.com/textures) |
| ambientCG | Hundreds of PBR materials | Public domain | L | [ambientcg.com](https://ambientcg.com/) |
| cgbookcase, ShareTextures, Texture.Ninja, 3DTextures.me, FreePBR | More free PBR and photo textures | Per site | L | [cgbookcase](https://cgbookcase.com/textures/) · [ShareTextures](https://www.sharetextures.com/) · [Texture.Ninja](https://texture.ninja/) · [3DTextures.me](https://3dtextures.me/) · [FreePBR](https://freepbr.com/) |
| AMD MaterialX Library | Free MaterialX materials | Per material | L | [matlib.gpuopen.com](https://matlib.gpuopen.com/main/materials/all) |
| BlenderKit | Assets, materials and alpha brushes | Mixed free and paid | L | [blenderkit.com](https://www.blenderkit.com/) |
| David Revoy's Krita brushes (2025 bundle) | Painterly Krita brush set | CC0 | L | [davidrevoy.com](https://www.davidrevoy.com/article1060/krita-brushes-2025-01-bundle/) |
| krita-brushes (portnov) and mypaint-brushes | Additional brush packs | open source | R | [krita-brushes](https://github.com/portnov/krita-brushes) · [mypaint-brushes](https://github.com/mypaint/mypaint-brushes) |
| CC0 stylized textures | Free stylized texture set | CC0 | L | [BlenderNation](https://www.blendernation.com/2025/11/04/cc0-stylized-textures/) |
| Hand-painted style textures | Small hand-painted texture pack | Per item | L | [OpenGameArt](https://opengameart.org/content/8-handpainted-style-textures) |

### Free tutorials, breakdowns and recreations

| Resource | What you learn | Ev. | Link |
|---|---|---|---|
| Arcane S2 texturing: Animating the hand-painted look | How Season 2 textures were painted and animated | S | [YouTube](https://www.youtube.com/watch?v=gCJIJG6Lz84) |
| A Closer Look at Texturing in Arcane, Parts 1–2 | Production models of Vi, the Firelight leader, Jinx's Fishbones, Caitlyn | S | [Part 1](https://80.lv/articles/a-closer-look-at-texturing-in-arcane) · [Part 2](https://80.lv/articles/a-closer-look-at-texturing-in-arcane-part-2) |
| Fortiche texture artists on ArtStation | Theuillon (Vi, Caitlyn, Silco), Gilles Roman (Singed, Scar), Thibaut Granet (Jinx), Ambre Sedogbo (S2 props) | S | [Vi](https://candicetheuillon.artstation.com/projects/b505vm) · [Caitlyn](https://candicetheuillon.artstation.com/projects/aGy4zz) · [Silco](https://candicetheuillon.artstation.com/projects/X1PKwy) · [Singed](https://www.artstation.com/artwork/AroEYW) · [Jinx](https://www.artstation.com/artwork/4X8vGl) · [S2 props](https://www.artstation.com/artwork/eR3Zdb) |
| Arcane S2 matte-painting breakdowns | Paint projected onto 3D sets | S | [Mathis Richard](https://www.artstation.com/artwork/rle426) · [Naïm Bonnot](https://www.artstation.com/artwork/WXYl8J) |
| Ekko recreated with Substance 3D and Blender | Painterly look with Substance's built-in brushes, rendered in Blender | S | [80.lv](https://80.lv/articles/3d-artist-recreates-arcane-s-ekko-with-substance-3d-blender) |
| Arcane-style game-ready prop, cannon and character | Game-oriented Arcane recreations (label them as such) | S | [Prop](https://80.lv/articles/stylized-3d-prop-with-arcane-like-graphics-created-with-3ds-max-substance-3d-painter) · [Cannon](https://80.lv/articles/creating-a-game-ready-cannon-in-an-arcane-inspired-style) · [Character](https://80.lv/articles/creating-a-game-ready-character-with-an-arcane-aesthetic) |
| Texturing in Blender with Ucupaint | Free written walkthrough of the layer workflow | S | [passivestar.xyz](https://passivestar.xyz/posts/texturing-in-blender-with-ucupaint/) |
| Ucupaint wiki | Official docs and demos | R | [ucupaint-wiki](https://github.com/ucupumar/ucupaint-wiki) |
| Stylized Paint Shader Breakdown (Gabriel de Laubier) | Procedural, surface-anchored brushwork shader design | L | [cyn-prod.com](https://cyn-prod.com/stylized-paint-shader-breakdown) |
| Oil painting effect shader (Dan Livings) | Post-process oil-paint filter, transferable to the Blender compositor | L | [Blog](https://danlivings.co.uk/blog/oil-painting-effect-shader-unity) · [Code](https://github.com/danlivings/oil-painting-effect-shader-unity) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Adobe Substance 3D Painter | Layered 3D painting with smart materials; the commonest tool in Arcane fan recreations (URL from prior knowledge, U) | [adobe.com](https://www.adobe.com/products/substance3d/apps/painter.html) |
| Adobe Substance 3D Designer | Node-based procedural materials and custom stroke generators (U) | [adobe.com](https://www.adobe.com/products/substance3d/apps/designer.html) |
| 3DCoat | Voxel sculpting, retopology, UVs and painting in one package (U) | [3dcoat.com](https://3dcoat.com/) |
| Foundry Mari | Film texture painter for very high-res UDIM work; on Fortiche's tool list (U) | [foundry.com](https://www.foundry.com/products/mari) |
| Procreate | One-time-purchase iPad painting app with 3D model painting (U) | [procreate.com](https://procreate.com/) |
| ArmorPaint binaries | Prebuilt ArmorPaint; buying them funds the zlib-licensed project | [armorpaint.org](https://armorpaint.org/) |
| Painterly Bundle (3 Methods) | Blender painterly shading and texturing bundle; contents unverified | [Superhive](https://superhivemarket.com/products/painterly-bundle-3-methods) |
| Ucupaint Plus | Paid tier adding PSD layer import and export; terms unverified | [Releases](https://github.com/ucupumar/ucupaint/releases) |

## 5. NPR shading, lighting and rendering: Blender 5.3 lighting nodes replace a dead prototype

Blender's NPR story changed in 2026. The **EEVEE NPR prototype**, a separate NPR node tree chosen from the Material Output node, with filter support, custom shading and AOV access, built on Blender 4.4 after the Dillon Goo Studio workshop ([devtalk feedback thread](https://devtalk.blender.org/t/eevee-npr-prototype-feedback/37098), S; [CG Channel](https://www.cgchannel.com/2024/12/check-out-blenders-experimental-non-photorealistic-rendering-build/), S), is **no longer in development**, and its final builds were archived on GitHub ([pragma37/Blender-NPR-Prototype](https://github.com/pragma37/Blender-NPR-Prototype), R). What landed instead is smaller and official: commit c3f2d1f, "EEVEE: Material Lighting Nodes", merged on **2 September 2026** by the prototype's developer, adds **Light Accumulation, Light Info, Light Evaluation and Shadow Raycast** nodes ([commit](https://github.com/blender/blender/commit/c3f2d1f), R). Per the 5.3 release notes they let artists author "how the Material reacts to Lights" for toon and stylized shading ([5.3 EEVEE notes](https://developer.blender.org/docs/release_notes/5.3/eevee/), S), and Shadow Raycast has a Softness control so area lights can still cast sharp shadows ([Material Lighting Nodes feedback](https://devtalk.blender.org/n/material-lighting-nodes-feedback/45695), S). The source code shows two practical details: Light Evaluation has **only an EEVEE (GPU) implementation, with no Cycles path**, and Light Accumulation writes its result into the standard diffuse and glossy compositing passes, so custom toon lighting still feeds the compositor ([Light Evaluation source](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/shader/nodes/node_shader_light_evaluation.cc), R; [Light Accumulation source](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/shader/nodes/node_shader_light_accumulation.cc), R). Blender's main branch reports 5.3 alpha on 2 October 2026, and one aggregator gives a 17 November release date (unverified). Until then, the classic **Shader to RGB into Color Ramp** recipe is still in Blender and works for 4.2–5.2 pipelines ([shader nodes source](https://github.com/blender/blender/tree/main/source/blender/nodes/shader/nodes), R). The other prototype features (NPR node tree, screen-space filters, render-texture sampling) are not in official Blender per the evidence found, so studios that need them today must use a fork or Malt, or move the work into compositing.

Arcane's lighting look is mostly painted rather than computed. A synthesis of the (mostly second-hand) sources gives a stack of **painted albedo carrying value and bevels; two or three graphic lighting layers (base, shadow, rim); hue-shifted rather than darkened shadows; specular painted rather than rendered; edges broken by strokes or abstraction; and a per-shot comp** in which, as a Fortiche compositing clip puts it, each shot is thought of as a painting ([Fortiche compositing short](https://www.youtube.com/watch?v=dn87jqMKxuY), L). Riot's related Worlds 2021 opening, rendered in Arnold, reportedly omitted specularity and painted highlights into diffuse ([Autodesk community blog](https://forums.autodesk.com/t5/community-blog-m-e-english/arnold-s-powerhouse-rendering-for-riot-s-worlds-2021-show-open/ba-p/13901225), L). Mielgo's approach is lighting-first painting: on *The Witness* "we didn't have 3D sets, we had paintings", so lighters matched CG characters to the light source Mielgo described in each painting before he adjusted levels per shot ([befores & afters](https://beforesandafters.com/2019/05/06/director-alberto-mielgo-reveals-all-about-those-crazy-visuals-in-the-witness/), S). In tool terms that means light linking, per-character light rigs, shadow catchers and per-shot curves rather than one magic shader. Gold's approach is Cycles, light linking and brushstroke geometry. The open Blender equivalent of all three is: **painted textures, then EEVEE with Shader to RGB ramps or the new Light Evaluation and Shadow Raycast nodes, light linking for rims and cheats, Brushstroke Tools on silhouettes and large forms, Line Art for selective lines, and the compositor's Kuwahara and grade**.

Beyond stock Blender, the open options carry production risk. **Goo Engine**, Dillon Goo Studios' GPL-3 fork with custom EEVEE shader nodes and light groups, officially remains on Blender 4.4, with builds distributed through Patreon rather than GitHub releases ([goo-engine](https://github.com/dillongoostudios/goo-engine), R). Two unofficial, single-maintainer ports bring Goo's nodes and the prototype's NPR tree, filter materials, screen-space outlines and a bundled Kuwahara group to Blender 5.1 and 5.2 ([bb-yi/blender](https://github.com/bb-yi/blender), R; [NaMgAl-Studio port](https://github.com/NaMgAl-Studio/goo-engine-5.2.0), R), but the NaMgAl README itself recommends the original Goo Engine 4.4 for production. **Malt** is a GLSL-programmable NPR framework (MIT per its README) aimed at TDs; it needs OpenGL 4.5, has no macOS support, and its last code push was in March 2026 ([Malt](https://github.com/bnpr/Malt), R). Outside Blender, the anime-focused shader repos (Unity Toon Shader 3, lilToon, the NiloCat URP example, MooaToon for UE5) teach ramps, SDF face shadows, rim light and outlines that transfer to Blender, but none is painterly by default.

### Built-in Blender building blocks

| Feature | Use for this look | Since / status | Ev. | Link |
|---|---|---|---|---|
| Material Lighting nodes (Light Accumulation, Light Info, Light Evaluation, Shadow Raycast) | Per-light custom toon shading; sharp shadows from area lights; results still land in comp passes | Merged 2 Sept 2026; ships in 5.3; EEVEE only | R / S | [Commit](https://github.com/blender/blender/commit/c3f2d1f) · [5.3 notes](https://developer.blender.org/docs/release_notes/5.3/eevee/) |
| Shader to RGB + Color Ramp | Classic EEVEE toon quantization of lit shading | Present in main | R | [Source](https://github.com/blender/blender/tree/main/source/blender/nodes/shader/nodes) |
| Light linking | Per-object "cheated" lights (hero-only rim, key that ignores the set) | Cycles light linking showcased in Gold (S); EEVEE light-linking code present in main (R); first EEVEE version unverified | R / S | [Gold announcement](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/) |
| Line Art modifier and Freestyle | Selective ink lines | Present in main | R | [Blender mirror](https://github.com/blender/blender) |
| Kuwahara compositor node | Painterly edge-preserving smoothing (see section 8) | Since 4.0 | R | [Source](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/composite/nodes/node_composite_kuwahara.cc) |

### Free NPR forks, frameworks and Blender add-ons

| Tool | What it does | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Brushstroke Tools (Blender Studio) | Gold's procedural 3D brushstroke layers | GPL-3.0 (per third-party docs) | Blender 4.2+; 5.x unverified | S / L | [Extensions](https://extensions.blender.org/add-ons/brushstroke-tools/) |
| Goo Engine | Blender fork with extra EEVEE NPR nodes and light groups | GPL-3 | Official build on Blender 4.4; Patreon downloads; repo push Sept 2026 | R | [GitHub](https://github.com/dillongoostudios/goo-engine) |
| bb-yi/blender | Goo Engine and NPR prototype ported to Blender 5.1/5.2: render textures, filter materials, outlines, For Each Light, Kuwahara group | GPL | Unofficial; last push 28 Sept 2026; 142 stars | R | [GitHub](https://github.com/bb-yi/blender) · [Feature doc](https://raw.githubusercontent.com/bb-yi/blender/main/blender-npr-features-and-usage.md) |
| NaMgAl-Studio goo-engine-5.2.0 | 13 Goo nodes ported to Blender 5.2.1, light groups | GPL | "Experimental, unofficial"; created July 2026 | R | [GitHub](https://github.com/NaMgAl-Studio/goo-engine-5.2.0) |
| Malt | Customizable real-time NPR render framework (GLSL + Python, VSCode hot reload) | MIT per README | OpenGL 4.5, Windows/Linux only; last code push Mar 2026; per-version release tags up to Blender 5.0 | R | [GitHub](https://github.com/bnpr/Malt) |
| Blender NPR Prototype | The discontinued 2024 prototype | GPL | **Archived**, frozen at Blender 4.4 | R | [GitHub](https://github.com/pragma37/Blender-NPR-Prototype) |
| LSCherry | Toon-shader framework evolved from aVersionOfReality's toon shader | GPL-3.0 | Active, Sept 2026 push | R | [GitHub](https://github.com/lvoxx/LSCherry) |
| BNPR shaders collection | EEVEE comics, sketch and toon shaders | per item | not checked | L | [blendernpr.org](https://blendernpr.org/downloads/) |
| Blender-StellarToon | Star Rail-style shader built for Goo Engine (game-asset oriented) | not checked | not checked | R | [GitHub](https://github.com/festivities/Blender-StellarToon) |
| Angora-Shader, cymatics, Blender-Halcyon-Engine | Brushstroke NPR toolkit; NPR shader with a 14-stage comp chain; from-scratch cel/ink/painted-backdrop engine | various | New in 2026, tiny adoption, unproven | R | [Angora](https://github.com/legralltitouan/Angora-Shader) · [cymatics](https://github.com/infinition/cymatics) · [Halcyon](https://github.com/ExtCan/Blender-Halcyon-Engine) |

### Toon and NPR shaders in other engines (techniques transfer)

| Tool | Engine | Licence | Status | Ev. | Link |
|---|---|---|---|---|---|
| Unity Toon Shader (UTS3) | Unity Built-in, URP, HDRP | Unity Companion License | Active, Sept 2026 push | R | [GitHub](https://github.com/Unity-Technologies/com.unity.toonshader) |
| lilToon | Unity | MIT | Active, July 2026 push | R | [GitHub](https://github.com/lilxyzw/lilToon) |
| UnityURPToonLitShaderExample (NiloCat) | Unity URP; short, readable learning shader | MIT | Unity 2021.3 to Unity 6; 7.8k stars | R | [GitHub](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) |
| GenshinCelShaderURP | Unity URP: ramps, SDF face shadows, rim, outlines | MIT | Mar 2025 push | R | [GitHub](https://github.com/Gaolingx/GenshinCelShaderURP) |
| Toon RP | Unity scriptable render pipeline for toon looks | MIT | Aug 2024 push | R | [GitHub](https://github.com/Delt06/toon-rp) |
| MooaToon | UE5 cinematic toon rendering: Lumen GI control, ramps, face shadow maps, outlines | See licence page | Active, Sept 2026 push | R | [GitHub](https://github.com/JasonMa0012/MooaToon) · [Licence](https://mooatoon.com/docs/Licence/) |
| FlexibleToonShaderGD / Godot-ComicShader | Godot toon and comic shaders | MIT / not checked | 2021 / Godot 4.x | R | [Flexible](https://github.com/CaptainProton42/FlexibleToonShaderGD) · [Comic](https://github.com/frankschoeman/Godot-ComicShader) |
| MNPR | Maya Viewport 2.0 watercolor-style stylization framework | MIT | **Unmaintained since 2019**; production successor MNPRX is paid | R | [GitHub](https://github.com/semontesdeoca/MNPR) |

### Free papers, talks and tutorials

| Resource | Why it matters | Ev. | Link |
|---|---|---|---|
| Hertzmann 1998, "Painterly Rendering with Curved Brush Strokes of Multiple Sizes", with original code | The foundational stroke-based painterly algorithm | R (code) / L (paper) | [painterJava (MIT)](https://github.com/hertzmann/painterJava) · [Project page](https://mrl.cs.nyu.edu/publications/painterly98/) |
| Meier 1996, "Painterly rendering for animation" | Particles fixed to surfaces: the idea behind world-space brushstrokes like Gold's | L | [SIGGRAPH history](https://history.siggraph.org/?p=117028) |
| Kyprianidis et al., anisotropic Kuwahara filtering | The algorithm behind Blender's Kuwahara node | R | [gpuakf reference code](https://github.com/jkyprian/gpuakf) |
| Mitchell et al. 2007, "Illustrative Rendering in Team Fortress 2" | Classic warped-diffuse and rim-light NPR | L | [PDF](https://steamcdn-a.akamaihd.net/apps/valve/2007/NPAR07_IllustrativeRenderingInTeamFortress2.pdf) |
| Disney Animation, "Painterly CG Concepts" | Studio notes on painterly CG | L | [PDF](https://media.disneyanimation.com/uploads/production/publication_asset/64/asset/painterlyCgConcepts.pdf) |
| GuiltyGearXrd's Art Style (GDC) and the GGXrdShading WebGL demo | Threshold shading, vertex-color control, inverted-hull outlines | L / R | [Talk](https://www.youtube.com/watch?v=yhGjCzxJV3E) · [Demo repo](https://github.com/galloscript/GGXrdShading) |
| 3D Game Shaders for Beginners (lettier) | Cel shading, rim light, Fresnel, outlining, posterization chapters (code licensed, text not) | R | [GitHub](https://github.com/lettier/3d-game-shaders-for-beginners) |
| Making a NPR Shader in Blender | Blender-specific NPR shader walkthrough | S | [typhomnt.github.io](https://typhomnt.github.io/post/blender_npr/) |
| Light and shadow direction principles (Hoarbound docs) | Painterly lighting rules: hue-shifted shadows, sharp contact shadows, edges at focal points | R | [Document](https://raw.githubusercontent.com/Nolavel/Hoarbound/main/docs/art/LIGHT_AND_SHADOW_DIRECTION.md) |
| Lightning Boy Studio (YouTube) | Free toon and NPR shading for Blender | L | [Channel](https://www.youtube.com/channel/UCd9i2MKimSaKezat1xkn8-A/videos) |
| Fan reverse-engineering of Arcane lighting (base, shadow, rim layers) | Fan speculation, useful as a starting recipe | L | [YouTube](https://www.youtube.com/watch?v=gw6m2W5ja4o) |
| Arcane-style game-ready cannon breakdown | Unlit + PBR + rim + fake front-light terminator shader | L | [80.lv](https://80.lv/articles/creating-a-game-ready-cannon-in-an-arcane-inspired-style) |
| MNPR and real-time watercolor research | Watercolor pigment, substrate and edge effects | L | [MNPR paper page](https://artineering.io/research/MNPR/) |

Spider-Verse and Puss in Boots SIGGRAPH talks, Genshin/miHoYo talks and Blender Conference NPR talks other than Gold's were **not located** in this session.

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Pencil+ 4 Line for Blender (PSOFT) | Production line rendering via a separate render app; Unity, Max and Maya versions exist | [psoft.co.jp](https://psoft.co.jp/en/product/pencil/blender/) |
| MNPRX (Artineering) | Production successor to open MNPR for Maya stylization | [artineering.io](https://artineering.io/projects/MNPRX/) |
| NiloToonURP | Full closed-source NiloCat toon shader, available on request | [README](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) |
| Brushed Shading | Superhive NPR shader; price not verified | [Superhive](https://superhivemarket.com/products/brushedshading) |
| Goo Engine builds | Prebuilt Goo Engine via Dillon Goo Studios' Patreon (source free, GPL-3) | [GitHub](https://github.com/dillongoostudios/goo-engine) |

## 6. Animation and rigging: keyframe from reference, step per shot, rig with CloudRig

All three reference productions are keyframe-first: Arcane Season 1 used no mocap, *The Witness* was "NO Mocap, NO rotoscope", and Jibaro's characters were hand-keyed from dancer reference after mocap was rejected (section 1). Fortiche's Head of Character Animation Alexis Wanneroy, a former DreamWorks Animation supervisor ([80.lv](https://80.lv/articles/a-podcast-with-fortiche-s-lead-animator-on-arcane-s-secret-to-success), S), has published shot breakdowns showing "how references or storyboards shaped the subtext, intent, and posing" ([Wanneroy on X](https://x.com/alwanneroy/status/1878007769204130228), S). The stepped-timing vocabulary comes from *Into the Spider-Verse*, where animation supervisor Josh Beveridge described moving in and out of twos inside a shot ("Sometimes we might have a 60-frame shot with the first 16 on 2s, then a 3-frame hold, then one's") ([AWN](https://www.awn.com/animationworld/creating-stylized-universe-sonys-spider-man-spider-verse), S; which of AWN or VFX Voice carries the quote is unverified), and where "echoey geometry" multiples replaced motion blur ([Todd Vaziri on X](https://twitter.com/tvaziri/status/1080340011256471552?lang=en), S). Stepping is therefore a **per-shot, per-character and even per-moment decision, not a global render setting**. No primary source confirms Arcane's character frame-rate policy, or whether Gold, Jibaro or *The Windshield Wiper* stepped their character animation; Gold's "stepping artifact" production page concerns brushstroke rendering, not timing.

Blender's built-in **Stepped Interpolation F-Curve modifier** fits that philosophy. It samples a curve every N frames, with **Offset** to desynchronize characters and **Start/End frames** to switch between ones and twos inside a shot, and because it is non-destructive animators can block on ones and preview on twos ([Blender 5.2 LTS manual](https://docs.blender.org/manual/en/latest/editors/graph_editor/fcurves/modifiers.html), S). **SMEAR**, a SIGGRAPH 2024 research add-on, generates elongated in-betweens, transparent multiples and motion lines through a Python pre-process and a Geometry Nodes modifier; it is v1.1.5, tested on Blender 4.2 LTS, GPL-3.0-or-later, and its Camera POV option only works on unrigged objects, while multiples need a manual alpha material ([GitHub](https://github.com/MoStyle/SMEAR), R; [Extensions](https://extensions.blender.org/add-ons/smear/), S). Lattice Magic's Camera Lattice handles cheats to camera, and the **Wiggle Bones** fork on the Extensions platform was refactored "to ensure compatibility with Blender 5.0 and newer" for follow-through ([Extensions](https://extensions.blender.org/add-ons/wiggle-bones/), S). **AnimAide**, once the standard free curve toolkit, is no longer developed, and its author warns Blender's new animation system "most likely will break" it ([GitHub](https://github.com/aresdevo/animaide), R).

**CloudRig** is the production-proven free rig generator. Blender Studio built it for its open movies and used it for "all or most of the characters on Sprite Fright, Charge, Wing It, Gold, and other projects"; it installs from the Extensions platform and generates a control rig from a parameterized metarig ([Blender Studio Rigging Tools training](https://studio.blender.org/training/blender-studio-rigging-tools/introduction/), S; [CloudRig docs](https://studio.blender.org/tools/addons/cloudrig/introduction), S). Blender Studio's CC-BY character rigs double as learning material, but some "require exactly Blender 3.6" ([Rex](https://studio.blender.org/characters/rex/v1/), S). A painterly 3D face needs a conventional deformation rig with correctives; a 2D-style face can be built from **Grease Pencil v3** layers (a complete rewrite shipped in Blender 4.3, so older GP face-rig tutorials may not match) ([CG Channel](https://www.cgchannel.com/2024/11/5-key-features-in-blender-4-3/), S) or from mesh cards with frame-swapped mouths, the pattern that Tiny 2D Rig Tools automates ([GitHub](https://github.com/NickTiny/Tiny-2D-Rig-Tools), R).

Free mocap is now practical but best used as blocking or reference. **FreeMoCap** (multi-webcam, AGPL-3.0, about 10.4k stars) shipped v2.0.0-alpha.25 on **24 September 2026** with Blender export options in the GUI, while v1.8.2 is the stable line ([releases](https://github.com/freemocap/freemocap/releases), R). **BlendCap** (GPL-3.0+) captures body, fingers and face from a single video inside Blender 4.2+ and retargets to Rigify, Auto-Rig Pro, CloudRig and Mixamo rigs, but needs an NVIDIA RTX 20 or GTX 16-class GPU with 6 GB+ VRAM, about 32 GB of disk and an 11 GB download ([GitHub](https://github.com/Arcomade/BlendCap), R). Watch the licences: **GVHMR** and pipelines built on it are restricted to "educational, research and non-profit purposes" ([GVHMR licence](https://github.com/zju3dv/GVHMR/blob/main/LICENSE), R), and WHAM's MIT code needs separately registered SMPL body models ([WHAM](https://github.com/yohanshin/WHAM), R). The Mielgo-faithful workflow is to shoot multi-angle reference, optionally capture it, retarget to a CloudRig or Rigify character, then **re-key it**: extract key poses, delete in-betweens, push poses to camera, and apply the Stepped modifier with varied step and offset. That workflow is a synthesis of the sources; no studio documents it.

### Free tools for stepped, smeared and cheated animation

| Tool | What it does for this look | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Stepped Interpolation F-Curve modifier | Per-curve stepping with step size, offset and frame range; non-destructive | GPL (Blender) | Built-in (5.2 LTS manual) | S | [Manual](https://docs.blender.org/manual/en/latest/editors/graph_editor/fcurves/modifiers.html) |
| Constant interpolation | Key every 2 frames with held values | GPL (Blender) | Built-in | S | [Manual](https://docs.blender.org/manual/en/latest/editors/graph_editor/fcurves/properties.html) |
| Stop Motion Style Animator | "Step Frames" on twos or threes without deleting keys; phase offset and stagger between objects | not confirmed (a "Pro" tier exists) | Blender 5.0+ | S | [Extensions](https://extensions.blender.org/add-ons/stop-motion-style-animator/) |
| SMEAR | Elongated in-betweens, multiples and motion lines (SIGGRAPH 2024) | GPL-3.0+ (paper CC-BY 4.0) | v1.1.5, tested on 4.2 LTS; 5.x unverified | R / S | [GitHub](https://github.com/MoStyle/SMEAR) · [Extensions](https://extensions.blender.org/add-ons/smear/) · [Paper](https://dl.acm.org/doi/10.1145/3641519.3657457) |
| Lattice Magic (Camera Lattice) | 2D-style per-shot cheats to camera | not verified | On Extensions; 5.x unverified | S | [Docs](https://studio.blender.org/tools/addons/lattice_magic) |
| Wiggle 2 (original) | Bone jiggle with collisions, pinning and one-click bake | GPL-3.0 | About 1k stars, 66 open issues; Blender versions not stated | R | [GitHub](https://github.com/shteeve3d/blender-wiggle-2) |
| Wiggle Bones (maintained fork) | Same idea, refactored for Blender 5.0+ | not checked (fork of GPL-3.0 code) | Maintained | S | [Extensions](https://extensions.blender.org/add-ons/wiggle-bones/) |
| Wiggle 2: RTX Edition / EXea Jiggle | Community-maintained jiggle alternatives | not checked | On Extensions | S | [Wiggle 2 RTX](https://extensions.blender.org/add-ons/wiggle-2/) · [EXea Jiggle](https://extensions.blender.org/add-ons/exea-jiggle/) |
| Copy Global Transform | Copy and paste world-space transforms for pose cheats | GPL (Blender) | Moved into Blender core in 5.0 (scripts enabling the old add-on break) | S | [5.0 notes](https://developer.blender.org/docs/release_notes/5.0/animation_rigging/) |
| AnimAide | Curve tools, offset propagation, key manager | not confirmed | **"Development no longer active"**; expected to break on the new animation system | R | [GitHub](https://github.com/aresdevo/animaide) |

### Free rigs and rigging systems

| Tool | What it does | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| CloudRig (Blender Studio) | Metarig-based rig generator used on Sprite Fright, Charge, Wing It! and Gold | not verified (GPL expected) | On Extensions; free training videos and livestreams | S | [Docs](https://studio.blender.org/tools/addons/cloudrig/introduction) · [Training](https://studio.blender.org/training/blender-studio-rigging-tools/) · [Source](https://projects.blender.org/Mets/CloudRig) |
| Rigify | Blender's bundled auto-rigger | GPL | Bundled; original GitHub repo archived | R | [Old repo](https://github.com/cessen/rigify) · [Rigify vs ARP](https://cgdive.com/rigify-vs-auto-rig-pro-auto-rigging-comparison/) |
| GameRig | Rigify-based, game-engine-friendly rigs | Open source, personal and commercial use | not checked | R | [GitHub](https://github.com/Arminando/GameRig) |
| ActionPoser / BoneWidget / mets_tools | Action-based correctives; custom bone shapes; production rigging utilities | various | not checked | R | [ActionPoser](https://github.com/Arminando/ActionPoser) · [BoneWidget](https://github.com/BlenderDefender/BoneWidget) · [mets_tools](https://github.com/Mets3D/mets_tools) |
| Blender Studio character rigs (Rex, Elder Sprite, Ellie, Sprite, Wing It! chicken) | Production rigs to study and reuse with credit | CC-BY | Some require exactly Blender 3.6 | S | [Rex](https://studio.blender.org/characters/rex/v1/) · [Ellie](https://studio.blender.org/characters/ellie/v1/) · [Sprite Fright cast](https://studio.blender.org/projects/sprite-fright/characters/) |
| Tiny 2D Rig Tools | Cut-out Grease Pencil rigs with time-offset mouths and hands | not stated | 22 stars | R | [GitHub](https://github.com/NickTiny/Tiny-2D-Rig-Tools) |
| gomez_poser | Auto-rig and skin Grease Pencil strokes | not checked | Small; last updated 2025 | R | [GitHub](https://github.com/dzigaVertov/gomez_poser) |
| Free 2D face rig | Mesh-based 2D face rig | CC0 | not checked | S | [BlendSwap](https://blendswap.com/blend/31464) |
| Pose Library | Asset-based pose library on the asset shelf (click to apply, drag to blend) | GPL (Blender) | Built-in; 5.0 removed legacy pose-library conversion | S | [Manual](https://docs.blender.org/manual/en/latest/animation/armatures/posing/editing/pose_library.html) |

### Free mocap and retargeting (use as reference, then re-key)

| Tool | What it does | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| FreeMoCap + Blender add-on | Multi-webcam markerless capture with Blender export | AGPL-3.0 (output data is yours) | Very active: v2.0.0-alpha.25 (24 Sept 2026); stable 1.8.2 | R | [GitHub](https://github.com/freemocap/freemocap) · [Blender add-on](https://github.com/freemocap/freemocap_blender_addon) |
| BlendCap | Single-video body, hands and face in Blender with cleanup and retargeting | GPL-3.0+ (includes AGPL YOLO11) | New (Mar 2026); Blender 4.2+; needs RTX-class GPU | R | [GitHub](https://github.com/Arcomade/BlendCap) |
| NyuyenMocap-Oyen | MediaPipe capture in Blender 4.2+, a fork of BlendArMocap | GPLv3 | Small (22 commits) | R | [GitHub](https://github.com/sadikinbancin/NyuyenMocap-Oyen) |
| BlendArMocap | Original MediaPipe-to-Rigify add-on | GPL-3.0 | **Discontinued** | R | [GitHub](https://github.com/cgtinker/BlendArMocap) |
| WHAM | World-grounded video-to-SMPL motion | MIT code; SMPL models need separate registration | Research code | R | [GitHub](https://github.com/yohanshin/WHAM) |
| GVHMR | World-grounded motion from video | **Research, education and non-profit only** | Research code; wrappers inherit the restriction | R | [Licence](https://github.com/zju3dv/GVHMR/blob/main/LICENSE) |
| Expy Kit | Convert and rename between Rigify, Mixamo and UE rigs; bake utilities | not stated | 438 stars | R | [GitHub](https://github.com/pKrime/Expy-Kit) |
| Rokoko Studio Live for Blender | Live streaming and retargeting of body, face and fingers | LGPL-3.0 | Blender 2.80+ | R | [GitHub](https://github.com/Rokoko/rokoko-studio-live-blender) |

### Free talks, articles and training

| Resource | What you learn | Ev. | Link |
|---|---|---|---|
| The Making of Arcane (Wanneroy interview) and iAnimate podcast | Keyframe-only animation from live-action reference, real-time rigs | S | [SyncSketch](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) · [iAnimate](https://ianimate.net/animationpodcast/arcane-magic-secrets-fortiche-lead-alexis-wanneroy-podcast) |
| Wanneroy's Season 1 shot breakdowns | Reference, subtext and posing | S | [X thread](https://x.com/alwanneroy/status/1878007769204130228) · [Reel](https://vimeo.com/1046434045) |
| "No motion capture, no problem" (Jinx animation) | Official note on Arcane's keyframe approach | S | [Arcane on X](https://x.com/arcaneshow/status/1564401767772991488) |
| Spider-Verse animation coverage | Fluid stepping, smears capped at one or two frames, multiples instead of blur | S | [AWN](https://www.awn.com/animationworld/creating-stylized-universe-sonys-spider-man-spider-verse) · [VFX Voice](https://vfxvoice.com/imageworks-artists-break-the-mold-to-create-an-alternate-spider-verse/) · [Cartoon Brew](https://www.cartoonbrew.com/feature-film/if-its-not-broke-break-it-sony-imageworks-renegade-approach-to-spider-man-into-the-spider-verse-167321.html) · [fxguide](https://www.fxguide.com/fxfeatured/why-spider-verse-has-the-most-inventive-visuals-youll-see-this-year/) |
| SMEAR project page and supplemental PDF | How the smear and multiples add-on works | S | [Project page](https://mostyle.github.io/blog/sig2024/) · [Supplemental](https://hal.science/hal-04576817v1/file/SMEAR%20-%20Stylized%20Motion%20Exaggeration%20with%20ARt-direction%20-%20Supplemental%20Material.pdf) |
| Blender Studio Rigging Tools (CloudRig series) | Free rigging videos and livestreams (2021 Snow, 2024 Mikassa) | S | [Training](https://studio.blender.org/training/blender-studio-rigging-tools/) |
| 2D face rig tutorials | Mesh-card face rig; Grease Pencil face rig with Rigify (pre-4.3 GP; check against GPv3) | S | [BlenderNation](https://www.blendernation.com/2020/03/28/create-a-2d-face-rig-for-characters-in-blender-no-textures/) · [YouTube](https://www.youtube.com/watch?v=4Cou-yVwF6o) |
| Official Making of Jibaro clip; Jibaro animation vs real-life reference | Reference-driven keyframing | S | [YouTube](https://www.youtube.com/watch?v=R4fkHC0-Pyw) · [80.lv](https://80.lv/articles/jibaro-animations-vs-real-life-references) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Auto-Rig Pro | Rigging, Smart auto-placement and Remap retargeting; about $25 Lite / $50 Full, Blender 2.93–5.2 per summary | [Superhive](https://superhivemarket.com/products/auto-rig-pro) |
| Animation Layers (Tal Hershkovich) | Layered keyframe and mocap editing; v2.4.1, Blender 4.2–5.1 reported | [Superhive](https://superhivemarket.com/products/animation-layers) |
| AnimBot | Maya animator toolset (successor to free aTools); about $60/year entry tier, unverified | [animbot.ca](https://animbot.ca/home/) |
| Autodesk Maya | Fortiche-style keyframe pipeline standard; 2026.1 added MotionMaker | [CG Channel](https://www.cgchannel.com/2025/06/autodesk-adds-ai-animation-tool-motionmaker-to-maya-2026-1/) |
| Cascadeur | Physics-assisted posing and in-betweening; free tier reportedly non-commercial with conflicting export limits | [Plans](https://cascadeur.com/plans) |
| Rokoko Vision | AI video mocap; free tier about 30 s/month, Basic about $10/month billed annually | [Pricing](https://www.rokoko.com/pricing) |
| Blender Studio subscription | Animation Fundamentals course (about 7.5 h, bouncing ball to acting) plus production rigs and files | [Course](https://studio.blender.org/training/animation-fundamentals/) |
| Coloso: Alexis Wanneroy, "Mastering Body Mechanics" | Course by Arcane's Head of Character Animation | [Coloso](https://coloso.global/en/products/characteranimator-alexiswanneroy2-us) |
| Bloop Animation / P2Design / Learn Blender | Blender animation courses; prices not verified | [Bloop](https://www.bloopanimation.com/blender-animation/) · [P2Design](https://www.p2design-academy.com/p/alive-animation-course-in-blender) · [Learn Blender](https://learn-blender.org/courses) |
| Smudge Pencil / Smearify | Geometry Nodes smear-frame setups on Gumroad (Smudge Pencil builds on Brushstroke Tools, Blender 4.3+); prices not confirmed | [Smudge Pencil](https://sanderjoon.gumroad.com/l/smudgepencil) · [Smearify](https://andykxyz.gumroad.com/l/Smearify) |
| Grease Pencil 2D Morphs | Interpolated frames and rig controls that fake shape keys for 2D eyes and mouths | [Gumroad](https://mattthoresen.gumroad.com/l/GP2DMorphs) |

## 7. VFX: draw on twos over locked 3D, or simulate and repaint

Arcane had a named, award-winning FX unit. The episode "Oil and Water" won the 2022 Annie for Best FX, credited to Guillaume Degroote, Aurélien Ressencourt, Martin Touzé, Frédéric Macé and Jérôme Dupré ([Cartoon Brew](https://www.cartoonbrew.com/awards/arcane-mitchells-vs-the-machines-dominate-the-annie-awards-analysis-full-winners-list-214196.html), S), and Season 2 took Best FX among its seven 2025 Annies ([Fortiche blog](https://forticheprod.com/blog/highlights/arcane-alongside-riot-games-french-animation-studio-fortiche-production-triumphs-at-the-2025-annie-awards/), S). The workflow was downstream of animation: 2D animators drew FX over finished 3D, reportedly "animated in Harmony on the renders which were then composited together" ([VFX Apprentice](https://www.vfxapprentice.com/blog/2d-fx-artist-netflix-arcane-league-of-legends), S), with smoke and fire treated as 2D ([VFX Voice](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/), S). For Season 2, Pascal Charrue and Alexis Wanneroy described "a more hybrid technique for FX that combines 2D and 3D elements" ([3DVF on VIEW Conference](https://3dvf.com/en/fortiche-production-shares-the-secrets-behind-arcane-season-2-at-view-conference/), S). Sony's Spider-Verse FX department went a similar way, with "a reusable library of 2D hand-drawn FX elements often animated on twos" mixed with 3D sims ([VFX Voice](https://vfxvoice.com/the-return-of-hand-drawn-and-stylized-effects-animation/), S). Mielgo goes the other way where physics matters: Jibaro's water and its splashes against armor and jewelry were 3D simulations, with separate textures for light above and below the surface, stylized afterwards through texturing and post ([IndieWire](https://www.indiewire.com/features/general/love-death-robots-season-3-jibaro-animation-netflix-1234726800/), S). Gold has no 2D-FX pipeline; its content list includes Geometry Nodes "particle emission from cracks" and "motion trail" particle FX, and its "-fx" shot files "contain simulation or setups to generate various effects" ([Gold production logs](https://studio.blender.org/projects/gold/production-logs/), S; [example shot file](https://studio.blender.org/projects/gold/3d823d3a8c9db8/?asset=7530), S). A Fortiche FX artist never confirmed Harmony, camera-projected FX cards or FX frame rates in anything this research could read.

**Grease Pencil v3** is the strongest free option for FX that live inside the 3D scene and camera. Blender 4.3 rewrote it with layer groups, Geometry Nodes access and much smaller files, though files saved in 4.3+ do not open in older versions ([4.3 Grease Pencil notes](https://developer.blender.org/docs/release_notes/4.3/grease_pencil/), S), and Blender 5.0 added **motion blur for Grease Pencil**, which helps drawn FX sit next to motion-blurred renders ([5.0 Grease Pencil notes](https://developer.blender.org/docs/release_notes/5.0/grease_pencil/), S). For drawing over rendered plates in a dedicated 2D package, **OpenToonz** (Modified BSD, "may be freely used or modified for business or personal purposes"; v1.8 adds FX such as "Smoother Fx Iwa" and draggable corner-pin cages) and its actively patched fork **Tahoma2D** are the closest free equivalents to Harmony's node FX ([OpenToonz](https://github.com/opentoonz/opentoonz), R; [releases](https://github.com/opentoonz/opentoonz/releases), R, year of v1.8 unconfirmed; [Tahoma2D releases](https://github.com/tahoma2d/tahoma2d/releases), R), while Krita 6 handles raster "paint the FX" work. The integration recipe is to lock and render the 3D; draw FX either as camera-parented or world-space Grease Pencil objects, or over the plate in OpenToonz or Krita and export PNG sequences with alpha; bring sequences back as cards or comp layers; and hold drawings on twos or threes through keyframe spacing. Glow and tone must come from the compositor, because Grease Pencil has no per-drawing FX nodes like Harmony's.

Free stylized 3D FX tooling is scattered. GitHub searches for stylized fire, toon smoke and explosion add-ons returned **no established repo**; the only hits were brand-new, unlicensed projects such as SVFXT ([GitHub](https://github.com/KomikusAdha/SVFXT-Simple-Visual-Effects-Toon---Simple-Toon-VFX-for-Blender), R), because such node groups mostly circulate on Gumroad, Superhive and YouTube, which could not be searched. The practical stack is Simulation Zones in Geometry Nodes for particles and trails (as Gold did), hand-drawn sprite cards or Grease Pencil strokes instanced on particles, toon-ramped mesh smoke instead of volumetrics, and Mantaflow or FLIP Fluids splashes re-shaded for Jibaro-style "simulate then paint". Realtime-VFX practice transfers to film: flipbook cards, channel-packed atlases and reusable element libraries let one hand-drawn element serve many shots. On the Houdini side, **SideFX Labs** is "a free, open-source, and artist-friendly toolset" with hundreds of HDAs ([SideFXLabs](https://github.com/sideeffects/SideFXLabs), R).

### Free tools for 2D FX over 3D

| Tool | What it does for this look | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Grease Pencil v3 | Drawn FX in the 3D scene with depth, layers, Geometry Nodes and (5.0+) motion blur | GPL (Blender) | Built-in since 4.3 | S | [4.3 notes](https://developer.blender.org/docs/release_notes/4.3/grease_pencil/) · [5.0 notes](https://developer.blender.org/docs/release_notes/5.0/grease_pencil/) |
| Greasepencil Tools (Pullusb) | Box deform, canvas rotation, timeline scrub, layer navigator, brush-pack import | GPL-3 | Bundled 2.91–4.1, now on Extensions; updated 2026 | R | [GitHub](https://github.com/Pullusb/greasepencil_tools) |
| GP_onion_peel / GP_clipboard / GP-Tool-Wheel | Custom onion skins; world-space stroke copy and paste; quick tool switching | not checked | Updated Sept 2026 | R | [Onion peel](https://github.com/Pullusb/GP_onion_peel) · [Clipboard](https://github.com/Pullusb/GP_clipboard) · [Tool wheel](https://github.com/SietseB/GP-Tool-Wheel) |
| Blender-SakugaGP | Grease Pencil add-on "made by 2D Animator for 2D Animators" | GPL-3 | Created Dec 2025; features not retrieved | R | [GitHub](https://github.com/spikysaurus/Blender-SakugaGP) |
| RenderGPKeyframes | Renders only Grease Pencil keyframes, so FX held on twos or threes export without duplicates | not checked | not checked | R | [GitHub](https://github.com/okuma10/RenderGPKeyframes) |
| Blender-BIS2GP | Batch image sequence to Grease Pencil (bring Krita or OpenToonz FX into GP) | not checked | not checked | R | [GitHub](https://github.com/mercuriousreign/Blender-BIS2GP) |
| Tesselate_texture_plane | Triangulates textured planes and drops alpha areas, for tight FX cards | not checked | not checked | R | [GitHub](https://github.com/Pullusb/Tesselate_texture_plane) |
| OpenToonz | 2D animation with node FX for drawing over plates | Modified BSD (commercial use allowed) | v1.8 stable (year unconfirmed); nightly builds to Oct 2026 | R | [GitHub](https://github.com/opentoonz/opentoonz) · [Releases](https://github.com/opentoonz/opentoonz/releases) |
| Tahoma2D | OpenToonz fork with friendlier UX | open source (OpenToonz-derived) | Active: 1.6.x fix releases, nightly 24 Sept 2026 | R | [Releases](https://github.com/tahoma2d/tahoma2d/releases) |
| Krita | Raster frame-by-frame FX; animation playback reworked on MLT in 5.3/6.0 | GPL-3 | Active | R / S | [Tags](https://github.com/KDE/krita/tags) · [Release notes](https://krita.org/en/release-notes/krita-5-3-release-notes/) |
| Pencil2D | Simple frame-by-frame 2D | open source | v0.7.2 (13 Mar 2026); minimal compositing | S | [Release](https://www.pencil2d.org/2026/03/pencil2d-0.7.2-release.html) |
| Synfig | Vector and tween animation; weak fit for frame-by-frame FX | open source | 1.4.5 is listed as stable while 1.5.5 is tagged "Latest"; check before choosing | R / S | [Releases](https://github.com/synfig/synfig/releases) |

### Free tools for stylized 3D FX and flipbooks

| Tool | What it does | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Geometry Nodes Simulation Zones | Particles, trails and emission from cracks, as on Gold | GPL (Blender) | Built-in | S | [Gold logs](https://studio.blender.org/projects/gold/production-logs/) |
| Brushstroke Tools | Painterly strokes on FX meshes as well as sets | GPL-3.0 (per third-party docs) | Blender 4.2+ | S / L | [Extensions](https://extensions.blender.org/add-ons/brushstroke-tools/) |
| RainGeneratorBlend | Geometry Nodes group that spawns rain for Mantaflow or FLIP | CC BY 4.0 | 2022; version not stated | R | [GitHub](https://github.com/NHodgesVFX/RainGeneratorBlend) |
| Molecular Script | Granular and sticky particle collisions | not shown | README mentions 3.1/3.2; 4.x/5.x unverified | R | [GitHub](https://github.com/scorpion81/Blender-Molecular-Script) |
| SVFXT, Blender-Lightning-Generator | One-click toon impacts, energy balls, beams; lightning | not stated | New (2026), 0 stars, unvetted | R | [SVFXT](https://github.com/KomikusAdha/SVFXT-Simple-Visual-Effects-Toon---Simple-Toon-VFX-for-Blender) · [Lightning](https://github.com/VAST-FRAME/Blender-Lightning-Generator) |
| blender-spritesheets | Render animations to sprite sheets plus JSON | MIT | Developed on Blender 2.81; 4.x/5.x unverified | R | [GitHub](https://github.com/theloneplant/blender-spritesheets) |
| blender-texture-atlas-generator / Spritify | Build flipbook atlases from image sequences | not checked | Updated 2025–2026 | R | [Atlas generator](https://github.com/JackTheFoxOtter/blender-texture-atlas-generator) · [Spritify](https://github.com/FreezingMoon/Spritify) |
| flipbook-packer | Pack sequences into atlases or channel-packed flipbooks (up to 256 frames across RGBA) | MIT | Python 3.12 + Pillow | R | [GitHub](https://github.com/stylerhall/flipbook-packer) |
| SideFX Labs | Hundreds of free Houdini HDAs and game or VFX tools | open source | Active | R | [GitHub](https://github.com/sideeffects/SideFXLabs) · [Examples](https://github.com/sideeffects/SideFXLabsExamples) |

### Free FX assets and learning

| Resource | What you get | Licence / note | Ev. | Link |
|---|---|---|---|---|
| Kenney Particle Pack | PNG and vector particle sprites for prototyping FX cards | CC0 | L | [kenney.nl](https://kenney.nl/assets/particle-pack) |
| Brackeys VFX Bundle | Multi-author particle textures and flipbooks | "Approximately CC0"; check in-pack notices | L | [itch.io](https://brackeysgames.itch.io/brackeys-vfx-bundle) |
| OpenGameArt | Particle, slash and VFX sprites | Mixed, per item | L | [opengameart.org](https://opengameart.org/) |
| VFX Apprentice free training and free 2D FX assets | Free FX lessons, a free 5-part Harmony intro, and an email-gated 2D FX asset pack (licence unverified) | Free | S | [Free training](https://www.vfxapprentice.com/free-vfx-training) · [Harmony intro](https://www.vfxapprentice.com/blog/intro-toon-boom-harmony-animation) · [Assets](https://www.vfxapprentice.com/opt-in-2DFX-Assets) |
| Sakuga-Extended / sakugaEnhancer | Browser extensions with frame stepping for counting twos and threes in FX cuts | open source | R | [Sakuga-Extended](https://github.com/ftLoic/Sakuga-Extended) · [sakugaEnhancer](https://github.com/Punyesh/sakugaEnhancer) |
| Arcane 2DFX showcase and Ressencourt portfolio | Frame-by-frame study of Arcane's 2D FX (reference only) | Reference | S | [Showcase](https://art-of-arcane.tumblr.com/post/677028964611571712/arcane-various-2dfx-showcase-twitter-gilad) · [ArtStation](https://aurelien_ressencourt.artstation.com/projects) |
| Gold "-fx" shot files and production logs | Real Simulation Nodes FX setups (some content may be subscription-gated) | Blender Studio terms | S | [Logs](https://studio.blender.org/projects/gold/production-logs/) |
| Recreating a Jibaro scene in Houdini and Arnold | FLIP water, collision-VDB splashes as a separate layer | Article | S | [80.lv](https://80.lv/articles/recreating-a-scene-from-ldr-s-jibaro-in-houdini-and-arnold) |
| OpenToonz sample files | Example scenes | open source | L | [GitHub](https://github.com/opentoonz/opentoonz_sample) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Toon Boom Harmony | Industry 2D package with node FX; the tool reportedly used for Arcane's 2D FX (URL from prior knowledge, U) | [toonboom.com](https://www.toonboom.com/) |
| TVPaint Animation | Bitmap frame-by-frame 2D software popular for hand-drawn FX (U) | [tvpaint.com](https://www.tvpaint.com/) |
| EmberGen (JangaFX) | Real-time GPU fire, smoke and explosions with VDB and flipbook export (U) | [jangafx.com](https://jangafx.com/) |
| Houdini Apprentice / Indie | Apprentice is free but non-commercial; Indie is the low-cost commercial tier (limits unverified, U) | [sidefx.com](https://www.sidefx.com/) |
| FLIP Fluids | Blender liquid add-on, Blender 4.5–5.2; GPL/MIT source, sold on Superhive with a free demo | [GitHub](https://github.com/rlguy/Blender-FLIP-Fluids) |
| TFlow | Motion-vector frame blending for smooth flipbooks (Unity, UE) | [GitHub](https://github.com/Tuatara-VFX/TFlow) |
| VFX Apprentice courses | Tradigital 2D FX, FX Design Principles, Harmony and more | [Tradigital 2D FX](https://www.vfxapprentice.com/tradigital-2d-fx) · [FX Design Principles](https://www.vfxapprentice.com/courses/fx-design-principles) |

## 8. Compositing and color finish the painting rather than create it

Compositing integrates and finishes the painted look; it does not create it. Fortiche's compositing department produced Arcane's final images, with Nuke named by secondary sources only, and press reports "2D paint-overs and lighting tweaks" as fixes when production hit roadblocks ([RedShark News](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline), S). Mielgo finishes in After Effects with exposure and level work, and Gold extended Blender's viewport compositor alongside its brushstroke geometry ([Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools), S). Mielgo's habit of playing with levels until a shot overexposes like a real camera suggests that bloom, halation and highlight roll-off are central to his look, which maps onto Blender's Glare node and a highlight-roll-off grade (an inference).

The **Blender compositor** is the strongest free finishing tool as of 5.2 LTS, and its source code confirms the details. The **Kuwahara node** (since 4.0) offers Classic and Anisotropic modes and reads **Size per pixel**, so a depth pass, Cryptomatte mask or SDF can vary abstraction across the frame, keeping detail where it matters and paint elsewhere ([Kuwahara source](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/composite/nodes/node_composite_kuwahara.cc), R). GPU execution for final-render compositing arrived in 4.2 ([rna_scene.cc](https://raw.githubusercontent.com/blender/blender/blender-v5.2-release/source/blender/makesrna/intern/rna_scene.cc), R). Glare covers Bloom, Fog Glow, Streaks and Sun Beams (merged into Glare in 5.0) with tint and saturation controls ([Glare source](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/composite/nodes/node_composite_glare.cc), R); the Filter node's Sobel, Prewitt, Kirsch and Laplace modes make ink lines from depth or normal passes ([Filter source](https://raw.githubusercontent.com/blender/blender/blender-v5.2-release/source/blender/nodes/composite/nodes/node_composite_filter.cc), R); Lens Distortion has a Dispersion input for chromatic aberration; and Light Groups and Cryptomatte passes isolate objects and lights. Blender 5.0 made the compositing node tree a reusable data-block with an asset shelf and a **Convert to Display** node, but it also **removed or replaced several compositor nodes** (Composite became Group Output; the compositor's own Math, Mix RGB, Map Range, Value and Texture nodes were removed), so node packs built before 5.0 can break ([5.0 migration guide](https://developer.blender.org/docs/release_notes/5.0/migration/compositor_migration/), S; [5.2 CMakeLists](https://raw.githubusercontent.com/blender/blender/blender-v5.2-release/source/blender/nodes/composite/CMakeLists.txt), R). Blender 5.1 added **Mask to SDF** for edge glows and erode effects, and 5.2 LTS added Blank Image and String to Image nodes and compositor node trees in the VSE ([CG Channel on 5.2](https://www.cgchannel.com/2026/07/blender-5-2-lts-is-here-discover-its-5-key-features/), S).

Temporal stability decides which filter to trust in motion. **World-space strokes (Gold) stay locked to surfaces. Image-space edge-preserving filters** (Kuwahara, Posterize) avoid texture-lock but shimmer wherever noise or sub-pixel detail changes between frames, so denoise first, enable High Precision and keep Size modest. **Patch-propagation tools in the EbSynth family** look the most hand-painted but drift and flicker between keyframes, and **per-frame neural style transfer** flickers worst. This ranking is reasoned from the tools' documented behaviour, not benchmarked. The EbSynth core is public domain ([jamriska/ebsynth](https://github.com/jamriska/ebsynth), R), and the MIT-licensed **ReEzSynth** rewrite adds temporal propagation and sparse feature guiding explicitly to reduce flicker and sliding ([ReEzSynth](https://github.com/FuouM/ReEzSynth), R). Static paper or canvas overlays create a "shower-door" effect, so boil them on twos or project paper in the shader instead. Outside Blender, **G'MIC** (CeCILL; Brushify, Painting, Ink Wash, Canvas and Paper Texture, Add Grain and more) runs inside GIMP and Krita ([GreycLab/gmic](https://github.com/GreycLab/gmic), R), while the official **Natron** has had no release after 2.5.0 and is "looking for developers and maintainers" ([Natron README](https://raw.githubusercontent.com/NatronGitHub/Natron/master/README.md), R).

Color management is a stylistic choice in NPR. Blender 5.x ships one OCIO v2 config with **Standard, AgX, Khronos PBR Neutral, Filmic, ACES 1.3 and ACES 2.0** views, and new scenes default to **AgX** ([5.2 config.ocio](https://raw.githubusercontent.com/blender/blender/blender-v5.2-release/release/datafiles/colormanagement/config.ocio), R; [versioning_defaults.cc](https://raw.githubusercontent.com/blender/blender/blender-v5.2-release/source/blender/blenloader/intern/versioning_defaults.cc), R). **Standard** applies "only the display's standard transform without additional mappings", so painted albedo colors land on screen unchanged; that makes it the right default for flat, hand-painted Arcane-like looks, and Blender's own 2D Animation template uses it. **AgX** or ACES 2.0 suit painterly-but-lit shots with hot practicals and sunsets (Mielgo-style overexposure), at the cost of desaturating bright highlights. The config also defines an "AgX Base sRGB" inverse space usable "to convert backplates or matte paintings to the working space", which matters when bringing painted plates into a scene-linear comp ([main config.ocio](https://raw.githubusercontent.com/blender/blender/main/release/datafiles/colormanagement/config.ocio), R), and a Resolve DCTL port of Blender's AgX lets the final grade match outside Blender ([Blender-AgX-Resolve](https://github.com/EaryChow/Blender-AgX-Resolve), R). Which view transform Arcane or Gold used is not documented in any source found.

### Technique-to-tool map for a painterly finishing pass

| Technique | Blender compositor (5.2 LTS, node names verified in source) | Other free route |
|---|---|---|
| Painterly smoothing | Kuwahara, Anisotropic, with Size driven by depth or a mask | G'MIC Painting, Brushify or Kuwahara; openfx-arena Oilpaint |
| Ink lines and edges | Filter (Sobel, Prewitt, Kirsch, Laplace) on depth, normal or Cryptomatte; Mask to SDF for line width and glow | G'MIC Sketch or Ink Wash; openfx-arena Edges |
| Paper or canvas overlay | Image node + Mix (Overlay or Multiply); Convolve | G'MIC Canvas or Paper Texture |
| Grain | Bundled 5.0 assets (unverified) or a noise node group | G'MIC Add Grain; Saffron Film Grain |
| Bloom and halation | Glare: Bloom, Fog Glow (Tint, Saturation) | Saffron Halation |
| Chromatic aberration | Lens Distortion, Dispersion | — |
| Flat color bands | Posterize (Steps) | G'MIC Posterize |
| Depth atmosphere and DOF | Mist or depth pass + Mix; Defocus or Bokeh Blur | — |
| Layer and light isolation | Cryptomatte, Light Groups, ID Mask | Natron fork with Cycles light-group AOVs |

### Free compositing tools and node packs

| Tool | What it does | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Blender compositor | Kuwahara, Glare, Filter, Posterize, Lens Distortion, Mask to SDF, Cryptomatte, Light Groups, Convert to Display | GPL | Built-in; GPU final comp since 4.2; node changes in 5.0 | R | [Kuwahara source](https://raw.githubusercontent.com/blender/blender/main/source/blender/nodes/composite/nodes/node_composite_kuwahara.cc) · [5.0 notes](https://developer.blender.org/docs/release_notes/5.0/compositor/) |
| MP_Comp | 100+ procedural compositor effects built from native nodes, as an asset library | CC0-1.0 | v3.0.0+ requires Blender 5.0+ | R | [GitHub](https://github.com/MomoPTFL/mp_comp) · [Docs](https://moportfolio.de/mp_comp-documentation/) |
| Saffron | Oklab grading, halation, film grain, vignette, dehaze, view transforms (flim, Khronos, ACES) as node groups | AGPL-3.0 | Runs in the viewport compositor; minimum Blender version not stated | R | [GitHub](https://github.com/bean-mhm/Saffron) |
| Cymatics | NPR shader plus a 14-stage comp chain: anisotropic Kuwahara, depth/normal outlines, palette remap, grain, canvas weave | GPL-3.0 | Blender 5.0+, tested on 5.2 LTS; created Aug 2026, experimental | R | [GitHub](https://github.com/infinition/cymatics) |
| Blender-Compositor-Extra-Nodes | Studio utility node groups with a tutorial playlist | MIT | Version compatibility undocumented | R | [GitHub](https://github.com/cgvirus/Blender-Compositor-Extra-Nodes) |
| Optical Flare Node | Lens-flare node group | GPL-3.0 | Old (2017); 5.x unverified | R | [GitHub](https://github.com/cgvirus/Optical-Flare-Node-For-Blender-Compositor) |
| G'MIC + G'MIC-Qt | Richest free painterly filter set (Brushify, Painting, Ink Wash, Canvas and Paper Texture, Add Grain) for GIMP, Krita and the CLI | CeCILL (core); GPL-3.0 (Qt plug-in) | Active (4.0.6 on master) | R | [G'MIC](https://github.com/GreycLab/gmic) · [G'MIC-Qt](https://github.com/c-koi/gmic-qt) |
| Natron (official) | Node compositor | GPL-2.0 | **No release after 2.5.0; seeking maintainers** | R | [GitHub](https://github.com/NatronGitHub/Natron) |
| Natron fork (Niik-l) | Qt6 "Natron 2.6" builds with Cycles-as-a-node, light-group AOVs, deep comp, ACES 2.0 | GPL-2.0 | Windows and Linux builds Sept 2026; author says "100% vibe coded… expect rough edges" | R | [GitHub](https://github.com/Niik-l/Natron) |
| openfx-misc / openfx-arena | OFX plugin sets; arena adds Oilpaint, Charcoal, Sketch, Edges, Texture, ReadKrita | GPL-2.0 | Natron and other OFX hosts | R | [openfx-misc](https://github.com/NatronGitHub/openfx-misc) · [openfx-arena](https://github.com/NatronGitHub/openfx-arena) |
| openfx-gmic | G'MIC as OFX or After Effects plugin | CeCILL-C / CeCILL 2.0 | "Very early test release… expect crashes" | R | [GitHub](https://github.com/NatronGitHub/openfx-gmic) |
| DaVinci Resolve (free) | Grading and Fusion compositing; can host OFX plugins | Proprietary freeware | Current version and free-tier limits unverified | L | [Product page](https://www.blackmagicdesign.com/products/davinciresolve/) |
| EbSynth (core) | Patch-based, keyframe-guided style propagation | Public domain | Research code | R | [GitHub](https://github.com/jamriska/ebsynth) |
| ReEzSynth / ComfyUI-EbSynth | PyTorch EbSynth with temporal propagation and anti-sliding guidance; ComfyUI nodes | MIT | Active | R | [ReEzSynth](https://github.com/FuouM/ReEzSynth) · [ComfyUI-EbSynth](https://github.com/FuouM/ComfyUI-EbSynth) |
| Ezsynth | Python EbSynth wrapper with optical flow and edge guides | AGPL-3.0 | not checked | R | [GitHub](https://github.com/Trentonom0r3/Ezsynth) |
| pytorch-AdaIN / ReReVST / CCPL | Neural and video style transfer | MIT / GPL-3.0 / Apache-2.0 | Research code | R | [AdaIN](https://github.com/naoto0804/pytorch-AdaIN) · [ReReVST](https://github.com/daooshee/ReReVST-Code) · [CCPL](https://github.com/JarrentWu1031/CCPL) |
| Anisotropic Kuwahara ports | Reference and host ports (original author's code, TouchDesigner, Nuke BlinkScript, Unity 6) | GPL-3.0 where stated | Reference | R | [gpuakf](https://github.com/jkyprian/gpuakf) · [TouchDesigner](https://github.com/yeataro/TD-Anisotropic-Kuwahara) · [Nuke](https://github.com/michaellevin/kuwahara-filter-nuke) · [Unity 6](https://github.com/ericxiong1/AKFUnity6) |

### Free color pipeline tools

| Tool | What it does | Licence | Ev. | Link |
|---|---|---|---|---|
| Blender OCIO config (5.x) | Standard, AgX (+ looks), Khronos PBR Neutral, Filmic, ACES 1.3 and 2.0, HDR displays; AgX Base sRGB inverse for painted plates | GPL (Blender) | R | [config.ocio](https://raw.githubusercontent.com/blender/blender/blender-v5.2-release/release/datafiles/colormanagement/config.ocio) |
| AgX (Eary Chow) and AgX theory (Sobotka) | The view transform behind Blender's default, fixing Filmic's hue collapse | open source | R | [EaryChow/AgX](https://github.com/EaryChow/AgX) · [sobotka/AgX](https://github.com/sobotka/AgX) |
| Blender-AgX-Resolve | DCTL that matches Blender's AgX in DaVinci Resolve | No licence file found | R | [GitHub](https://github.com/EaryChow/Blender-AgX-Resolve) |
| OpenColorIO and ACES configs | Color pipeline library and studio/CG configs | BSD-3-Clause; configs New BSD, docs CC-BY-4.0 | R | [OpenColorIO](https://github.com/AcademySoftwareFoundation/OpenColorIO) · [ACES configs](https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES) |
| flim | Film-emulation view transform used by Saffron | not checked | R | [GitHub](https://github.com/bean-mhm/flim) |
| lut-maker / ray-cast lut | Interactive LUT maker; .cube grading LUTs | not checked | R | [lut-maker](https://github.com/o-l-l-i/lut-maker) · [lut](https://github.com/ray-cast/lut) |

### Free documents and references

| Resource | What you get | Ev. | Link |
|---|---|---|---|
| Blender manual: Kuwahara node | Parameters and artifact warnings | S | [Manual](https://docs.blender.org/manual/en/latest/compositing/types/creative/kuwahara.html) |
| Blender 5.0 compositor notes and migration guide | What changed and how to port node trees | S | [Notes](https://developer.blender.org/docs/release_notes/5.0/compositor/) · [Migration](https://developer.blender.org/docs/release_notes/5.0/migration/compositor_migration/) |
| Blender 5.1 and 5.2 compositor notes | Mask to SDF, speedups, VSE compositing | S | [5.1](https://www.blender.org/download/releases/5-1/) · [5.2](https://developer.blender.org/docs/release_notes/5.2/compositor/) |
| Arcane compositing job (Maxime Templé) | Before and after study of Arcane comp work | S | [ArtStation](https://www.artstation.com/artwork/L316XK) |
| Yann Leroy portrait and Konbini clip | Arcane's compositing supervisor on building an episode's final image | S | [ECV](https://www.ecv.fr/portrait-de-yann-leroy-compositeur-artist-chez-fortiche-et-intervenant-a-lecv-bordeaux/) · [TikTok](https://www.tiktok.com/@konbini/video/7439320810067692833) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Foundry Nuke | Compositor reported for Arcane; BlinkScript runs custom GPU filters such as anisotropic Kuwahara; price not verified | [BlinkScript docs](https://learn.foundry.com/nuke/content/reference_guide/other_nodes/blinkscript.html) |
| Adobe After Effects | Mielgo's reported final compositing tool; subscription, price not verified | [AE SDK page](http://www.adobe.com/devnet/aftereffects.html) |
| DaVinci Resolve Studio | Paid upgrade of free Resolve; price and Studio-only features not verified | [Product page](https://www.blackmagicdesign.com/products/davinciresolve/) |

## 9. Sound design and music start from cheap organic recordings

Every reference production built its stylized sound from **cheap, organic recordings that were then heavily processed**, and designed sound and music together rather than in sequence. Arcane's Hextech sound began as **rubbed wine glasses** processed into a library and layered with instruments and synths, and Shimmer used many animal and human vocals ([AwardsDaily interview with Brad Beaumont and Eliot Connors](https://www.awardsdaily.com/2022/08/16/brad-beaumont-and-eliot-connors-interview/), S). The Tonebenders episode on Season 2, recorded with both sound supervisors and composers Alex Seaver and Alex Temple, explains why the sound design "had to be based in organic sounds" ([Tonebenders 313](https://tonebenderspodcast.com/313-the-sound-design-music-of-arcane-season-2/), S), and the Season 2 re-recording mixers worked on parallel pre-dubs, dialogue and music on one side and effects, backgrounds and Foley on the other, before combining them ([CineMontage](https://cinemontage.org/arcane-sound-mixers-penny-harold-and-andy-lange-on-pushing-the-limits-of-sound-in-animated-tv/), S). Mielgo is credited as sound designer on Jibaro and on *The Windshield Wiper*, where he was also director, writer, editor and composer. Jibaro's armor is "knives, pans, forks and everything that I was able to find in my kitchen", **recorded on his iPhone** ([80.lv](https://80.lv/articles/sounds-of-armor-for-jibaro-were-recorded-using-kitchen-utensils), S), and the siren's voice is deliberately "obnoxious" because the film has no dialogue and the sound must show what the spell does ([Deadline](https://deadline.com/2022/06/alberto-mielgo-love-death-robots-jibaro-animation-dialogue-1235039230/), S). Critics note how Jibaro's deaf-knight perspective uses near-silence and muffled rumbles against piercing screams ([UVic audio blog](https://uvicaudio.wordpress.com/2023/04/13/love-death-robots-jibaro-the-greatness-of-silence/), S, secondary), a no-cost technique for dialogue-free shorts. For the *Windshield Wiper* café conversations, Mielgo invited three men, then three women, to dinner and asked each group the same six questions so the improvised talk would hit specific story beats ([Cartoon Brew](https://www.cartoonbrew.com/interviews/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html), S).

Blender Studio is the indie-scale model. Gold's sound design is credited to Sander Houtman, Cristo Pruppers and Hjalti Hjálmarsson, with music by Dalal & Maesa ([Gold credits](https://studio.blender.org/projects/gold/pages/credits/), S), and a search summary says that on *Sprite Fright* "more than 1500 audio files" were assembled inside Blender's sequencer, with OpenTimelineIO as the studio's documented exchange path ([OpenTimelineIO in Blender](https://studio.blender.org/blog/opentimelineio-in-blender/), S; which page holds the 1,500 figure is unconfirmed). The lesson for a small team is that sound can live in the animation tool until a dedicated mix is needed, and that one author can carry the design while a hired re-recording mixer finishes it, as Jack Goodman did on *The Windshield Wiper* ([Wikipedia](https://en.wikipedia.org/wiki/The_Windshield_Wiper), S).

A fully free audio pipeline is practical in October 2026. **Audacity 4.0** (3 September 2026, followed by 4.0.1 on 30 September) makes clip editing non-destructive and can export each track or labeled region to its own file ([releases](https://github.com/audacity/audacity/releases), R). **Ardour 9** (9.8 on 20 August 2026) adds Region FX, plugins that travel with a single clip ([tags](https://github.com/Ardour/ardour/tags), R; [9.0 news](https://ardour.org/news/9.0.html), S). **OpenTimelineIO** with the separate otio-aaf-adapter can move a Blender cut to AAF for a Pro Tools mixer, though the adapter does not carry effects or complex speed changes ([otio-aaf-adapter](https://github.com/OpenTimelineIO/otio-aaf-adapter), R). LSP Plugins added official Windows builds in August 2026, x42 supplies an EBU R128 loudness meter (LV2, Linux-first), Airwindows is MIT-licensed, and Surge XT, Vital and Dexed cover synthesis; note that Vital's GPLv3 source forbids using the Vital name on your own builds and its free presets cannot be redistributed ([Vital](https://github.com/mtytel/vital), R). Three former staples need care: **LMMS** stable is still 1.2.2 from July 2020 ([LMMS releases](https://github.com/LMMS/lmms/releases), R), **Calf** is officially end-of-life because it depends on GTK2 ([Calf](https://github.com/calf-studio-gear/calf), R), and **Cakewalk by BandLab stopped operating on 1 August 2025**, replaced by Cakewalk Sonar with a free tier ([Gearnews](https://www.gearnews.com/cakewalk-sonar-free-daw-studio/), S). Delivery loudness targets for festivals and streamers were not verified in this research; check each destination's spec before the final mix, and deliver stems (dialogue, music, effects, Foley, backgrounds, plus an M&E mix) alongside the full mix.

For a short headed to festivals or sale, prefer libraries that allow **commercial use without attribution**, namely the Sonniss GDC bundles and Pixabay, and keep a licence log (file, source, licence, author, URL) from day one, because freesound mixes licences per sound and Zapsplat's free tier requires a credit line. Do not use **BBC Sound Effects** under the RemArc licence for anything beyond personal, educational or research use.

### Free audio tools

| Tool | Stage | Licence | Status (Oct 2026) | Ev. | Link |
|---|---|---|---|---|---|
| Audacity 4 | Record, clean, edit | GPL | 4.0.0 (3 Sept 2026), 4.0.1 (30 Sept 2026); 3.7.x continues in parallel | R | [Releases](https://github.com/audacity/audacity/releases) |
| Tenacity | Audacity fork for record and edit | GPL-2.0+ | Development moved to Codeberg (GitHub is a mirror); 1.3.5 stable, 1.4 in alpha | R / S | [Codeberg releases](https://codeberg.org/tenacityteam/tenacity/releases) |
| Blender Video Sequencer | Temp sound and animatic sync; Blender Studio assembled film sound here | GPL | Built-in; audio feature details unverified | S | [OTIO in Blender](https://studio.blender.org/blog/opentimelineio-in-blender/) |
| OpenTimelineIO + otio-aaf-adapter | Conform the cut to AAF (Pro Tools) or EDL | Apache-2.0 | Active; adapters are separate packages | R | [OTIO](https://github.com/AcademySoftwareFoundation/OpenTimelineIO) · [AAF adapter](https://github.com/OpenTimelineIO/otio-aaf-adapter) |
| Ardour 9 | Edit, design, score and mix | GPL | 9.8 on 20 Aug 2026; Linux, macOS, Windows | R | [Tags](https://github.com/Ardour/ardour/tags) |
| LSP Plugins | EQ, dynamics, de-esser and more (LV2, VST2, VST3, CLAP) | open source | 1.2.35 (23 Aug 2026), now with official Windows builds | R | [Releases](https://github.com/lsp-plugins/lsp-plugins/releases) |
| x42-plugins | About 25 LV2 plugins incl. EBU R128 loudness meter, fil4 EQ, convolver | open source | Binaries via gareus.org; Linux-first | R | [GitHub](https://github.com/x42/x42-plugins) |
| Airwindows | Large set of effect plugins | MIT | Repo read-only, no contributions accepted | R | [GitHub](https://github.com/airwindows/airwindows) |
| Surge XT | Hybrid synth for synthetic layers and score | open source | Stable 1.3.4 (Aug 2024); nightlies active to 1 Oct 2026 | R | [Stable](https://github.com/surge-synthesizer/releases-xt/releases) · [Nightly](https://github.com/surge-synthesizer/surge/releases) |
| Vital | Wavetable synth | GPLv3 source; Vital name and free presets restricted | Repo updated after binary releases | R | [GitHub](https://github.com/mtytel/vital) |
| Dexed | DX7 FM synth | open source | v1.0.1 (29 Nov 2024), VST3, AU, CLAP | R | [Releases](https://github.com/asb2m10/dexed/releases) |
| SPARTA | Ambisonic and binaural spatial audio suite | GPLv3 | Up to 10th-order Ambisonics; VST, VST3, AU, LV2, AAX | R | [GitHub](https://github.com/leomccormack/SPARTA) |
| Cakewalk Sonar (free tier) | Windows DAW replacing the discontinued Cakewalk by BandLab | Proprietary freemium | Current | S | [cakewalk.com/sonar](https://www.cakewalk.com/sonar) |
| LMMS | Pattern-based DAW | GPL | **Stagnant**: stable 1.2.2 (2020); 1.3.0-alpha.2 (Sept 2024) | R | [Releases](https://github.com/LMMS/lmms/releases) |
| Calf Studio Gear | LV2 effects | LGPL-2.1 | **End-of-life** (GTK2) | R | [GitHub](https://github.com/calf-studio-gear/calf) |

The IEM plug-in suite, Decent Sampler, Pianobook and Spitfire LABS are commonly used free options, but their sites could not be opened, so their licences and EULAs are **unverified** here.

### Free and freemium sound libraries

| Library | Free terms | Commercial use | Ev. | Link |
|---|---|---|---|---|
| Sonniss GDC Game Audio Bundle | Yearly free bundle (2026: 7.47 GB, 347 WAV files); royalty-free, no attribution; no selling sounds individually; AI-training use reportedly prohibited | Yes | S | [gdc.sonniss.com](https://gdc.sonniss.com/) |
| Pixabay sound effects | Pixabay Content License, 110k+ effects, no attribution; no reselling as-is | Yes | S | [FAQ](https://pixabay.com/service/faq/) |
| Zapsplat (free Basic) | Attribution required; about 4 downloads/hour, MP3 only | Yes, with credit | S | [FAQ](https://www.zapsplat.com/faq/) |
| freesound.org | Per-sound CC0, CC BY or CC BY-NC (check every file; NC rules out commercial use) | Depends on each sound | U | [freesound.org](https://freesound.org/) |
| Soundly (free plan) | App features, about 300 cloud sounds, up to 2,500 local files | Per library terms | S | [Review](https://postperspective.com/review-soundly-an-essential-tool-for-sound-designers/) |
| BBC Sound Effects (RemArc) | 33,000+ effects for personal, educational or research use only | **No** (separate licence needed) | S | [sound-effects.bbcrewind.co.uk](https://sound-effects.bbcrewind.co.uk/) |

### Free talks, interviews and analyses

| Resource | What you learn | Ev. | Link |
|---|---|---|---|
| How Arcane's sonic magic is made | Hextech, Hexite, Shimmer and the Zaun and Piltover soundscapes, with composer Alexander Temple | S | [A Sound Effect](https://www.asoundeffect.com/arcane-sound/) |
| Tonebenders 313 and 309 | Arcane S2 sound design and music; the S2 mix team | S | [313](https://tonebenderspodcast.com/313-the-sound-design-music-of-arcane-season-2/) · [309](https://tonebenderspodcast.com/309-the-mixing-team-for-arcane-season-2/) |
| The Sound and Music of Arcane | Featurette and podcast | S | [SoundWorks Collection](https://soundworkscollection.com/post/the-sound-music-of-arcane-league-of-legends) |
| Arcane S2 re-recording mixers | Split pre-dubs and the finale mix | S | [CineMontage](https://cinemontage.org/arcane-sound-mixers-penny-harold-and-andy-lange-on-pushing-the-limits-of-sound-in-animated-tv/) · [ScreenRant](https://screenrant.com/arcane-re-recording-mixer-penny-harold-mixer-andy-lange-on-building-the-series-finale-through-sound/) |
| Mielgo on Jibaro's sound | Kitchen-utensil armor, the "obnoxious" siren | S | [Deadline](https://deadline.com/2022/06/alberto-mielgo-love-death-robots-jibaro-animation-dialogue-1235039230/) · [AwardsDaily](https://www.awardsdaily.com/2022/06/26/alberto-mielgo-on-his-animated-short-jibaro-in-netflixs-love-death-robots/) |
| Brad North, Love, Death & Robots supervising sound editor | How the series' sound team worked, including Krotos tools | S | [Krotos interview](https://sound.krotosaudio.com/brad-north-supervising-sound-editor-interview/) · [Formosa Group](https://formosagroup.com/supervising-sound-editor-brad-north-and-team-talk-about-their-emmy-award-winning-work-on-the-love-death-robots-series/) |
| "Alberto Mielgo: The Art of Messy Sound Design" | Third-party video essay across his films | S | [YouTube](https://www.youtube.com/watch?v=Bx-t6FzcNVc) |
| Jibaro: The Greatness of Silence | Critical analysis of the deaf-POV mix | S | [UVic audio blog](https://uvicaudio.wordpress.com/2023/04/13/love-death-robots-jibaro-the-greatness-of-silence/) |
| The Windshield Wiper team interview | Staged dinner conversations as walla | S | [Cartoon Brew](https://www.cartoonbrew.com/interviews/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html) |

### Paid (one line each)

| Item | One line | Link |
|---|---|---|
| Avid Pro Tools | Industry-standard post-production DAW; reachable from Blender via OTIO to AAF; price not verified | [Wikipedia](https://en.wikipedia.org/wiki/Pro_Tools) |
| Reaper | Low-cost professional DAW; price not verified (page could not be loaded) | [reaper.fm](https://www.reaper.fm/purchase.php) |
| Soundly Pro | Cloud SFX library and manager, about $14.99/month or $12.49/month annually (may be outdated) | [Review](https://postperspective.com/review-soundly-an-essential-tool-for-sound-designers/) |
| Krotos Everything Bundle | Real-time sound-design tools used on Love, Death & Robots; price not verified | [Krotos case study](https://www.krotosaudio.com/love-death-robots-sound-design/) |
| Zapsplat Gold | Removes attribution, adds WAV and unlimited downloads; about £4.99/month or £39.99/year | [Upgrade page](https://www.zapsplat.com/donating-and-upgrading/) |
| A Sound Effect marketplace | Store for commercial SFX libraries | [asoundeffect.com](https://www.asoundeffect.com/product-tag/arcane/) |

## 10. Abandoned, outdated and license-restricted tools to avoid

Free tooling for this style decays quickly, for three reasons visible in the evidence. Blender's own rewrites broke older add-ons: custom normals changed in 4.1, Grease Pencil and brushes were rebuilt in 4.3, and 5.0 changed the animation system and removed compositor nodes. Many tools have a single maintainer. And research code often carries non-commercial licences. Pin add-on versions to your Blender version, prefer add-ons with a recent 5.x release, and test anything below before it touches production.

### Abandoned, stale or at-risk

| Tool | Area | Problem | Ev. | Use instead |
|---|---|---|---|---|
| Storyboarder | Boards | No stable release since v2.1.0 (Sept 2023); "still maintained?" issue unanswered | R | Grease Pencil + VSE; Krita |
| KIT Scenarist | Script | Officially replaced: "no KIT updates anymore" | S | Story Architect |
| Storypencil | Boards | User reports of breakage with Grease Pencil 3 (4.3+) | S | Plain GP scenes + VSE scene strips; storytools |
| CrowdRender | Render | Blender 5.0 support still "in development" | S | Flamenco |
| blender-studio-tools GitHub mirrors | Pipeline | Archived (July 2026 and Aug 2023) | R / S | projects.blender.org/studio/blender-studio-tools |
| EEVEE NPR Prototype | Shading | Discontinued; archived at Blender 4.4 | R | Blender 5.3 Material Lighting nodes; compositor |
| bb-yi and NaMgAl Goo/NPR ports | Shading | Unofficial single-maintainer builds | R | Official Blender, or Goo Engine 4.4 frozen |
| Malt | Shading | No code push since Mar 2026; no macOS | R | Official EEVEE |
| EEVEEToon; btoon | Shading | 2.8-era and "outdated"; stale since 2020 | R | Shader to RGB, LSCherry, 5.3 lighting nodes |
| Blender-miHoYo-Shaders; StarRailNPRShader | Shading | Archived; built for datamined game assets | R | Study only |
| MNPR | Shading (Maya) | Unmaintained since 2019 | R | MNPRX (paid) |
| Godot-Cel-Shader (EXPWorlds) | Shading (Godot) | Godot 3 era, last push 2020 | R | Godot-ComicShader |
| Blender-Normal-Editing-Tools (isathar) | Modeling | Built for Blender 2.74–2.79 | R | Abnormal; Set Mesh Normal node |
| Edit Split Normals (Oscurart) | Modeling | Old tweet-linked tool, status unknown | U | Abnormal |
| Abnormal | Modeling | Last release targets 4.5; no 5.x statement | R | Test first; fall back to Set Mesh Normal |
| "Enable Auto Smooth" normal-transfer tutorials | Modeling | Obsolete since Blender 4.1 | S | Smooth by Angle; custom normals work without it |
| Box_deform (standalone) | Grease Pencil | Last update 2022, predates GPv3 | R | Greasepencil Tools |
| Pre-4.3 append-style brush packs (e.g. Rakurri); Brush Manager | Sculpt | Pre-asset brush model | R / L | Re-save as 4.3+ brush assets |
| TexTools | UVs and baking | No commits since Dec 2024; no 4.2-extension or 5.x note | R | Ucupaint bakes; unproven TexTools-Blender5 fork |
| Flow Map Painter | Texturing | Self-declared deprecated in Blender 5.0 | R | Wait for its refactor |
| EasyBake; Principled-Baker | Baking | Last commits 2022 and 2020 | R | Ucupaint bake types; Bake Wrangler |
| Magic UV (GitHub README) | UVs | Lists only Blender 2.7x/2.8 | R | Built-in UV tools |
| ArmorLab | Texture generation | Archived and dropped from armortools | R | — |
| AnimAide | Animation | "Development no longer active" | R | Built-in Graph Editor tools |
| BlendArMocap | Mocap | Discontinued by its author | R | NyuyenMocap-Oyen fork; BlendCap |
| Open Mocap | Mocap | Blender 4.0 and earlier only | R | BlendCap; FreeMoCap |
| Blender Studio rigs pinned to 3.6 | Rigging | Some "require exactly Blender 3.6" | S | Study in 3.6; rebuild with CloudRig |
| Pre-4.3 Grease Pencil face-rig tutorials; GPMouth | 2D rigs | Written for the GPv2 API | S | GPv3-era material; Tiny 2D Rig Tools |
| DWANGO OpenToonz plugins | VFX | Prebuilt for OpenToonz 1.0 with old OpenCV | R | OpenToonz 1.8 built-in FX |
| Morevna OpenToonz | VFX | Flagged discontinued | L | OpenToonz; Tahoma2D |
| coa_tools | 2D cut-out | Likely outdated | L | Tiny 2D Rig Tools |
| Geometry-Nodes-Simulation hack | FX | Blender 3.2 workaround superseded by Simulation Zones | R | Simulation Zones |
| blender-spritesheets | FX | Developed on Blender 2.81 | R | Test, or flipbook-packer |
| Natron (official) | Compositing | No release after 2.5.0; seeking maintainers | R | Blender compositor; Niik-l fork (experimental) |
| openfx-gmic | Compositing | "Very early test release" | R | G'MIC-Qt in GIMP or Krita |
| blender-custom-nodes (bitsawer) | Compositing | 2.79-era custom build | R | MP_Comp; Cymatics |
| Compositor node packs made before 5.0 | Compositing | Blender 5.0 removed or replaced several nodes | R / S | Packs that state 5.0+ (MP_Comp, Cymatics) |
| LMMS | Sound | Stable still 1.2.2 (2020) | R | Ardour + Surge XT |
| Calf Studio Gear | Sound | End-of-life (GTK2) | R | LSP; x42 |
| Cakewalk by BandLab | Sound | Shut down 1 Aug 2025 | S | Cakewalk Sonar free tier; Ardour |

### Free, but not free for every use

| Item | Restriction | Ev. |
|---|---|---|
| Stylized Neural Painting | CC BY-NC-SA 4.0: non-commercial only | R |
| GVHMR and pipelines built on it | Educational, research and non-profit use only | R |
| artistic-videos | Non-profit use only | R |
| Few-Shot Patch-Based Training | No open-source licence; "for commercial interests, please, reimplement it" | R |
| WHAM | MIT code, but SMPL body models need separate registration (terms not checked) | R |
| Cascadeur free tier | Reportedly non-commercial with export caps (conflicting summaries) | S |
| Houdini Apprentice | Non-commercial (limits unverified) | U |
| Anchorpoint Personal | Single user, non-commercial | S |
| BBC Sound Effects (RemArc) | Personal, educational or research use only | S |
| freesound sounds marked CC BY-NC | No commercial use; licence is per sound | U |
| Zapsplat free tier | Credit line required | S |
| Vital | GPLv3 source, but the Vital name and free presets are restricted | R |
| Kitsu/Zou, FreeMoCap, Saffron, Ezsynth (AGPL-3.0) | Network copyleft applies if you modify and host or redistribute; rendered frames are generally not considered derivative, but check with counsel | R / U |
| GeometryNodes-Stylized-Scene-Generator | No licence stated, so default copyright applies | R |
| Blender Studio assets | CC-BY with attribution; some files are CC-BY-ND | S |

## 11. Recommended free starter stack: Blender 5.2 LTS plus a dozen free tools

This is the smallest free stack that covers every subtopic and maps onto how the reference productions work. It assumes a Blender-centred team of one to ten people; every pick is current as of October 2026 and every watch-out comes from the sections above.

| Stage | Free pick | Why this one | Fallback | Watch-out |
|---|---|---|---|---|
| Core application | **Blender 5.2 LTS** | Supported to July 2028; every tool below targets it | Move to 5.3 after release for Material Lighting nodes | Pin add-on versions per Blender version |
| Script | **Story Architect**, saved as Fountain in version control | GPL, active, clean diffs | Trelby | — |
| Visdev, color script, painted plates | **Krita 6** + David Revoy's CC0 brushes | GPL, active | GIMP + G'MIC | Older Krita plugins may need Krita 6 updates |
| Boards and animatic | **Grease Pencil + Video Sequencer** | Same file lineage as layout; how Gold was boarded | Kdenlive for external edits | Storypencil breakage; Storyboarder abandoned |
| Tracking and review | **Kitsu** (self-hosted) + Blender Kitsu add-on | Very active; built-in review | Prism 2 (lighter) | Needs hosting; AGPL if you modify and host for others |
| Version control | **Git LFS**, or **SVN + Blender SVN** | Both supported by Blender Studio's docs | Perforce free tier (up to 5 users) | Use file locking for .blend files |
| Sculpt and retopology | Blender sculpt + **RetopoFlow** (GPL source) | Free and active | — | Brush packs must be 4.3+ assets |
| Face normals | Data Transfer proxy + **Set Mesh Normal**; **Abnormal** for hand edits | Built-in; MIT | — | Abnormal's 5.x support unconfirmed |
| Camera cheats | **Lattice Magic** Camera Lattice; PersPress for telephoto faces | Studio-made; Geometry Nodes-based | — | PersPress is weeks old |
| Painterly surfaces | **Brushstroke Tools** | The tool that made Gold | Kuwahara in comp | 5.x compatibility unverified |
| Texturing | **Ucupaint** + Krita (blender-krita-link) + Quick Edit/Apply projection | Layers inside Blender; projection is the Arcane and Mielgo paint-over | ArmorPaint (compile), Material Maker | The Krita bridge is experimental |
| Shading and lighting | EEVEE **Shader to RGB** ramps now, **Light Evaluation / Shadow Raycast** in 5.3; light linking | Official, stable path | Goo Engine 4.4 if you can freeze on 4.4 | Lighting nodes are EEVEE-only |
| Lines | Line Art / Freestyle, or Filter-node edges in comp | Built-in | Pencil+ 4 (paid) | — |
| Rigging | **CloudRig** | Used on Gold and three other open movies | Rigify | CC-BY rigs pinned to 3.6 |
| Animation | **Stepped F-Curve modifier** + **SMEAR** + Wiggle Bones (5.0+ fork) | Per-shot stepping, smears and multiples, follow-through | Stop Motion Style Animator | SMEAR tested on 4.2 only |
| Reference and mocap | Phone video reference; **FreeMoCap** or **BlendCap** for blocking | Matches the reference-then-keyframe practice | — | Avoid GVHMR-based tools commercially |
| 2D FX | **Grease Pencil v3** in scene; **OpenToonz/Tahoma2D** or Krita over plates | GP motion blur since 5.0; Modified BSD licence | — | Glow and tone must come from comp |
| 3D FX | **Simulation Zones** + instanced hand-drawn cards; flipbook-packer | How Gold built its FX | FLIP Fluids (paid) | No mature free toon-FX add-on exists |
| Compositing | **Blender compositor** + **MP_Comp** (CC0) + **Saffron** (AGPL) | Native nodes, 5.0+ | Natron fork (experimental) | Pre-5.0 node packs break |
| Color and grade | **Standard** view for flat painted looks, **AgX** for hot highlights; free Resolve + AgX DCTL | Painted colors land unchanged under Standard | ACES 2.0 config | AgX desaturates bright highlights |
| Render | **Flamenco** on your own machines | Official and active | SheepIt for non-confidential overflow | SheepIt renders on volunteers' machines |
| Sound | **Audacity 4** → **Ardour 9** + LSP, Airwindows, x42 + Surge XT, Vital, Dexed | All free and current | Cakewalk Sonar free tier (Windows) | LMMS stagnant; Calf end-of-life |
| Sound libraries | Own recordings + **Sonniss GDC** + **Pixabay** | Commercial use, no attribution | Zapsplat (with credit); freesound CC0 sounds | BBC RemArc is non-commercial |
| Interchange | **OpenTimelineIO** (+ AAF adapter) | Apache-2.0; Blender Studio's documented path | EDL | The AAF adapter drops effects |

## 12. Where to start: six tests before building the film

Do not build the pipeline first. Each reference production settled its look in pre-production and tests, and a small team should do the same at small scale: one shot, one character, one effect, one sound. Run the tests in this order, because each depends on the decisions before it.

| Step | Goal | Do this | Free resources | Done when |
|---|---|---|---|---|
| 0. Study | Know what each look actually is | Watch the Gold film and the BCON 2024 "Procedural Oil Painting" talk; watch the Arcane S2 texturing video and read VFX Voice on Season 2; read the befores & afters and BlenderNation interviews on *The Witness* and the *Windshield Wiper* Q&A | Section 1 tables | You can say where the paint lives in each production |
| 1. Choose a strategy per shot | Build no more 3D than the shot needs | Tag every board panel as painted plate + 3D character (Windshield Wiper, cheapest), projected paint on simple 3D (The Witness, Arcane S2), or full brushstroke 3D set (Gold) | Krita; Grease Pencil boards | Every shot has a tag and a reason |
| 2. Set up a minimal project | Avoid file chaos later | Install Blender 5.2 LTS; copy Blender Studio's folder and naming conventions; set up Git LFS or SVN; start a licence log for every asset and sound | [Naming conventions](https://studio.blender.org/tools/naming-conventions/introduction); [Git LFS](https://github.com/git-lfs/git-lfs) | Any shot file can be found by its path |
| 3. Look-dev test (one 5-second shot) | Prove the image | Paint a color key in Krita; model simple forms; paint albedo in Ucupaint and Krita; shade in EEVEE with a Shader to RGB ramp and light linking; add one Brushstroke Tools layer on large forms; finish with Kuwahara (Size driven by depth), Glare and grain under the Standard view | Ucupaint, Brushstroke Tools, MP_Comp, Saffron | The render matches the color key at thumbnail size |
| 4. Animation test | Prove the motion | Shoot phone reference; animate a Blender Studio CC-BY rig or a CloudRig character on ones; apply the Stepped modifier on twos with per-character offsets; add one SMEAR multiple and one Camera Lattice cheat | CloudRig, SMEAR, Lattice Magic | A 3-second action reads clearly on twos |
| 5. FX test | Prove the effects language | Draw a smoke puff or spark on twos in Grease Pencil v3 over the locked render, or in OpenToonz exported to a card; add glow in comp | Grease Pencil v3, OpenToonz, Kenney particles for blocking | The drawn FX sits in the shot under matching light |
| 6. Sound test | Prove the sound language | Record household Foley on a phone; clean it in Audacity; layer it with a Surge XT texture in Ardour; mix against the test shot | Audacity, Ardour, Surge XT, Sonniss | Picture and sound work together on the test shot |
| Then scale | Grow the pipeline only when needed | Add Kitsu and Flamenco, then Shot Builder and Asset Pipeline as the shot count grows; re-check section 10 before adopting any add-on | Section 2 tables | — |

Two habits will save the most time. First, **verify before you lock**: every S-, L- or U-tagged claim, and every add-on's Blender 5.x compatibility, should be checked on the live page, because this research could not open most of them. Second, **keep the painting central**: if a test shot looks wrong, the fix in all three reference productions was a better painting or a better light decision, not a new shader.

## Conclusion

The research reframes the question an indie creator should ask. It is not "which renderer or shader makes Arcane", but **"where does the paint live in this shot, and who paints it?"** All three productions answer with painted inputs (texture, plate or stroke) and keep 3D, rendering and compositing as integration, so the scarce resource is painting time and art direction, not software. That makes the per-shot choice between a painted plate, projected paint on simple 3D and a full brushstroke set the most consequential technical decision on a small film, ahead of any shader. It also explains why surface-anchored paint (UV paint, camera projection, world-space strokes) is the safer foundation than screen-space filters: it holds up in motion, while filters are best kept for unifying a frame.

2026 is a transition year for open NPR. Official Blender gained per-light material shading in 5.3, but the rest of the prototype's ideas survive only in single-maintainer forks, so a production starting now should design its look to work in official EEVEE plus the compositor, treat forks as optional experiments, and revisit after the next releases. The evidence behind this reference is also thin in a specific way: facts about open-source tools are solid because they were read from GitHub, while facts about how the films were made are mostly second-hand. Before quoting any production claim from this repository, re-read the primary page; the highest-value targets are the Arcane S2 texturing video, the BCON 2024 Gold talk and the befores & afters Mielgo interviews.
