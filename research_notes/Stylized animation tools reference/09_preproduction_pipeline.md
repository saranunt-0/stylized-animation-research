# Pre-production, Pipeline & Production-Management Tools for an Indie Stylized/Painterly 3D Short (as of Oct 2026)

> **Method note for the report writer (read first).** This environment's egress proxy blocked direct page fetches for almost every domain (studio.blender.org, projects.blender.org, flamenco.blender.org, 80.lv, awn.com, beforesandafters.com, creativebloq.com, blog.cg-wire.com, syncsketch, web.archive.org, vendor sites). Only github.com pages could be fetched in full. The session's shared web-search budget also ran out partway through. Each finding is therefore tagged:
> - **[F]** = the page itself was fetched and read.
> - **[S]** = the fact comes from the search engine's summary/snippet of that URL. The URL is real (returned by search), but the page text was not read directly, so treat exact numbers and quotes as "verify before publishing."
>
> Category tags used: `documentation` / `tutorial` / `tool` / `code-repo` / `asset` / `course(paid)` / `talk`.

---

## Q1. What does Blender Studio's open pipeline consist of as of Oct 2026 (repos, docs URLs, what each tool does), and how suitable is it for a 1–10 person indie team?

### Takeaway
Blender Studio's pipeline is a set of open-source Blender add-ons (**Blender Kitsu** with its built-in **Shot Builder**, **Asset Pipeline**, **Blender SVN**, **Render Review**, **Contact Sheet**, plus animation and utility add-ons). They sit on top of three services: **Kitsu** (tracking), **SVN** (or Git LFS) for versioning, and **Flamenco** (rendering). The code lives at projects.blender.org/studio/blender-studio-tools and the docs at studio.blender.org/tools. The docs include a Quick Start, a Setup Assistant, folder and naming conventions, and TD and artist guides, so a small team can adopt the pipeline. However, it assumes a TD-literate person who will run a Kitsu server and an SVN repo. A third-party wrapper (OpenStudioHub) exists because outsiders found that setup hard. In July 2026 Blender Studio announced the feature film *Overgrown* and promised more open pipeline tools and docs for larger productions, so expect the pipeline to keep changing through 2026–27.

### Cited Findings

**Repos (code-repo)**
- Official source repo: `projects.blender.org/studio/blender-studio-tools` ("Blender Studio tools source code"). Clone with `git clone https://projects.blender.org/studio/blender-studio-tools.git` — [S] [Blender Projects repo](https://projects.blender.org/studio/blender-studio-tools); the docs' TD guide has a "Repository" page — [S] [studio.blender.org/tools/td-guide/repository](https://studio.blender.org/tools/td-guide/repository)
- A GitHub mirror (paulgolter/blender-studio-tools) was **archived (read-only) on July 1, 2026**. Its snapshot lists 14 tools: shot-builder, blender-kitsu, asset-pipeline, blender-purge, cache-manager, contactsheet, render-review, anim-setup, bone-gizmos, blender-media-viewer, grease-converter, anim-cupboard, blender-svn, pose-shape-keys (1,520 commits). The README calls them "tools that are used by the Blender Animation Studio across productions." — [F] [github.com/paulgolter/blender-studio-tools](https://github.com/paulgolter/blender-studio-tools). *This is an old layout. Use the projects.blender.org repo as the canonical, current source.*
- Another fork (Warnakala/blender-studio-tools) was archived Aug 4, 2023 — [S] [GitHub](https://github.com/Warnakala/blender-studio-tools)
- A user fork on projects.blender.org is named `blender-studio-pipeline` and has `scripts-blender/addons/blender_kitsu/`. This suggests the repo was once called "blender-studio-pipeline" (inference from the fork name, unverified) — [S] [projects.blender.org/Mets/blender-studio-pipeline …/blender_kitsu/README.md](https://projects.blender.org/Mets/blender-studio-pipeline/src/branch/main/scripts-blender/addons/blender_kitsu/README.md)

**Docs hub (documentation) — studio.blender.org/tools**
- Add-ons overview / readme — [S] [Blender Studio Add-ons](https://studio.blender.org/tools/addons/overview); [S] [Add-ons readme](https://studio.blender.org/tools/addons/addons_readme)
- Pipeline Quick Start: Setup — [S] [Pipeline Setup](https://studio.blender.org/tools/pipeline-overview/quick-start/setup); Usage — [S] [Pipeline Usage](https://studio.blender.org/tools/pipeline-overview/quick-start/usage). The workflow "relies on Blender, Blender Add-Ons, and additional services like Kitsu and Flamenco" — [S] (same pages)
- Infrastructure page — [S] [Infrastructure](https://studio.blender.org/tools/pipeline-overview/infrastructure)
- Shot Assembly (how task files link to each other) — [S] [Shot Assembly](https://studio.blender.org/tools/pipeline-overview/shot-production/shot-assembly)
- Setup Assistant (TD guide) — [S] [Setup Assistant](https://studio.blender.org/tools/td-guide/setup_assistant)
- Project Tools, artist guide: Project Overview — [S] [Project Overview (artist guide)](https://studio.blender.org/tools/artist-guide/project_tools/project-overview) / [S] [(user guide)](https://studio.blender.org/tools/user-guide/project_tools/project-overview); "Creating Your First Asset" — [S] [usage-asset](https://studio.blender.org/tools/artist-guide/project_tools/usage-asset)
- Kitsu user guide — [S] [Kitsu](https://studio.blender.org/tools/user-guide/kitsu); Using SVN — [S] [Using SVN](https://studio.blender.org/tools/user-guide/svn)
- Render farm TD notes — [S] [Render Farm](https://studio.blender.org/tools/gentoo/td/render_farm)

**What each tool does**
- **Blender Kitsu** (`tool`): an add-on for working with a Kitsu server from inside Blender — [S] [Blender Kitsu docs](https://studio.blender.org/tools/addons/blender_kitsu); background — [S] [Kitsu add-on for Blender (blog)](https://studio.blender.org/blog/kitsu-addon-for-blender/)
- **Shot Builder** (`tool`, now a feature of Blender Kitsu). It builds one shot file per task type from Kitsu data, auto-names scenes, and creates output collections for anim/fx/layout/lighting/previz/storyboard. It also links output collections between task types following the shot-assembly spec, loads editorial exports into the shot file's VSE, and loads assets via an `asset_index.json`. Per-project "hooks" live in `assets/scripts/shot-builder` and can be generated from the add-on preferences — [S] [Blender Kitsu docs](https://studio.blender.org/tools/addons/blender_kitsu); [S] [Shot Assembly](https://studio.blender.org/tools/pipeline-overview/shot-production/shot-assembly); [S] [Pipeline Setup](https://studio.blender.org/tools/pipeline-overview/quick-start/setup)
- **Asset Pipeline** (`tool`). "Task layers" (e.g., Modeling, Rigging, Shading) are defined in a JSON file, and each task layer usually gets its own file. The add-on includes an Asset Builder and an Asset Updater — [S] [Asset Pipeline docs](https://studio.blender.org/tools/addons/asset_pipeline); history — [S] [Asset Pipeline 2022 Update (blog)](https://studio.blender.org/blog/asset-pipeline-update-2022/)
- **Blender SVN** (`tool`): a UI for the Subversion version control the studio uses, worked from inside Blender — [S] [Blender SVN](https://studio.blender.org/tools/addons/blender_svn)
- **Render Review** (`tool`): review Flamenco renders in the Sequence Editor ("Once your shot(s) have been rendered by Flamenco, you are ready to review your renders using the Render Review Add-On") — [S] [Pipeline Usage](https://studio.blender.org/tools/pipeline-overview/quick-start/usage) (snippet surfaced with the add-ons overview results)
- **Contact Sheet** (`tool`): "Make Contactsheet" builds a temporary scene that lays the selected VSE strips out in a grid — [S] [Contact Sheet docs](https://studio.blender.org/tools/addons/contactsheet); [S] [Contact Sheet Add-on (blog)](https://studio.blender.org/blog/contact-sheet-addon/)
- Other add-ons in the repo (anim-setup, bone-gizmos, cache-manager, pose-shape-keys, anim-cupboard, blender-purge, grease-converter, media-viewer). These appear in the archived mirror's list but were not individually verified for Oct 2026 status — [F] [mirror](https://github.com/paulgolter/blender-studio-tools)

**Folder structure & naming conventions (documentation)**
- A project has three main directories. `local` holds Blender and add-ons, `shared` is network-synced, and `svn` is the version-controlled folder holding production .blend files. An optional `render` folder can be added — [S] [Folder Structure Overview](https://studio.blender.org/tools/td-guide/folder_structure_overview); [S] [Project Folder Setup](https://studio.blender.org/tools/td-guide/project_folder_structure)
- Proposed SVN tree: `pro` (production), `pre` (pre-production), `dev` (tests), `edit` (editorial), `tools` — [S] [SVN Folder Structure](https://studio.blender.org/tools/naming-conventions/svn-folder-structure); populating — [S] [Populating SVN](https://studio.blender.org/tools/td-guide/populating_svn)
- Naming tokens: `variant` (exports/renders only), `version` (v001, v002…), `version_info` (720p, lowres, cache). Shot files live at `svn/pro/shots/<sequence>/<shot>/<shot>-<task>.blend` — [S] [Naming Conventions intro](https://studio.blender.org/tools/naming-conventions/introduction)
- The tools are "designed to work with version control software (SVN/GIT-LFS)", and the docs recommend SVN, Git LFS, or Perforce — [S] [Pipeline Setup](https://studio.blender.org/tools/pipeline-overview/quick-start/setup)

**Context: films & roadmap**
- Project Gold was announced 22 May 2023 — [S] [Blender Studio blog](https://studio.blender.org/blog/announcing-project-gold-the-next-blender-open-movie/); [S] [BlenderNation](https://www.blendernation.com/2023/05/23/project-gold-new-blender-open-movie-announced/). It premiered at Blender Conference 2024 and was released online 7 Nov 2024. It showcased light linking, Simulation/Geometry Nodes tools, viewport compositor work and "art-directable, stylized, non-photorealistic rendering with Cycles". Project files and the painterly Brushstroke Tools are public; logs and a workshop are for subscribers — [S] [Creative Bloq](https://www.creativebloq.com/3d/heres-how-to-watch-blender-studios-beautiful-project-gold-and-get-the-project-files-and-brushstroke-tools); project page — [S] [studio.blender.org/projects/gold](https://studio.blender.org/projects/gold/)
- **Overgrown** (2026) is Blender Studio's feature-film project, co-directed by Hjalti Hjálmarsson and Rik Schutte. It promises "logs, production knowledge, project files, documentation and open source tools for larger animated productions" and is funded through subscriber growth — [S] [Digital Production, 2026-07-09](https://digitalproduction.com/2026/07/09/overgrown-targets-an-open-feature-pipeline-for-blender/); [S] [Overgrown announcement](https://studio.blender.org/blog/overgrown-announcement/); [S] [Overgrown project page](https://studio.blender.org/projects/overgrown/)
- An ACM Digital Library entry titled **"Building a Blender pipeline in 30 Minutes"** exists (`talk`). The DOI prefix suggests a SIGGRAPH 2025 talk, but its authorship and content are **unverified** — [S] [dl.acm.org/doi/10.1145/3721251.3742867](https://dl.acm.org/doi/10.1145/3721251.3742867)

**Third-party wrapper aimed at indies**
- **OpenStudioHub** (`code-repo`, GPL-3.0) is a desktop app that creates isolated Blender environments per project. It injects add-ons and preferences and adds Kitsu SSO and SVN management. Its README says the Blender Studio tools carry "a brutal technical learning curve" and don't work outside their exact infrastructure; OpenStudioHub wraps them in "a smart Sandbox environment". The project is tiny (111 commits, 2 stars) and targets indie to mid-size studios — [F] [github.com/3dvm/openstudiohub](https://github.com/3dvm/openstudiohub); [S] [tech-artists.org thread](https://www.tech-artists.org/t/simplifying-blender-studio-tools-kitsu-and-blender-pipeline-meet-openstudiohub/18500)

### Inferences
- **Suitability for 1–10 people.**
  - *Good fit* if the team is Blender-only and has one TD-minded member. Shot Builder plus Kitsu removes most manual file plumbing (per-task shot files, linked output collections, editorial loaded into the VSE). The folder and naming conventions can be copied as-is even without the tools.
  - *Friction points:*
    - You have to host Kitsu (Docker/VM) and SVN, and Flamenco if you want Render Review.
    - The tools follow Blender Studio's internal conventions (task types, hook scripts, asset_index.json).
    - Docs and tools change with each Blender release.
    - The third-party OpenStudioHub README frames the learning curve as steep.
  - For 1–3 people, a sensible approach is to copy the **conventions** (folder tree, naming, task-layer thinking) and use only **Blender Kitsu + Flamenco**. Add Asset Pipeline and Shot Builder hooks once the team and shot count grow.
- Because GitHub mirrors are archived and the canonical repo is on projects.blender.org, always pin add-on versions to the Blender version (the tools are developed against current Blender releases at the studio).
- Overgrown's "feature pipeline" promise means the toolset may be reorganized again in 2026–27. Check studio.blender.org/tools before locking in.

### Gaps
- Could not read studio.blender.org/tools directly (egress blocked). So there is no verified Oct 2026 list of add-ons beyond the archived mirror, and no confirmation of whether Render Review, Contact Sheet etc. are still separate add-ons or have been merged/moved to the Extensions platform.
- No direct confirmation of Blender Studio's team size, or of whether they still use SVN rather than Git LFS in 2026. The docs mention both; the studio's own SVN usage is stated on the Blender SVN page [S].
- License of blender-studio-tools not verified (likely GPL like Blender add-ons — **unverified**).
- No authoritative statement on whether the old repo name "blender-studio-pipeline" redirects to blender-studio-tools.

---

## Q2. What is the most practical free/open-source pipeline stack (pre-production → tracking → version control → render → review) for an indie stylized short, with links and maintenance status?

### Takeaway
A practical, almost entirely FOSS stack:

| Stage | Pick | Alternatives |
|---|---|---|
| Script | **Story Architect** (or Trelby) using Fountain | — |
| Concept/visdev | **Krita** | Blender **Brushstroke Tools** for painterly 3D look-dev |
| Boards | **Blender Grease Pencil** in the VSE | Krita; Storyboarder is legacy/unmaintained |
| Animatic | **Blender VSE** | Kdenlive/Shotcut; OTIO for interchange |
| Tracking | **Kitsu** self-hosted + Blender Kitsu add-on | Prism (lighter); AYON (heavier) |
| Version control | **SVN + Blender SVN add-on**, or **Git LFS** | Perforce free ≤5 users; Anchorpoint/Diversion free tiers |
| Render | **Flamenco** on own machines; SheepIt for non-confidential overflow | CrowdRender |
| Review | Kitsu review + Render Review/Contact Sheet | OpenRV/xSTUDIO if a pro player is needed (build from source) |

Biggest maintenance warnings: **Storyboarder** has had no maintainer activity since early 2024. **Storypencil** has reported breakage with Grease Pencil 3 (Blender 4.3+).

### Cited Findings

#### A. Script writing
- **Story Architect / STARC** (`tool`, GPL-3.0). Takes a story "from the first idea to a production-ready document" (screenplay, series, comics, stage, audio). Imports and exports Final Draft, Fountain, DOCX, ODT, PDF, Celtx, Trelby and KIT Scenarist. The repo is active (3,450 commits). Premium plans exist (starc.app/pricing), but the open-source core is free — [F] [github.com/story-apps/starc](https://github.com/story-apps/starc); site [starc.app](https://starc.app); [S] [LinuxLinks overview](https://www.linuxlinks.com/story-architect-reinventing-screenwriting/)
- **KIT Scenarist** (`tool`) — **discontinued**: "KIT Scenarist is now replaced by Story Architect. There will be no KIT updates anymore." — [S] [kitscenarist.ru](https://kitscenarist.ru/en/index.html)
- **Trelby** (`tool`, GPL-2.0). Multi-platform screenwriting app, recently ported to Python 3 via a merged fork. Available via Flatpak, Fedora, Chocolatey and PyPI. 55 open issues and 11 PRs show it is maintained — [F] [github.com/trelby/trelby](https://github.com/trelby/trelby); site [trelby.org](https://www.trelby.org/); Fountain-site note — [S] [fountain.io/2023/05/30/trelby](https://fountain.io/2023/05/30/trelby/)
- **Fountain** (plain-text screenplay markup, `documentation`). Supported by Story Architect, KIT and Trelby — [S] [fountain.io](https://fountain.io/2023/05/30/trelby/). *Inference:* a `.fountain` file diffs cleanly in Git/SVN.
- Final Draft (paid): see Q4.

#### B. Concept art, visdev & color scripts
- **Krita** (`tool`, GPL-3). "Free and open source digital painting application" for concept artists, illustrators and VFX. Stable branch 5.2, with 5.3 in development (per README). User manual [docs.krita.org](https://docs.krita.org/en/user_manual.html); community forum (where brush packs are shared) [krita-artists.org](https://krita-artists.org/) — [F] [github.com/KDE/krita](https://github.com/KDE/krita); site [krita.org](https://www.krita.org)
- **Brushstroke Tools** (`tool`, from Blender Studio for Project Gold). Lets you build and edit layers of procedurally generated 3D brushstrokes, either filling a mesh surface or drawing directly onto it, with per-layer stroke shape, style and material control. Published on the Blender Extensions platform; v1.2.3 (Nov 2024 per snippet), requires Blender 4.2 LTS+, with 127k+ downloads (snippet) — [S] [extensions.blender.org/add-ons/brushstroke-tools](https://extensions.blender.org/add-ons/brushstroke-tools/); [S] [CG Channel, Nov 2024](https://www.cgchannel.com/2024/11/get-the-blender-studios-free-brushstroke-tools-for-blender/)
- Training: **"Stylized Rendering with Brushstrokes"** (`tutorial`/`course(paid)`, subscriber workshop) — [S] [studio.blender.org/training/stylized-rendering-with-brushstrokes](https://studio.blender.org/training/stylized-rendering-with-brushstrokes/)
- Fortiche/Mielgo visdev methods: see Q3.

#### C. Storyboarding
- **Storyboarder (Wonder Unit)** (`tool`). **Effectively unmaintained.**
  - GitHub releases: v3.0.0 *pre-release* on 17 Feb 2024, last stable v2.1.0 on 3 Sep 2023 — [F] [releases](https://github.com/wonderunit/storyboarder/releases)
  - Issue #2665 (opened 8 Jun 2026): "are we still maintaining this repo? the last update to master branch is already 4 years ago". No maintainer reply, no labels — [F] [issue #2665](https://github.com/wonderunit/storyboarder/issues/2665)
  - Similar open questions: [#2609 "Is this project still alive?"](https://github.com/wonderunit/storyboarder/issues/2609), [#2509](https://github.com/wonderunit/storyboarder/issues/2509), [#2585 "2.1 or 3.0?"](https://github.com/wonderunit/storyboarder/issues/2585) — [S]
  - Wonder Unit's own essay on FOSS — [S] [wonderunit.com/thoughts-on-free-and-open-source](https://wonderunit.com/thoughts-on-free-and-open-source/)
  - **Conflict:** a download aggregator claims "v2.1 released 12/25/2024" — [S] [updatestar](https://storyboarder.updatestar.com/). This contradicts GitHub ([F]), so trust GitHub.
- **Storypencil** (`tool`, bundled Blender add-on). Built by the Grease Pencil team for storyboarding with the VSE: add, edit and render linked scenes. "Draw ▸ Setup Storyboard Session" (2D Animation template) creates the workspaces and scenes — [S] [Blender Manual 3.4 – Storypencil](https://docs.blender.org/manual/en/3.4/addons/sequencer/storypencil.html); design task — [S] [T100665](https://developer.blender.org/T100665); earlier GP storyboarding workflow task — [S] [T68321](https://developer.blender.org/T68321); demo video (`talk`/`tutorial`) — [S] [video.blender.org](https://video.blender.org/w/nmfHw6DoKztuA8WFKbp5B2)
  - Now on the Extensions platform as "Storypencil – Storyboard Tools". User reviews report it **broken with Grease Pencil 3 / Blender 4.3** — [S] [extensions.blender.org reviews](https://extensions.blender.org/add-ons/storypencil-storyboard-tools/reviews/). *Status for Blender 4.5/5.x unverified.*
- Community alternative: **greasy-boarding-blender** (`code-repo`), a Grease Pencil storyboarding add-on — [S] [github.com/marikodes/greasy-boarding-blender](https://github.com/marikodes/greasy-boarding-blender) (maintenance not checked)
- Paid add-on: **Storyboard & Animatic** (Ed White), docs and Gumroad — [S] [gitbook docs](https://edwardswhite.gitbook.io/storyboard-animatic); [S] [Gumroad](https://edwhite3d.gumroad.com/l/StoryboardAnimatic) (price not captured)
- Blender Studio pipeline treats "storyboard" and "previz" as Kitsu task types that Shot Builder creates collections for — [S] [Blender Kitsu docs](https://studio.blender.org/tools/addons/blender_kitsu)

#### D. Animatics / editorial
- **Blender VSE** (`tool`). In the Blender Studio pipeline, Shot Builder loads editorial exports into each shot file's VSE, and Render Review and Contact Sheet run in the VSE — [S] [Blender Kitsu docs](https://studio.blender.org/tools/addons/blender_kitsu); [S] [Contact Sheet](https://studio.blender.org/tools/addons/contactsheet)
- **Kdenlive** (`tool`, GPL-3.0, MLT-based, Qt/KF6). Very active (24k+ commits) — [F] [github.com/KDE/kdenlive](https://github.com/KDE/kdenlive); site [kdenlive.org](https://kdenlive.org)
- **Shotcut** (`tool`, GPLv3, MLT-based). Actively built for Linux, macOS and Windows — [F] [github.com/mltframework/shotcut](https://github.com/mltframework/shotcut); site [shotcut.org](https://www.shotcut.org)
- **OpenTimelineIO** (`code-repo`/`documentation`, Apache-2.0). The "interchange format and API for editorial cut information" (C++ with Python bindings). Adapters for FCP XML, AAF and CMX3600 EDL now ship as separate PyPI plugin packages — [F] [github.com/AcademySoftwareFoundation/OpenTimelineIO](https://github.com/AcademySoftwareFoundation/OpenTimelineIO); docs [opentimelineio.readthedocs.io](https://opentimelineio.readthedocs.io/), site [opentimeline.io](http://opentimeline.io/). Latest release seen: v0.18.1. The release page's date text is inconsistent ("Beta 18 – November 2025" listed with a 2024 date), so verify — [F] [releases](https://github.com/AcademySoftwareFoundation/OpenTimelineIO/releases)
- DaVinci Resolve (free): not verified in this session (see Gaps).

#### E. Previs / layout
- Shot Builder creates per-shot `layout` and `previz` task files and links layout output collections into anim and lighting via the shot-assembly spec — [S] [Shot Assembly](https://studio.blender.org/tools/pipeline-overview/shot-production/shot-assembly)
- No sourced material found on lens choices for painterly or graphic framing (see Gaps).

#### F. Production tracking
- **Kitsu** (CGWire) (`tool`, AGPL). A production tracker for animation, VFX and games covering tasks, asset review and collaboration — [S] [GitHub org cgwire](https://github.com/cgwire). **Very actively maintained:** releases v1.0.64 → v1.0.68 shipped 22–29 September (2026 inferred from current date) — [F] [github.com/cgwire/kitsu/releases](https://github.com/cgwire/kitsu/releases)
  - "Kitsu v1.0.0 was officially released in 2025" — [S] (search summary drawing on CGWire blog; exact date unverified)
  - June 2026 update covers **Project Templates** (spin up productions from predefined task types/statuses) and a "Sustainable AI Manifesto" — [S] [CGWire blog, June 2026](https://blog.cg-wire.com/build-in-public-june-2026-update/); earlier: [S] [Dec 2025 update](https://blog.cg-wire.com/build-in-public-december-2025-update/)
  - **Zou** (backend API, AGPL-3.0, Python/Flask, 5.8k commits) stores projects, shots, assets, tasks and file metadata, and generates file paths. Docs [zou.cg-wire.com](https://zou.cg-wire.com), API spec [api-docs.kitsu.cloud](https://api-docs.kitsu.cloud). **Gazu** is the Python client for pipeline scripts — [F] [github.com/cgwire/zou](https://github.com/cgwire/zou)
  - CGWire comparison pages (vendor marketing): [S] [vs ShotGrid](https://www.cg-wire.com/shotgrid-alternative/), [S] [vs ftrack](https://www.cg-wire.com/ftrack-alternative/)
  - Older overviews: [S] [CG Channel 2019](https://www.cgchannel.com/2019/02/check-out-open-source-production-tracking-tool-kitsu/)
- **Prism Pipeline 2** (`tool`, LGPL-3.0 free tier). The free plan covers Blender, Houdini, Maya, Nuke, Photoshop, After Effects, C4D, Deadline, 3ds Max and PureRef, "for free in commercial and non-commercial projects". USD, Unreal and ZBrush plugins are paid (Plus €19/user/mo or €180/yr, ≤15 users; Pro €45/user/mo or €468/yr) — [S] [Prism licensing docs](https://prism-pipeline.com/docs/latest/general/licensing/); [S] [CG Channel, Prism 2.0](https://www.cgchannel.com/2023/11/prism-2-0/); [S] [Digital Production 2024](https://digitalproduction.com/2024/04/19/prism-pipeline-the-second/); repo — [F] [github.com/PrismPipeline/Prism](https://github.com/PrismPipeline/Prism) (399 stars; docs [prism-pipeline.com/docs/latest](https://prism-pipeline.com/docs/latest/))
- **AYON** (Ynput, formerly OpenPype) (`tool`). A full pipeline platform connecting DCCs, publishing and tracking — [S] [CG Channel launch 2023](https://www.cgchannel.com/2023/08/ynput-launches-free-vfx-and-animation-pipeline-platform-ayon/); [S] [AYON 1.0 (Jan 2024)](https://www.cgchannel.com/2024/01/ynput-releases-ayon-1-0/); [S] [befores & afters intro](https://beforesandafters.com/2024/04/17/introducing-ayon-advancing-creative-workflows-for-animation-and-vfx-pipelines/)
  - **License change:** the AYON *server* (two main server repos) is moving to the **Functional Source License (Fair Source)**. ayon-core, the launcher, the Python API and all DCC integrations stay Apache-2.0 — [S] [ayon.app blog](https://ayon.app/blog/ayon-server-is-adopting-fair-source)
  - Blender integration **ayon-blender** (Apache-2.0, ~1.6k commits on develop, active) — [F] [github.com/ynput/ayon-blender](https://github.com/ynput/ayon-blender); company [ynput.io](https://ynput.io/)

#### G. Version control for art
- **SVN + Blender SVN add-on** (Blender Studio's choice) — [S] [Blender SVN](https://studio.blender.org/tools/addons/blender_svn); [S] [Using SVN](https://studio.blender.org/tools/user-guide/svn)
- **Git LFS** (`tool`). "Git extension for versioning large files" (Go, prebuilt binaries); the repo includes a `locking` component — [F] [github.com/git-lfs/git-lfs](https://github.com/git-lfs/git-lfs); site [git-lfs.com](https://git-lfs.github.com). The Blender Studio docs list SVN, Git LFS and Perforce as options — [S] [Pipeline Setup](https://studio.blender.org/tools/pipeline-overview/quick-start/setup)
- **Perforce P4** (formerly Helix Core). "Free for up to 5 users and 20 workspaces", self-hosted. P4 Cloud is ~$39/user/mo (snippet) — [S] [perforce.com free version control](https://www.perforce.com/products/helix-core/free-version-control); rename — [S] [Re-Introducing P4](https://www.perforce.com/blog/vcs/introducing-the-p4-platform)
- **Anchorpoint** (`tool`, Git-based with file locking, built for artists). Personal = free, non-commercial, single user. Team ≈ €20/user/mo annual (€25 monthly), with a 50% indie discount (pricing via third-party summary) — [S] [Anchorpoint blog: version control for artists](https://www.anchorpoint.app/blog-topics/version-control); [S] [Anchorpoint: Perforce alternative](https://www.anchorpoint.app/blog/perforce-alternative-for-game-development); [S] [itechguides comparison](https://www.itechguides.com/compare/anchorpoint-game-version-control-system-vs-git/)
- **Diversion** (`tool`, cloud VCS pitched against Perforce/Git/SVN). Free "Indie" tier (snippet: up to 10 users, 100 GB); Pro from $25/user/mo — [S] [diversion.dev](https://www.diversion.dev/). *Free-tier limits unverified; check the pricing page.*

#### H. Rendering infrastructure
- **Flamenco** (`tool`, open source, Blender Studio). Three parts: a Blender add-on, a Manager (web UI that distributes jobs) and Workers — [S] [flamenco.blender.org](https://flamenco.blender.org/)
  - Latest stable **3.9.3**, experimental **3.10-beta1** ("do not run this on production systems"); binaries for Windows, Linux, macOS Intel and Apple Silicon; the add-on downloads from the Manager web UI — [S] [Flamenco download page](https://flamenco.blender.org/download/)
  - v3.7 added on-demand job-compiler script loading and FFmpeg 7.0 — [S] [Blender on Mastodon](https://mastodon.social/@Blender/114273589204626771); upgrade guide — [S] [Upgrading Flamenco](https://flamenco.blender.org/usage/upgrading/)
  - Background — [S] [Announcing Flamenco 3](https://studio.blender.org/blog/announcing-flamenco-3-release/); [S] ["Easier than ever" release](https://studio.blender.org/blog/new-release-of-flamenco-easier-than-ever/); 2026 self-hosting tutorial (`tutorial`) — [S] [CGWire blog: Self-Hosting a Blender Render Farm Using Flamenco in 2026](https://blog.cg-wire.com/self-hosted-blender-render-farm/); cloud GPU example — [S] [LeaderGPU guide](https://www.leadergpu.com/catalog/588-blender-remote-rendering-with-flamenco)
- **SheepIt** (`tool`, free community render farm, Blender only)
  - Terms of use: run the worker only on machines you own or have permission for. Multi-accounting, cheating clients and NSFW projects are abuse. No liability for damage or data loss — [S] [Terms of use](https://www.sheepit-renderfarm.com/termsofuse)
  - FAQ: SheepIt "does not lay any claim to generated images"; the project owner keeps all rights (as long as they hold the asset rights). Unlimited projects, but only **3 rendering at once**. No NSFW because there is no minimum age — [S] [FAQ](https://www.sheepit-renderfarm.com/faq)
  - Points: earn ~38 points per minute rendering for others and spend ~10 per minute of your own renders (third-party article) — [S] [GameDev.tv article](https://gamedev.tv/articles/using-sheepit-render-farm)
  - **Caveat (biased sources):** competitors say SheepIt is unsuitable for client, NDA or pre-release work because files render on volunteer machines — [S] [RenderStreet vs SheepIt (competitor)](https://render.st/renderstreet-vs-sheepit/); [S] [GarageFarm comparison (competitor)](https://garagefarm.net/blog/blender-render-farms-comparing-sheepit-and-garagefarm-net-for-every-3d-artists-needs). I found no SheepIt clause that **prohibits** commercial use. The confidentiality risk is inherent, not contractual.
- **CrowdRender** (`tool`, free add-on). Peer-to-peer distributed rendering across machines with no separate server; suits ~2–20 machines — [S] [crowd-render.com October update](https://www.crowd-render.com/single-post/october-update-for-our-3d-rendering-distributed-rendering-plugin-for-blender); [S] [BlenderNation dev update (Aug 2023)](https://www.blendernation.com/2023/08/07/development-update-for-crowdrender/); [S] [v0.4.1 release thread](https://blenderartists.org/t/faster-cycles-rendering-v0-4-1-of-crowdrender-released/1331807). A search summary says Blender 5.0 support is "in development" and quotes "2025 wasn't kind". **Treat as slow-moving / at-risk.** Exact source page unverified.
- Paid cloud farms (summary only): [GarageFarm](https://garagefarm.net/blog/blender-render-farms-comparing-sheepit-and-garagefarm-net-for-every-3d-artists-needs), [RenderStreet](https://render.st/renderstreet-vs-sheepit/), [Fox Renderfarm](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/); 2026 comparison of free tiers — [S] [superrendersfarm "Free Render Farms Compared (2026)"](https://superrendersfarm.com/article/free-render-farms-compared-2026) (vendor content; prices not captured)

#### I. Review / playback
- Kitsu has built-in review. Blender Studio uses **Render Review** + **Contact Sheet** in the VSE — [S] [Pipeline Usage](https://studio.blender.org/tools/pipeline-overview/quick-start/usage); [S] [Contact Sheet](https://studio.blender.org/tools/addons/contactsheet)
- **Open RV** (`code-repo`). An open-source version of Autodesk RV (Sci-Tech award), "high-performant, hardware accelerated, and pipeline-friendly". You must **build it from source** (macOS 13+, Windows 10+, Rocky 8/9) — [F] [github.com/AcademySoftwareFoundation/OpenRV](https://github.com/AcademySoftwareFoundation/OpenRV); [S] [ASWF news](https://www.aswf.io/news/openrv/); [S] [Autodesk FAQ](https://www.autodesk.com/support/technical/article/caas/sfdcarticles/sfdcarticles/RV-Open-Source-Frequently-Asked-Questions.html)
- **xSTUDIO** (DNEG, Apache-2.0) (`code-repo`). Playback and review for VFX and feature animation; v1.3.0 per README; build guides for Linux, Windows and macOS (prebuilt binaries not evident) — [F] [github.com/AcademySoftwareFoundation/xstudio](https://github.com/AcademySoftwareFoundation/xstudio); [S] [Cartoon Brew](https://www.cartoonbrew.com/tools/dneg-xstudio-open-source-tracking-review-software-225138.html); [S] [AWN](https://www.awn.com/news/dneg-releases-open-source-xstudio-playback-and-review-application)
- ASWF **Open Review Initiative** (umbrella for OpenRV, xSTUDIO and SPI's itview) — [S] [aswf.io/openreviewinitiative](https://www.aswf.io/openreviewinitiative/)

#### J. Asset management, linking & overrides
- Blender Studio Asset Pipeline (task layers per file; Asset Builder/Updater) and "Creating Your First Asset" — [S] [Asset Pipeline](https://studio.blender.org/tools/addons/asset_pipeline); [S] [Creating Your First Asset](https://studio.blender.org/tools/artist-guide/project_tools/usage-asset)
- Shot Builder loads assets via `asset_index.json` and links output collections between task files — [S] [Blender Kitsu docs](https://studio.blender.org/tools/addons/blender_kitsu)

#### K. Learning references (free unless noted)
- Blender Studio pipeline docs (all of Q1) — `documentation`
- Storypencil demo — [S] [video.blender.org](https://video.blender.org/w/nmfHw6DoKztuA8WFKbp5B2) (`tutorial`)
- "Building a Blender pipeline in 30 Minutes" — [S] [ACM DL](https://dl.acm.org/doi/10.1145/3721251.3742867) (`talk`, details unverified)
- CGWire's Flamenco 2026 self-hosting guide — [S] [blog.cg-wire.com](https://blog.cg-wire.com/self-hosted-blender-render-farm/) (`tutorial`)
- Arcane S2 texturing video, "Animating the hand-painted look" (publisher unverified) — [S] [YouTube gCJIJG6Lz84](https://www.youtube.com/watch?v=gCJIJG6Lz84) (`talk`)
- Production logs and project files: Blender Studio subscription (see Q4)

#### L. Legal / licensing practicalities
- Blender Studio content is generally **CC-BY** (© Blender Foundation). Each asset shows its license snippet, and you "can freely reuse and distribute this content, also commercially, as long you include proper attribution" — [S] [studio.blender.org/remixing](https://studio.blender.org/remixing/); per-project examples: [S] [Coffee Run licensing (CC BY 4.0)](https://studio.blender.org/projects/coffee-run/pages/licensing/), [S] [Wing It! licensing](https://studio.blender.org/projects/wing-it/pages/licensing/)
- **Exception:** the Agent 327 film file is **CC-BY-ND** (no derivatives). Always check each asset's license line — [S] [Agent 327 CC-BY-ND post](https://studio.blender.org/blog/agent-327-film-file-released-as-cc-by-nd/)
- Mixed-license Blender products (marketplace guidance; the GPL code vs. asset distinction) — [S] [Superhive: mixed licenses](https://support.superhivemarket.com/article/297-using-mixed-licenses-for-blender-products); [S] [Superhive licensing options](https://support.superhivemarket.com/article/54-available-licensing-options)
- SheepIt claims no rights to rendered output — [S] [SheepIt FAQ](https://www.sheepit-renderfarm.com/faq)
- Tool licenses relevant if you redistribute or modify: Kitsu/Zou **AGPL-3.0** (network-use copyleft applies if you modify and host for others) [F] [zou](https://github.com/cgwire/zou); AYON server **FSL** vs integrations **Apache-2.0** [S] [ayon.app](https://ayon.app/blog/ayon-server-is-adopting-fair-source); Prism **LGPL-3.0** [F] [Prism repo](https://github.com/PrismPipeline/Prism)

### Inferences
- **Recommended indie FOSS stack (1–10 people):**
  1. Story Architect → `.fountain` in VCS.
  2. Krita for visdev and color scripts.
  3. Blender Grease Pencil boards in the VSE, kept inside Blender so boards → animatic → layout share one file lineage. Verify Storypencil on your Blender version, or use plain GP scenes plus VSE scene strips.
  4. Blender VSE animatic, exported via OTIO/EDL if an external editor is used.
  5. Kitsu (Docker) + Blender Kitsu add-on.
  6. SVN + Blender SVN add-on, *or* Git LFS. Perforce's free tier only if ≤5 users.
  7. Flamenco on the team's own GPUs.
  8. Review in Kitsu plus the Render Review add-on.
  - This mirrors the Blender Studio setup, which is the best-documented open Blender pipeline.
- **Maintenance/risk summary:**
  - *Abandoned / at-risk:* Storyboarder; KIT Scenarist (officially replaced); CrowdRender.
  - *Compatibility-risk:* Storypencil (GP3).
  - *Active:* Kitsu, Flamenco, Krita, Kdenlive, Shotcut, Trelby, Story Architect, ayon-blender, Prism.
  - *License shift to watch:* AYON server (FSL).
- AYON is the most capable but heaviest option and is overkill for a Blender-only short. Prism is lighter, file-system-based, and free for Blender. Kitsu fits best with the Blender Studio add-ons.
- OpenRV and xSTUDIO require self-compiling, which is a real cost for a small team. Kitsu review plus the Blender VSE is usually enough for a short.

### Gaps
- Could not verify (search budget exhausted, sites blocked):
  - DaVinci Resolve free-tier limits;
  - Blender Manual pages on Asset Browser, asset libraries and library overrides (no URL captured this session);
  - USD import/export status in Blender 4.x/5.x;
  - Kitsu cloud pricing;
  - Procreate/Procreate Dreams pricing;
  - camera/lens guidance for painterly framing.
- The following official URLs are **known from prior knowledge but NOT verified in this session**; the writer should confirm before publishing: DaVinci Resolve (blackmagicdesign.com/products/davinciresolve), Blender Manual library overrides (docs.blender.org/manual/en/latest/files/linked_libraries/library_overrides.html), Blender Manual asset libraries (docs.blender.org/manual/en/latest/files/asset_libraries/index.html), Kitsu docs (kitsu.cg-wire.com), Storyboarder home (wonderunit.com/storyboarder), Final Draft (finaldraft.com), Procreate (procreate.com).
- No free books/PDFs on animation production pipelines were found and verified in this session.
- No specific Blender Conference or Annecy talk URLs on indie short production were captured (besides the ACM entry and the Storypencil video).
- No font or music licensing sources captured (general pointers only, e.g. SIL Open Font License and CC music libraries — **unsourced**).
- Diversion and Anchorpoint free-tier numbers come from third-party or snippet text; confirm on the vendors' pricing pages.

---

## Q3. How did Fortiche (Arcane) and Alberto Mielgo structure pre-production/visual development (color scripts, concept-to-3D)?

### Takeaway
**Fortiche** front-loads pre-production. It spent about a year of visdev on Piltover (shape language, colors, materials) and builds color direction from director-selected mood boards into color keys and scripts that are paced across episodes. It locks story heavily at the storyboard stage and keeps all departments in-house. Concept paintings become direct references for modelers and texture artists, who **hand-paint and project textures** onto 3D. In S2, some simulated FX were **repainted frame by frame**.
**Mielgo** (Pinkman.TV) works as a painter-director. On *The Windshield Wiper* he **painted every background himself in Photoshop**, and the team keyframed 3D characters into those paintings ("2D background with a 3D character", "the old Disney technique"). On *Jibaro* he mixed full 3D environments with heavily painted shots and 2D post work. He drew the storyboard drafts on paper, then colored them and placed them into 3D scenes. He deliberately removes unneeded detail ("more impressionism than realism").

### Cited Findings

**Fortiche / Arcane**
- About a year of visual development of Piltover, focused on shape language, colors and materials. Development artist **Anne-Laure To** worked on the color script and color keys — [S] [Playgrounds speaker page: Fortiche (Anne-Laure To)](https://weareplaygrounds.nl/slot/fortiche-anne-laure-to/)
- The color palette and lighting approach is "a combination of intuition and visual references carefully selected with the directors from the mood board phase". The aim is a coherent dynamic across episodes and seasons that deliberately alternates darker moments with high-contrast sequences and allows foreshadowing between episodes — [S] [VFX Voice: Arcane S2](https://vfxvoice.com/riot-games-and-fortiche-get-revolutionary-with-arcane-season-2/) / [S] [AWN: Arcane S2](https://www.awn.com/animationworld/riot-games-and-fortiche-push-every-possible-boundary-arcane-season-2). *The search summary merged these; which of the two contains the quote is unverified.*
- Fortiche "prioritizes locking things down early in the storyboarding process, spending significant time on this phase" so later steps are streamlined. Producers, directors, storyboard artists, animators, compositors and editors all work in-house — [S] [SyncSketch: interview with Alexis Wanneroy](https://blog.syncsketch.com/creator-stories/arcane-fortiche/) / [S] [AnimationXpress](https://www.animationxpress.com/animation/talent-experimentation-originality-how-fortiche-revolutionised-animated-storytelling-with-arcane/). *Again merged in the summary; exact attribution unverified.*
- Concept-to-3D: "Each episode began with concept artists painting Piltover and Zaun, defining color palettes and the painterly style". These paintings were references for 3D modelers and texture artists. Artists project hand-painted textures onto 3D assets with traditional-style brushes, deliberately adding shaky freehand lines, and add detail selectively where characters interact — [S] [YouTube: "Arcane S2 texturing: Animating the hand-painted look"](https://www.youtube.com/watch?v=gCJIJG6Lz84) (uploader unverified); see also [S] [daily.dev summary of the same video](https://daily.dev/posts/how-traditional-art-3d-combine-for-backgrounds-in-arcane-fntyfatwp)
- S2 pushed alternative looks (watercolour, charcoal, comic-style). Some FX began as Houdini/Maya simulations and were then **painted frame-by-frame** to match the painterly look — [S] [Creative Bloq on Arcane S2](https://www.creativebloq.com/art/2d-animation/how-the-creative-team-behind-netflixs-arcane-pushed-the-animation-even-further-for-the-second-season)
- Further reading: [S] [RedShark News: how Fortiche ramped up the pipeline](https://www.redsharknews.com/why-netflixs-arcane-looks-so-good-how-fortiche-ramped-up-the-animation-pipeline); [S] [3DVF interview](https://3dvf.com/en/arcane-how-does-it-feel-to-work-on-a-major-hit-series/); [S] [Fortiche (Wikipedia)](https://en.wikipedia.org/wiki/Fortiche); fan analysis (secondary) — [S] [Medium: Fortiche's design process](https://medium.com/@mellybea/currently-obsessed-with-fortiches-design-process-2d20a3bf00f0)

**Alberto Mielgo / Pinkman.TV**
- *The Windshield Wiper* (2021):
  - Mielgo painted all the detailed backgrounds in Photoshop. The animation team, led by **Leo Sanchez Barbosa**, keyframed 3D characters into the scenes ("2D background with a 3D character") — [S] [IndieWire interview](https://www.indiewire.com/awards/industry/the-windshield-wiper-animated-short-alberto-mielgo-interview-1234693351/); [S] [befores & afters Q&A](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/)
  - He paints the backgrounds to avoid hyperrealism: "being able to add realism in certain areas and avoid [it] in others, like adding realistic lighting but not being forced to be hyper real and show every single detail". He did all the paintings himself so the 3D characters would sit inside them — [S] [AWN](https://www.awn.com/animationworld/windshield-wiper-reveals-many-sides-modern-love); [S] [Cartoon Brew team interview](https://www.cartoonbrew.com/shorts/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html)
  - He calls the method "very traditional… the old Disney technique" of 2D backgrounds with characters — [S] (same search summary; one of the above sources); also [S] [Variety](https://variety.com/2021/artisans/markets-festivals/alberto-mielgo-windshield-wiper-1235017864/), [S] [Wikipedia](https://en.wikipedia.org/wiki/The_Windshield_Wiper)
- *Jibaro* (Love, Death + Robots Vol. 3, 2022):
  - It is "essentially a 3D film" with many shots painted like paintings. Some shots are fully built 3D forest with standard lighting; there is a lot of 2D in post. Character designs are simplified but keep realistic light physics. Mielgo picks the approach per shot and removes unneeded detail — [S] [80.lv: development process behind Jibaro](https://80.lv/articles/the-development-process-behind-love-death-robots-jibaro); [S] [SlashFilm interview](https://www.slashfilm.com/867120/love-death-and-robots-director-alberto-mielgo-talks-about-his-stunning-new-short-jibaro-interview/)
  - His style comes from years of painting: "more impressionism than realism" — [S] (same summary; SlashFilm/80.lv)
  - Pinkman.TV merges hand-drawn and CG imagery by layering textures (e.g., natural forest tones against the metallic armor and siren) — [S] [Peliplat article](https://www.peliplat.com/en/article/10009911/behind-the-creation-of-jibaro-in-love-death-robots)
  - "The director drew all the storyboard drafts himself on paper, scanned them into After Effects, colored them, and placed them in the corresponding 3D scenes" — [S] [Fox Renderfarm article](https://www.foxrenderfarm.com/share/techniques-behind-the-production-of-jibaro-love-death-and-robots/) (*secondary, vendor blog; verify against a primary interview*)
  - Other interviews: [S] [80.lv on creating LD+R episodes](https://80.lv/articles/alberto-mielgo-talks-specifics-of-creating-love-death-robots-short-episodes); [S] [GameRant](https://gamerant.com/interview-alberto-mielgo-love-death-and-robots-volume-3-jibaro-netflix/); [S] [AwardsDaily](https://www.awardsdaily.com/2022/06/26/alberto-mielgo-on-his-animated-short-jibaro-in-netflixs-love-death-robots/); [S] [Gold Derby video interview](https://www.goldderby.com/feature/alberto-mielgo-love-death-robots-jibaro-video-interview-1204988524/); crew artwork — [S] [Mariano Tazzioli, ArtStation](https://www.artstation.com/artwork/8wLQkR)

### Inferences
- **Transferable indie recipe:**
  1. Build a mood board with the director, then paint color keys and a color script in Krita, planning the contrast rhythm across the film as Fortiche does.
  2. Lock story at the board/animatic stage before building 3D.
  3. Treat the painted keys as binding references for modeling and texturing.
  4. Decide per shot whether the environment is (a) a full 3D painterly set (Brushstroke Tools / hand-painted projected textures) or (b) a single painted matte with 3D characters composited in (Mielgo/Windshield Wiper). Option (b) is far cheaper for a small team on locked-off shots.
- The Mielgo approach maps directly onto Blender: a camera-projected painted background plus a 3D character layer, with a 2D paint-over pass in post. This is cheaper than fully 3D painterly sets.

### Gaps
- No source captured on Mielgo's process for **The Witness** (Love, Death + Robots Vol. 1).
- No primary source (Fortiche artist talk transcript or Annecy masterclass) was read directly. All Fortiche and Mielgo claims are search-summary [S] level, and some quotes could not be pinned to a single article.
- No color-script images or page references from *The Art & Making of Arcane* (book) were verified.

---

## Q4. Paid tools/courses — one-line summaries + links

### Takeaway
For an indie short, paid tools are optional. The highest-value paid item is a **Blender Studio subscription** (≈€11.50/month per snippet; production files, logs and trainings). Industry trackers (Flow Production Tracking ≈$50/user/mo, ftrack Studio ≈$25–30/user/mo) and Storyboard Pro (≈$90/mo or $776/yr) are overkill unless a co-producer requires them.

### Cited Findings
- **Blender Studio subscription** (`course(paid)`). Production assets, production logs, unlimited trainings. A snippet gives €11.50/mo, $34.50 per quarter, and team plans "from $540/month". The numbers conflict across sources (one also says "$17/month"), so verify — [S] [studio.blender.org/join](https://studio.blender.org/join/); [S] [Blender Studio for Teams](https://studio.blender.org/teams/); third-party price tracker — [S] [subger.com](https://subger.com/en/service/blender-studio); terms — [S] [T&Cs](https://studio.blender.org/terms-and-conditions/)
- **Stylized Rendering with Brushstrokes** workshop (Project Gold), subscriber training — [S] [link](https://studio.blender.org/training/stylized-rendering-with-brushstrokes/)
- **Toon Boom Storyboard Pro**: industry storyboarding app. ≈$90/mo, $776/yr, $2,212 for 3 yrs; students ≈$11/mo or $90/yr (snippet) — [S] [Toon Boom shop](https://shop.toonboom.com/en/subscriptions/storyboard-pro); reseller — [S] [Novedge](https://novedge.com/products/buy-storyboard-pro-annual-subscription)
- **Autodesk Flow Production Tracking (ex-ShotGrid)**: enterprise tracker with RV included. ≈$50/user/mo (other listings say from $45). Annual and 3-year figures in snippets look inconsistent ($390/yr; $1,170 for 3 yrs), so verify — [S] [Shade review 2026](https://shade.inc/blog/autodesk-flow-production-tracking-for-post-production); [S] [Capterra](https://capterra.com/p/150447/Shotgun/)
- **ftrack Studio**: tracking, scheduling and review. ≈$25/user/mo annual or $30 monthly; Enterprise adds on-prem/SSO — [S] [G2 pricing](https://www.g2.com/products/ftrack/pricing)
- **Prism Plus / Pro**: paid USD/Unreal/ZBrush plugins. Plus €19/user/mo (≤15 users), Pro €45/user/mo — [S] [CG Channel](https://www.cgchannel.com/2023/11/prism-2-0/)
- **Perforce P4 Cloud**: hosted P4. ≈$39/user/mo (snippet) — [S] [perforce.com](https://www.perforce.com/products/helix-core/free-version-control)
- **Anchorpoint Team**: Git + locking UI for artists. ≈€20/user/mo annual, 50% indie discount (third-party summary) — [S] [itechguides](https://www.itechguides.com/compare/anchorpoint-game-version-control-system-vs-git/)
- **Diversion Pro**: cloud VCS, from $25/user/mo — [S] [diversion.dev](https://www.diversion.dev/)
- **Storyboard & Animatic (Blender add-on, Ed White)**: paid Gumroad add-on for GP boards and animatics (price not captured) — [S] [Gumroad](https://edwhite3d.gumroad.com/l/StoryboardAnimatic)
- **Story Architect premium**: optional paid cloud/pro features on top of the GPL app — [F] [starc repo (links starc.app/pricing)](https://github.com/story-apps/starc)
- **AYON paid services/add-ons**: core is free; Ynput earns from services and paid add-ons — [S] [CG Channel AYON 1.0](https://www.cgchannel.com/2024/01/ynput-releases-ayon-1-0/)

### Inferences
- If a paid item is needed, the Blender Studio subscription gives the most pipeline knowledge per euro (real production files and logs from Gold and other projects), especially for a Blender-based painterly short.

### Gaps
- Not captured or verified this session: Final Draft price; Procreate / Procreate Dreams price; DaVinci Resolve Studio price; Kitsu Cloud (hosted) price; paid courses outside Blender Studio (e.g., CG Spectrum, Schoolism, CGMA visdev/color-script courses). Search budget was exhausted before these could be researched.
