# Sound Design, Foley, Music & Audio Post for an Indie Stylized Animated Short (as of Oct 2026)

> **Research conditions (read first).** This session ran with heavy network limits. Most sites could not be opened directly (asoundeffect.com, indiewire.com, studio.blender.org, freesound.org, ardour.org, docs.blender.org, reaper.fm, blackmagicdesign.com, partnerhelp.netflixstudios.com, tech.ebu.ch, plugins.iem.at, pianobook.co.uk, gdcvault.com and others all returned "EGRESS_BLOCKED"). The shared web-search budget also ran out partway through.
> - **[verified-page]**: I opened the primary page itself. In this session that was only possible on github.com.
> - **[search-summary]**: the claim comes from a search-engine summary of the linked page. The URL is real (it was returned by search), but I could not read the full text. Treat the wording as close to the page but not quoted.
> - **[unverified]**: background knowledge with no source opened in this session. It is listed only in Gaps and must be checked before publishing.
> - One example of why this matters: a search summary dated LMMS 1.3.0-alpha.2 to "September 6, 2026". GitHub shows the real date is **September 6, 2024**. Dates that come only from search summaries should be treated with caution.
>
> Category tags: `[documentation]` `[tutorial]` `[tool]` `[asset-library]` `[course(paid)]` `[talk]` `[interview]`

---

## Q1. What is publicly documented about the sound approach of Arcane, Jibaro, The Witness, The Windshield Wiper and Blender Studio open movies?

### Takeaway
All of these productions build their stylized sound from **organic, often homemade recordings that are then heavily processed**. Arcane's Hextech sound started as rubbed wine glasses and its Shimmer sound as animal and human vocals. Mielgo recorded Jibaro's armor with kitchen utensils on an iPhone. The Windshield Wiper's café chatter came from staged dinner conversations. In every case music and sound were designed together, not handed off one after the other. Blender Studio is the indie-scale counterpart: a small in-house team (Sander Houtman and others) assembled much of the sound inside Blender's own sequencer, and the studio documents its OpenTimelineIO export path.

### Cited Findings

#### Arcane (Fortiche / Riot Games, Netflix; S1 2021, S2 2024)
- `[interview]` A Sound Effect's long-form piece "How Arcane's Sonic Magic Is Made" (by Jennifer Walden) interviews sound designers **Eliot Connors** and **Brad Beaumont** and composer **Alexander Temple** (Riot Games). It covers the sounds of Hexite, Hextech, magic, Shimmer, and the steampunk, gear-driven worlds of Zaun and Piltover, and how music and sound design were made to fit together. [search-summary] — [A Sound Effect](https://www.asoundeffect.com/arcane-sound/) (forum mirrors: [Gearspace](https://gearspace.com/threads/how-arcanes-sonic-magic-is-made-with-composer-alexander-temple-more.1368125/), [VI-Control](https://vi-control.net/community/threads/how-arcane%E2%80%99s-sonic-magic-is-made-interview-with-composer-alexander-temple-more.118768/))
- `[interview]` Connors and Beaumont describe building sound from **organic material**:
  - **Hextech** came from **wine glasses**. Rubbing the rim makes the glass "sing", and those recordings were processed into a full library, then mixed with instruments and synths that Beaumont had assembled.
  - **Shimmer** used many **animal and human vocals**.
  - [search-summary] — [AwardsDaily, 16 Aug 2022](https://www.awardsdaily.com/2022/08/16/brad-beaumont-and-eliot-connors-interview/)
- `[interview]` Further Emmy-season craft coverage of S1 sound editing: [IndieWire – Emmys 2022: Arcane Best Sound Editing](https://www.indiewire.com/awards/industry/emmys-2022-arcane-sound-editing-1234749817/), and the related syndication ["How 'Arcane' Broke the Video Game Curse One Sound at a Time" (Yahoo)](https://www.yahoo.com/entertainment/arcane-broke-video-game-curse-163048060.html). [search-summary]
- `[interview]` SoundWorks Collection made a featurette and podcast, "The Sound & Music of Arcane: League of Legends". [search-summary] — [SoundWorks Collection](https://soundworkscollection.com/post/the-sound-music-of-arcane-league-of-legends); [podcast version](https://creators.spotify.com/pod/profile/soundworkscollection/episodes/The-Sound--Music-of-Arcane-League-of-Legends-e1cg63k)
- `[talk]` **Tonebenders episode 313, "The Sound Design & Music Of Arcane Season 2"** (published 15 Jun 2025, 56 min, recorded at the Riot Games campus). Supervising sound editors Eliot Connors and Brad Beaumont talk with composers Alex Seaver and Alex Temple about how each discipline shaped the others. They cover how the musical themes evolved, why the sound design "had to be based in organic sounds", and their goal of making the sound match the visuals. [search-summary] — [Tonebenders 313](https://tonebenderspodcast.com/313-the-sound-design-music-of-arcane-season-2/); [Apple Podcasts](https://podcasts.apple.com/ie/podcast/313-the-sound-design-music-of-arcane-season-2/id599310888?i=1000712776735)
- `[talk]` **Tonebenders episode 309, "The Mix Team For Arcane Season 2"**. [search-summary] — [Tonebenders 309](https://tonebenderspodcast.com/309-the-mixing-team-for-arcane-season-2/); [YouTube](https://www.youtube.com/watch?v=_lD6_i4vLDQ)
- `[interview]` Season 2 re-recording mixers **Penny Harold** and **Andy Lange** split the work:
  - Harold mixes dialogue, loop group and music. Lange mixes sound effects, backgrounds and Foley.
  - They work **offline from each other on their own pre-dubs at the same time**, then join up to combine everything.
  - The mixers describe the show as having intense dialogue, massive sound design, soaring songs and a bombastic score.
  - [search-summary] — [ScreenRant](https://screenrant.com/arcane-re-recording-mixer-penny-harold-mixer-andy-lange-on-building-the-series-finale-through-sound/); [CineMontage](https://cinemontage.org/arcane-sound-mixers-penny-harold-and-andy-lange-on-pushing-the-limits-of-sound-in-animated-tv/)
- `[interview]` Season 2 sound craft piece: ["'Arcane' Season 2 Sound Gives 'League of Legends' Heart, Grit, Songs" (IndieWire)](https://www.indiewire.com/features/craft/arcane-season-2-sound-league-of-legends-songs-interview-netflix-1235065216/). [search-summary; full text not read]
- `[interview]` The music credits name **Alexander Temple, Andrew Kierszenbaum and Alex Seaver (Mako)**. Seaver co-composed the S2 score and was **executive music producer** on the S2 soundtrack. He also discussed working with Twenty One Pilots. [search-summary] — [What's on Netflix](https://www.whats-on-netflix.com/news/interviews/alex-mako-seaver-breaks-down-the-iconic-arcane-season-2-soundtrack/); [Sound of Life](https://www.soundoflife.com/blogs/people/alex-seaver-arcane-interview); [ScreenRant (Seaver & Temple)](https://screenrant.com/arcane-season-2-greatest-moments-explained-composers-alex-seaver-alexander-temple-interview/); [ScreenRant (Seaver)](https://screenrant.com/arcane-season-2-music-producer-songwriter-composer-alex-seaver-interview/); [Temple of Geek SDCC](https://templeofgeek.com/interview-arcane-composer-alex-seaver-at-san-diego-comic-con/); [Winter is Coming](https://winteriscoming.net/arcane-executive-music-producer-alex-seaver-mako-takes-us-inside-the-epic-soundtrack-for-season-2-01jdjaw68xp0)
- `[documentation]` Eliot Connors has a Wikipedia entry. — [Wikipedia: Eliot Connors](https://en.wikipedia.org/wiki/Eliot_Connors)

#### Jibaro (Love, Death & Robots Vol. 3, 2022; dir. Alberto Mielgo)
- `[interview]` Mielgo explains why the sound matters so much: "There is no dialogue, so I needed to show visually what the spell does to people. The sound is sort of obnoxious… but it physically controls your body and it makes you loop, dance, and kill everything around you." The siren's voice is deliberately *unpleasant*, which reverses the usual beautiful siren song. [search-summary] — [Deadline, Jun 2022](https://deadline.com/2022/06/alberto-mielgo-love-death-robots-jibaro-animation-dialogue-1235039230/)
- `[interview]` Asked how he made the armor sounds, Mielgo said: "Forks and spoons and old kitchen apparel." [search-summary] — [AwardsDaily, 26 Jun 2022](https://www.awardsdaily.com/2022/06/26/alberto-mielgo-on-his-animated-short-jibaro-in-netflixs-love-death-robots/)
- `[interview]` "All the armor sounds are knives, pans, forks and everything that I was able to find in my kitchen." Everything was **recorded on Mielgo's iPhone**, which he chose for its sound quality and convenience while traveling. [search-summary; secondary report of the interviews] — [80.lv](https://80.lv/articles/sounds-of-armor-for-jibaro-were-recorded-using-kitchen-utensils)
- `[documentation]` IMDb sound credits for Jibaro. IMDb is user-contributed, so verify before quoting. [search-summary] — [IMDb full credits](https://www.imdb.com/title/tt20239442/fullcredits/)

  | Role | Name |
  |---|---|
  | Sound supervisor | Brad North |
  | Re-recording mixers | Chris Carpenter, Joe DeAngelis |
  | Sound designer | **Alberto Mielgo** |
  | Foley artist | Zane D. Bruce |
  | Recordist | Albert Romero |
  | Foley editor / mixer | Antony Zeller |

- `[interview]` Brad North is the supervising sound editor for the *Love, Death & Robots* series. [search-summary] — [Krotos interview](https://sound.krotosaudio.com/brad-north-supervising-sound-editor-interview/); [Krotos: How Krotos helped shape LD+R sound](https://www.krotosaudio.com/love-death-robots-sound-design/); [Formosa Group feature](https://formosagroup.com/supervising-sound-editor-brad-north-and-team-talk-about-their-emmy-award-winning-work-on-the-love-death-robots-series/); [Avid Emmy profile](https://connect.avid.com/Emmys_Bradley-North-MPSE.html)
  - He has 22+ years of experience (Stranger Things, Watchmen, and others) and used the **Krotos Everything Bundle** on LD+R.
  - The series won an **Emmy for Outstanding Sound Editing for an Animated Program in 2025**. That year was a later volume, not Jibaro's.
- `[documentation]` Collider describes Jibaro as the "double Emmy-winning episode" with **music by electronic artist Killawatt**. It won short-form animation and individual achievement in animation at the 2022 Creative Arts Emmys. [search-summary] — [Collider](https://collider.com/love-death-and-robots-volume-3-soundtrack-songs/)
- `[documentation]` Critical analysis of the **deaf-POV sound**: when the film is with the knight, "the forest is eerily silent, with only muffled rumbles", set against the siren's song and the screams of men and horses. The screams are sometimes muted and mixed with silence. Analysts describe the technique as using silence to put the viewer inside the knight's perception. [search-summary; secondary/critical, not production statements] — [SlashFilm](https://www.slashfilm.com/869884/if-you-watch-just-one-love-death-robots-short-make-it-jibaro/); [UVic audio blog – "The Greatness of Silence"](https://uvicaudio.wordpress.com/2023/04/13/love-death-robots-jibaro-the-greatness-of-silence/); [onderhond review](https://www.onderhond.com/blog/jibaro-review-alberto-mielgo)
- `[documentation]` The siren's movement was performed by dancer **Megan Goldstein** as live reference. [search-summary] — [80.lv – Jibaro animations vs real-life references](https://80.lv/articles/jibaro-animations-vs-real-life-references). More behind-the-scenes coverage: [Peliplat](https://www.peliplat.com/en/article/10009911/behind-the-creation-of-jibaro-in-love-death-26-robots)
- `[tutorial]` Third-party video essay, "Alberto Mielgo – The Art of Messy Sound Design", analyzes Mielgo's sound across his films. [search-summary] — [YouTube](https://www.youtube.com/watch?v=Bx-t6FzcNVc)
- `[documentation]` A Sound Effect's Emmy 2022 roundup covers the sound stories behind 14 sound editing and mixing nominees. [search-summary] — [A Sound Effect](https://www.asoundeffect.com/emmy-2022-sound-mixing-editing-nominees/)

#### The Witness (Love, Death & Robots Vol. 1, 2019; dir. Mielgo)
- `[documentation]` Music by **Rob Cairns**, music supervisor **Ben Sokoler**. Licensed tracks include **"Ox1" by Tommy Four Seven** and **"4101" by Roly Porter**, both hard-edged electronic and industrial artists. [search-summary; IMDb is user-contributed] — [IMDb soundtrack](https://www.imdb.com/title/tt9788486/soundtrack/); [IMDb full credits](https://www.imdb.com/title/tt9788486/fullcredits/); [Tunefind S1](https://www.tunefind.com/show/love-death-robots/season-1/79386)
- `[documentation]` The episode won three Emmys and an Annie. [search-summary] — [Wikipedia: Alberto Mielgo](https://en.wikipedia.org/wiki/Alberto_Mielgo)

#### The Windshield Wiper (2021; Oscar winner, Best Animated Short)
- `[interview]` Mielgo was **director, screenwriter, editor, sound designer and composer**.
  - Music includes a track by LA artist **Lera Pentelute** and one by **Soko**.
  - For the café conversations, Mielgo **invited three men to dinner and asked them six specific questions**. On another day he asked **three women the same six questions**, so the improvised talk would hit specific story moments.
  - [search-summary] — [Cartoon Brew](https://www.cartoonbrew.com/interviews/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html)
- `[documentation]` Credits: sound designer **Alberto Mielgo**, re-recording mixer **Jack Goodman**; music by Mielgo, Lera Pentelute and Soko. [search-summary] — [Wikipedia](https://en.wikipedia.org/wiki/The_Windshield_Wiper); [IMDb full credits](https://www.imdb.com/title/tt9464038/fullcredits/)
  - Track names cited in one summary: Pentelute "When In Gloom", Mielgo "Pianillo Dos", Soko "We Might Be Dead by Tomorrow". This is **[unverified]**: it appeared next to an AI-encyclopedia source ([Grokipedia](https://grokipedia.com/page/The_Windshield_Wiper)) and needs checking against IMDb or the film's end credits.
- `[interview]` Other interviews: [Variety (Cannes 2021)](https://variety.com/2021/artisans/markets-festivals/alberto-mielgo-windshield-wiper-1235017864/); [befores & afters Q&A](https://beforesandafters.com/2021/12/15/sometimes-the-characters-they-are-still-and-they-basically-breathe-a-little-bit-and-thats-good-enough/); [AWN](https://www.awn.com/animationworld/windshield-wiper-reveals-many-sides-modern-love); [IndieWire](https://www.indiewire.com/awards/industry/the-windshield-wiper-animated-short-alberto-mielgo-interview-1234693351/); [Gold Derby video](https://www.goldderby.com/feature/alberto-mielgo-the-windshield-wiper-director-video-interview-1204747223/); [AFA Podcast](https://creators.spotify.com/pod/profile/animation-for-adults/episodes/The-AFA-Podcast-Interview-Alberto-Mielgo-Director-The-Windshield-Wiper--2022-Oscar-Nominated-Short-e1fo7dk). [search-summary; sound content of these not read]

#### Blender Studio open movies
- `[documentation]` **Sprite Fright (2021)** sound design was by **Sander Houtman**. A search summary of studio.blender.org results also states that "a large chunk of sound design work was done in Blender, with more than **1500 audio files** assembled inside of the Blender Sequence Editor." [search-summary — I could not open the page to confirm which post says this; the likely source is the OTIO post below] — [Sprite Fright Premiere](https://studio.blender.org/blog/sprite-fright-premiere/); [Sprite Fright production logs](https://studio.blender.org/blog/introducing-sprite-fright-production-logs/); [Blender press page](https://www.blender.org/press/sprite-fright-open-movie/)
- `[documentation]` Blender Studio blog post **"OpenTimelineIO in Blender"**, which covers how the studio exchanged editorial and sound timelines. [title found by search; content not read] — [studio.blender.org](https://studio.blender.org/blog/opentimelineio-in-blender/)
- `[documentation]` **Project Gold** credits:
  - **Music: Dalal & Maesa.** Dalal Bruchmann composed and produced, and performed vocals, violin, organ and piano. Maesa Pullman sang. Jason Hiller produced, mixed and played percussion. David Goodstein played drums and percussion, with Emily Gregg (viola), Megan Shung (violin) and Mikala Schmitz (cello solo).
  - **Sound design: Sander Houtman, Cristo Pruppers, Hjalti Hjálmarsson.**
  - [search-summary] — [Project Gold Credits](https://studio.blender.org/projects/gold/pages/credits/); [Project Gold Premiere](https://studio.blender.org/blog/project-gold-premiere/); [Production Log 04](https://studio.blender.org/blog/gold-production-log-04/); [Production Log 02 (video)](https://video.blender.org/w/1vpWXyLaQzQFGWeLzkHjh5); [Production Log 06 (YouTube)](https://www.youtube.com/watch?v=M788vUWI2Rk); [Storyboarding in Blender](https://studio.blender.org/blog/project-gold-storyboarding-in-blender/)
- `[documentation]` A third-party Patreon post describes Project Gold as a stylized-rendering showcase that "feels like a music video, complete with foley sound effects". [search-summary; third-party] — [Patreon](https://www.patreon.com/posts/project-gold-for-115660793)
- `[documentation]` Film index and context: [Blender Studio Films](https://studio.blender.org/films/); ["20 Years of Open Movies: What's Next?"](https://studio.blender.org/blog/20-years-of-open-movies-what-is-next/); ["Wing It!" Premiere Date](https://studio.blender.org/blog/wing-it-premiere-date/)

### Inferences
- **The common pattern is "organic source, then processing, then music-aware mix".** Arcane (wine glasses, vocals), Jibaro (kitchen utensils on an iPhone) and The Windshield Wiper (staged dinner conversations) all start from cheap, real recordings. For an indie short, that suggests spending on *recording time and creative processing*, not on large commercial libraries.
- **A single author can carry the sound.** Mielgo is credited as sound designer on both Jibaro and The Windshield Wiper, with a professional mixer finishing (Jack Goodman on Wiper; Formosa/Brad North's team on Jibaro). A practical indie model: the director designs the sound, then hires a re-recording mixer only for the final mix.
- **Silence and perspective can tell the story.** Jibaro's deaf-POV approach (near-silence and muffled rumbles cut against piercing screams) shows a no-cost technique that stylized shorts can use when they have no dialogue.
- **Blender Studio shows that sound can live in the animation tool.** Assembling 1,500+ files in the VSE (if confirmed), with OTIO as the exchange path, means a no-budget team can keep sound editing in Blender until a dedicated DAW mix is needed.
- **Arcane's split pre-dubs** (dialogue and music on one side, effects, backgrounds and Foley on the other) can be copied at small scale by organizing stems early: DX / MX / SFX / BG / FOL.

### Gaps
- I found no **Netflix Tudum** article on Arcane or LD+R sound in this session (search budget ran out).
- The **sound-design credits for The Witness** (designer, mixers, Foley) were not found. Only the music credits were.
- **Imagine Dragons and the Arcane songs** ("Enemy" as the theme, with JID) could not be confirmed this session [unverified]. Neither could the Arcane S1/S2 Emmy and MPSE outcomes for sound.
- I could not confirm the **Jibaro siren's vocal performer or source**. One fan-wiki claim (Alina Smolyar) is low quality and not included. Whether Killawatt scored the whole episode or contributed specific tracks is unclear.
- **Charge (2022), Wing It! (2023), Spring and Coffee Run**: music and sound credits were not found (search budget exhausted). I could not confirm whether Blender Studio publishes **sound-design-specific logs or a downloadable SFX library**. The production files on Blender Studio may include audio, but this is unverified.
- I could not read whether the Arcane articles name specific plugins or DAWs (Pro Tools is industry standard but **[unverified]** for this show).

---

## Q2. What is a complete free/open-source audio pipeline for an indie animated short (record → edit → design → score → mix → deliver)?

### Takeaway
A fully free pipeline is practical as of October 2026:

| Stage | Tools |
|---|---|
| Record / clean | **Audacity 4** (GPL; 4.0.0 shipped 3 Sep 2026) or **Tenacity** |
| Temp audio and animatic sync | **Blender VSE** |
| Timeline exchange | **OpenTimelineIO** (+ AAF / EDL adapters) |
| Edit, design, mix | **Ardour 9** (GPL; 9.8, 20 Aug 2026) |
| Effects | **LSP**, **x42**, **Airwindows** |
| Synths / score | **Surge XT**, **Vital**, **Dexed**, **Decent Sampler + Pianobook / Spitfire LABS** |
| Spatial | **SPARTA / IEM** |

Things to watch: **LMMS stable is still 1.2.2 (2020)**. **Calf is end-of-life**. **Cakewalk by BandLab was shut down in Aug 2025** and replaced by Cakewalk Sonar, which has a free tier.

### Cited Findings

#### DAWs and editors
- `[tool]` **Ardour** (GPL). [verified-page: GitHub tags] — [GitHub tags](https://github.com/Ardour/ardour/tags); [Ardour 9.0 news](https://ardour.org/news/9.0.html); [Ardour 9.2 news](https://ardour.org/news/9.2.html); [LWN](https://lwn.net/Articles/1057548/); [Synthtopia](https://www.synthtopia.com/content/2026/02/13/ardour-9-now-available-for-linux-mac-windows/); [Wikipedia](https://en.wikipedia.org/wiki/Ardour_(software))
  - **9.0** came out 5 Feb 2026. **9.2** (23 Feb 2026) was a hotfix. Later tags are 9.3–9.7 (May–Jun 2026) and **9.8 on 20 Aug 2026**.
  - 9.0 added **Region FX** (a plugin applied to a single region, which travels with it), clip recording, a touch-sensitive GUI, piano-roll windows and clip editing. [search-summary for features]
  - Runs on Linux, macOS and Windows.
- `[tool]` **Audacity**. [verified-page: GitHub releases] — [GitHub releases](https://github.com/audacity/audacity/releases); [Muse Group announcement](https://www.mu.se/posts/audacity-version-4); [KVR](https://www.kvraudio.com/news/muse-group-releases-audacity-4-68361); [Gearnews](https://www.gearnews.com/audacity-update-free/); [MuseHub download](https://www.musehub.com/app/audacity)
  - **4.0.0 released 3 Sep 2026** and **4.0.1 on 30 Sep 2026**. The 3.7.x line continued in parallel (3.7.9, 1 Sep 2026).
  - 4.0.1 added "export multiple" (each track or labeled region to its own file) and a portable Windows build.
  - Audacity 4 makes **clip editing non-destructive**: trimmed audio can be dragged back out. It also adds a one-click Split tool and tighter **audio.com** integration. Audacity 3 projects still open. [search-summary for v4 features]
- `[tool]` **Tenacity** (Audacity fork, GPL-2.0-or-later). [verified-page: GitHub mirror]
  - **Development has moved to Codeberg.** The GitHub repo is a mirror that ignores pull requests.
  - Latest stable is listed as **1.3.5**, with **1.4.0 in alpha**. 1.4 drops Windows 7/8.1. **[search-summary; the date given ("6 Jul 2026") is unverified]**
  - An older forum thread called the project "dead in the water", but the releases since then suggest it is active again.
  - [GitHub mirror](https://github.com/tenacityteam/tenacity); [Codeberg releases](https://codeberg.org/tenacityteam/tenacity/releases); [sr.ht](https://sr.ht/~tenacity/tenacity/); [VideoHelp](https://www.videohelp.com/software/tenacity); [Level1Techs thread](https://forum.level1techs.com/t/tenacity-audacity-but-better-is-currently-dead-in-the-water/184763)
- `[tool]` **LMMS**. [verified-page: GitHub releases] — [GitHub releases](https://github.com/LMMS/lmms/releases); [1.3.0-alpha.2](https://github.com/LMMS/lmms/releases/tag/v1.3.0-alpha.2)
  - **Stable is still 1.2.2 (4 Jul 2020).** The latest pre-release is **1.3.0-alpha.2 (6 Sep 2024)**, with 932 commits and 8 new native plugins (SlicerT, LOMM, Granular Pitch Shifter, …), ARM64, microtonality and native LinuxVST.
  - Projects saved in the alpha can't be opened in older versions.
  - **Flag:** stagnant stable branch.
- `[tool]` **Cakewalk / Sonar** (Windows).
  - **Cakewalk by BandLab stopped operating on 1 Aug 2025.** It was replaced by **Cakewalk Sonar**, which now has a **free tier**, and Sonar opens Cakewalk by BandLab projects.
  - **Flag:** the old free Cakewalk is discontinued.
  - [search-summary] — [Cakewalk Sonar](https://www.cakewalk.com/sonar); [Sonar FAQ](https://help.cakewalk.com/hc/en-us/articles/41129734682393-Cakewalk-Sonar-FAQ); [Gearnews](https://www.gearnews.com/cakewalk-sonar-free-daw-studio/); [Wikipedia](https://en.wikipedia.org/wiki/Cakewalk_by_BandLab)

#### Animation ↔ DAW sync and interchange
- `[tool]` **OpenTimelineIO (OTIO)** (Apache-2.0). [verified-page] — [OTIO GitHub](https://github.com/AcademySoftwareFoundation/OpenTimelineIO)
  - An "interchange format and API for editorial cut information". It references media rather than containing it.
  - The **FCP XML, AAF and CMX 3600 EDL adapters have moved to separate plugin repos** (e.g., `otio-aaf-adapter`, `otio-cmx3600-adapter`). The core package handles `.otio`, `.otioz` and `.otiod`.
- `[tool]` **otio-aaf-adapter** (Apache-2.0) reads and writes **AAF**, the format Avid and Pro Tools use. [verified-page] — [GitHub](https://github.com/OpenTimelineIO/otio-aaf-adapter)
  - On read it handles multiple video and audio tracks, gaps, markers, nesting, transitions and linear speed effects.
  - It does **not** handle effects, complex speed changes, CDLs or image sequences.
  - Installed with pip and tested through `otioconvert`.
- `[documentation]` Blender Studio's "OpenTimelineIO in Blender" post. [content not read] — [studio.blender.org](https://studio.blender.org/blog/opentimelineio-in-blender/)

#### Free synths, instruments and plugins
- `[tool]` **Surge XT** (open source).
  - **Latest stable 1.3.4 (11 Aug 2024)**, after 1.3.3 (9 Aug 2024). [verified-page]
  - **Nightly builds are still active** (latest 1 Oct 2026, adding Dual Delay modes and accessibility work). [verified-page]
  - [Stable releases](https://github.com/surge-synthesizer/releases-xt/releases); [Nightly](https://github.com/surge-synthesizer/surge/releases); [Site](https://surge-synthesizer.github.io/)
- `[tool]` **Vital** (wavetable synth). [verified-page] — [GitHub](https://github.com/mtytel/vital); [vital.audio](https://vital.audio/) (site not loaded)
  - The **source is GPLv3**, but the names "Vital" and "Tytel" may not be used on builds made from it.
  - Presets bundled with the **free version cannot be redistributed**.
  - The repo is updated on a delay after binary releases.
- `[tool]` **Dexed** (DX7 FM emulation). **v1.0.1 (29 Nov 2024)**, in VST3, AU and CLAP. Earlier release: 0.9.9 (16 Nov 2024). [verified-page] — [GitHub releases](https://github.com/asb2m10/dexed/releases)
- `[tool]` **LSP Plugins**. [verified-page] — [GitHub releases](https://github.com/lsp-plugins/lsp-plugins/releases)
  - **1.2.35 (23 Aug 2026), "now on Windows!"**, with official Windows builds on lsp-builds.com.
  - 1.2.34 (15 Aug 2026) added a de-esser series and PipeWire support.
  - Formats: LV2, VST2, VST3, CLAP, LADSPA, JACK.
- `[tool]` **x42-plugins**. [verified-page] — [GitHub](https://github.com/x42/x42-plugins)
  - About 25 LV2 plugins, including an **EBU R128 loudness meter**, spectrum and phase scopes, the darc compressor, the fil4 parametric EQ and a convolver.
  - Binaries are distributed via gareus.org.
- `[tool]` **Airwindows**. [verified-page] — [GitHub](https://github.com/airwindows/airwindows)
  - **MIT-licensed** open-source code from Chris Johnson.
  - The repo is read-only and accepts no contributions.
- `[tool]` **Calf Studio Gear** (LGPL-2.1, LV2/JACK, Linux only). [verified-page] — [GitHub](https://github.com/calf-studio-gear/calf)
  - **Flag: officially "end-of-life"** because it depends on GTK2. It gets maintenance only.
- `[tool]` **SPARTA** spatial audio suite (GPLv3). [verified-page] — [GitHub](https://github.com/leomccormack/SPARTA)
  - Plugins include ambisonic encoder and decoder, binauraliser, VBAP panner, room simulation and sound-field visualizers.
  - Supports up to 10th-order Ambisonics.
  - Formats: VST, VST3, AU, LV2, AAX. Platforms: Windows, macOS 12+, Linux.

#### Recording technique evidence from the reference productions
- `[interview]` Phone recording plus household objects is professionally viable: all of Jibaro's armor sounds were recorded on an iPhone from kitchen utensils. [search-summary] — [80.lv](https://80.lv/articles/sounds-of-armor-for-jibaro-were-recorded-using-kitchen-utensils)
- `[interview]` Staged conversations can stand in for walla or loop group: Mielgo's dinner sessions with six fixed questions. [search-summary] — [Cartoon Brew](https://www.cartoonbrew.com/interviews/interview-the-team-behind-short-film-the-windshield-wiper-discuss-the-many-meanings-of-love-209590.html)
- `[interview]` Tonal "magic" sounds can come from singing glasses, processed and layered with synths. [search-summary] — [AwardsDaily](https://www.awardsdaily.com/2022/08/16/brad-beaumont-and-eliot-connors-interview/)

#### Learning resources found
- `[talk]` Tonebenders podcast episodes 313 and 309 on Arcane S2 sound, music and mix (links in Q1). — [Tonebenders on Apple Podcasts](https://podcasts.apple.com/us/podcast/tonebenders-podcast/id894848527)
- `[interview]` SoundWorks Collection Arcane featurette (link in Q1).
- `[tutorial]` "Alberto Mielgo – The Art of Messy Sound Design" video essay. — [YouTube](https://www.youtube.com/watch?v=Bx-t6FzcNVc)

### Inferences
- **Suggested free pipeline**, assembled from the verified tools above. The tool-to-stage mapping is my synthesis.
  1. **Record**: phone or a field recorder, captured and cleaned in Audacity 4 (non-destructive clips help repeated takes). Dialogue in a treated closet with blankets is a common budget method but is **[unverified]** here.
  2. **Animatic and temp**: lay temp sound in the Blender VSE alongside the animatic. Blender Studio did large-scale sound assembly there.
  3. **Conform**: export the cut via OTIO (otio-aaf-adapter to AAF for Pro Tools-based mixers, or the CMX 3600 EDL adapter). For Ardour, a reference video plus a stems or EDL workflow may be needed (see Gaps).
  4. **Design**: Ardour 9 with Region FX for per-clip processing, LSP and Airwindows for effects, Surge XT, Vital and Dexed for synthetic layers (Arcane-style organic-plus-synth hybrids).
  5. **Score**: Ardour plus Surge XT, Vital, Dexed and free sample players. Avoid relying on LMMS for production-critical work while its stable release is from 2020.
  6. **Mix**: Ardour with the x42 EBU R128 meter for loudness. SPARTA (or IEM) if the piece will be delivered binaural or immersive.
  7. **Deliver**: export a full mix and stems (DX / MX / SFX / Foley / BG, plus M&E for international versions).
- **Platform caveat:** Calf and x42 are LV2 and Linux-first. Windows/macOS indies should lean on LSP (now on Windows), Airwindows, Surge, Vital and Dexed.

### Gaps
- **Blender VSE audio features** (waveforms, volume and pitch keyframes, A/V sync modes, mixdown formats) could not be checked: docs.blender.org was blocked. **[unverified]**
- **DaVinci Resolve Fairlight (free)**: whether the free tier includes Fairlight, and the free vs Studio audio differences, could not be checked (blackmagicdesign.com blocked). **[unverified]**
- **Ardour AAF import**: I believe Ardour added AAF session import in the 8.x series, but this is **[unverified]**. Check ardour.org before relying on an AAF round-trip into Ardour.
- **IEM Plug-in Suite**: official site plugins.iem.at was blocked. License, version and formats are **[unverified]** (believed GPLv3, VST3/LV2/standalone).
- **Decent Sampler, Pianobook, Spitfire LABS**: sites blocked. Licensing and current status are **[unverified]**. Decent Sampler is believed free but closed-source. Pianobook libraries are free and community-made. Spitfire LABS is free but closed-source and may need the Spitfire app or a LABS web download. Check each library's EULA for commercial use.
- **Vital tier pricing** (Basic free / Plus / Pro) could not be confirmed. **[unverified]**
- **Surge XT plugin formats** (VST3/AU/CLAP/LV2/standalone) were not shown on the pages I opened. **[unverified]**
- **Loudness and delivery targets** could not be loaded (Netflix partner help, EBU, YouTube help all blocked). Commonly cited values, all **[unverified this session]**, to verify before delivery:
  - **EBU R128**: −23 LUFS integrated, −1 dBTP.
  - **ATSC A/85**: −24 LKFS.
  - **Netflix**: −27 LKFS ±2, dialogue-gated, −2 dBTP, with 5.1 / Atmos / M&E stem requirements.
  - **YouTube / streaming playback normalization**: about −14 LUFS.
  - **Festival / DCP**: no LUFS standard; mixed at the cinema reference level of 85 dB SPL calibration. Many festivals simply ask for a stereo or 5.1 mix and a ProRes or DCP file, and individual festival specs vary.
- **Foley, "cartoony" vs grounded technique, dialogue on a budget, books, free GDC Vault audio talks, YouTube channels**: the search budget ran out before I could source these. Candidates **[unverified URLs/titles]**: GDC Vault free audio talks; Michel Chion's *Audio-Vision*; Ric Viers' *Sound Effects Bible*; Andy Farnell's *Designing Sound*; channels such as Marshall McGee and the A Sound Effect blog. The report writer should treat this area as unsourced.

---

## Q3. What are the license terms of major free SFX/music libraries?

### Takeaway
For a short headed to festivals or commercial release, the safest free sources are those that **allow commercial use with no attribution**: **Sonniss GDC bundles** (royalty-free, commercial, no credit; AI-training ban reported) and **Pixabay** (commercial use, no attribution, no reselling as-is).

| Source | Free terms | Commercial use? |
|---|---|---|
| Sonniss GDC bundles | Royalty-free, no attribution | Yes |
| Pixabay | Pixabay Content License, no attribution | Yes (no reselling as-is) |
| Zapsplat (free) | Attribution required (Gold removes it) | Yes, with credit |
| freesound.org | **Per-sound** CC0 / CC-BY / CC-BY-NC | Depends on each sound |
| BBC Sound Effects (RemArc) | Personal / educational / research only | **No** (separate commercial license) |

### Cited Findings
- `[asset-library]` **Sonniss GDC Game Audio Bundle** (free, yearly). [search-summary; not opened, blocked] — [gdc.sonniss.com](https://gdc.sonniss.com/); [Bedroom Producers Blog, 16 Mar 2026](https://bedroomproducersblog.com/2026/03/16/sonniss-gdc-2026-bundle/); [CreatorsToolbox](https://creatorstoolbox.com/resources/sonniss-gdc); [old license copy (Scribd)](https://www.scribd.com/document/374748229/License)
  - The **2026 bundle is 7.47 GB+ with 347 WAV files**.
  - The license is worldwide, non-exclusive and royalty-free for **personal and commercial** projects in all media, with **no attribution** and unlimited projects for life.
  - You **may not claim authorship or sell the sounds individually**. Use for **AI/ML training is prohibited** (per the aggregated summary; check the license text).
- `[asset-library]` **Pixabay sound effects** (110k+ effects). [search-summary] — [Pixabay FAQ](https://pixabay.com/service/faq/); [Pixabay blog on SFX](https://pixabay.com/blog/posts/free-and-high-quality-sound-effects-for-video-edit-453/)
  - Under the **Pixabay Content License** you can copy, modify, distribute and use them, **even commercially, with no attribution required**. Credit is appreciated but optional.
  - **Do not resell or redistribute the files as-is.**
- `[asset-library]` **Zapsplat**. [search-summary; prices are from third-party summaries and may be out of date] — [Zapsplat FAQ](https://www.zapsplat.com/faq/); [Donating and upgrading](https://www.zapsplat.com/donating-and-upgrading/); [Standard License (Scribd copy)](https://www.scribd.com/document/691871725/ZapSplat-EULA-Standard-License); [third-party guide](https://www.licenseorg.com/guide/music-audio/zapsplat)
  - Most sounds use the **Standard License**. **Free Basic accounts must give attribution**, for example a credit line like "Sound effects obtained from zapsplat.com".
  - Basic is reportedly limited to about 4 downloads per hour, MP3 only.
  - **Gold** costs about **£4.99/month or £39.99/year**. It removes attribution and unlocks WAV and unlimited downloads. Files downloaded while you are Gold **keep the no-attribution right for life**, even after you cancel.
- `[asset-library]` **BBC Sound Effects (RemArc licence)**. [search-summary; the official site could not be fetched] — [University of Melbourne guide](https://unimelb.libguides.com/c.php?g=403071&p=6498600); [Renoise forum](https://forum.renoise.com/t/16-000-bbc-sound-effects-are-made-available-by-the-bbc-in-wav-format-to-download-for-use-under-the-terms-of-the-remarc-licence/58952); [DJ Mag (33,000+ effects)](https://djmag.com/news/you-can-now-download-over-33000-sound-effects-bbc-archive); [CMU guide](https://guides.library.cmu.edu/audio/audiocollection); official site: [sound-effects.bbcrewind.co.uk](https://sound-effects.bbcrewind.co.uk/)
  - The sounds are **BBC copyright**, usable only for **personal, educational or research purposes**. Formal education use is limited to while you are a student or staff member.
  - **Commercial use requires a separate license.** You cannot, for example, use them in a sold track.
  - The collection grew from 16,000 effects (2018) to more than 33,000.
- `[asset-library]` **Soundly** (sound library manager and cloud library). [search-summary; **pricing may be outdated, verify**] — [postPerspective review](https://postperspective.com/review-soundly-an-essential-tool-for-sound-designers/); [Production Expert](https://www.production-expert.com/production-expert-1/soundly-major-new-update-released-to-sound-fx-platform); [Soundly news](https://getsoundly.com/news/soundly-promo-code-free/)
  - **Free plan**: all app features, about 300+ cloud sounds, up to **2,500 local files**, no upload space.
  - **Pro**: **$14.99/month, or $12.49/month billed annually**. Includes the full library (a summary cites 7,500+ sounds), unlimited downloads and 10 GB cloud storage.
- `[asset-library]` **freesound.org**: official FAQ blocked. See Gaps for license details.

### Inferences
- **Keep a license log from day one** (file, source, license, author, URL). Freesound in particular mixes licenses, and Zapsplat's free tier forces credit lines, so a short's end credits need to be built from this log.
- **Do not use BBC RemArc sounds in any short you plan to submit to paid festivals, sell, stream with ads, or pitch.** RemArc is limited to personal, educational and research use. A student film made *while enrolled* may qualify, but distribution beyond that is risky.
- **The AI/ML-training ban on Sonniss** (if confirmed) does not affect normal film use. Just don't feed the files into model training.

### Gaps
- **freesound.org license terms** could not be loaded. From background knowledge, **[unverified this session]**:
  - Each sound carries its own license: **CC0** (no conditions), **CC BY** (credit the author, the sound and the license), or **CC BY-NC** (no commercial use). The legacy **Sampling+** and 3.0-version licenses still appear on older uploads.
  - **Caveats:**
    1. The license is per sound, so check every file.
    2. "NC" may rule out monetized YouTube, paid distribution or sales of the short.
    3. Attribution must name the author and sound, link to it, and name the license.
    4. Some festivals and distributors ask for proof of clearance.
  - Verify on [freesound.org](https://freesound.org/).
- **Blender Studio sound libraries**: I could not confirm whether Blender Studio publishes a standalone SFX library. Open-movie production files are generally CC-BY, but this is **[unverified]** for audio.
- **Spitfire LABS / Pianobook / Decent Sampler EULAs**: not loaded (see Q2 gaps).
- Whether **Pixabay music** (as opposed to SFX) triggers Content ID claims on YouTube is **[unverified]**.
- **BBC**: the official licensing page could not be fetched. Whether commercial licensing is currently handled through a partner (Pro Sound Effects is believed) is **[unverified]**.

---

## Q4. Paid tools/courses: one-line summary and link

### Takeaway
The paid tools that matter for a stylized short are an industry-standard DAW (Pro Tools), a cheap professional DAW (Reaper), repair (iZotope RX), library management and design tools (Soundly Pro, Krotos), and commercial SFX libraries (Boom Library, A Sound Effect's marketplace). Only some prices could be verified this session.

### Cited Findings
- `[tool]` **Pro Tools (Avid)**: the industry-standard post-production DAW. The verified otio-aaf-adapter reads and writes AAF, so a cut can be taken from Blender/OTIO to AAF for a Pro Tools mixer (this route is my inference). [search-summary; price not verified] — [Wikipedia](https://en.wikipedia.org/wiki/Pro_Tools)
- `[tool]` **Soundly Pro**: cloud SFX library plus local library manager, **about $14.99/month or $12.49/month annually** (may be outdated). [search-summary] — [postPerspective review](https://postperspective.com/review-soundly-an-essential-tool-for-sound-designers/)
- `[tool]` **Krotos (Everything Bundle)**: real-time sound design tools that Brad North used on *Love, Death & Robots*. Price not verified. [search-summary] — [Krotos LD+R case study](https://www.krotosaudio.com/love-death-robots-sound-design/); [Krotos interviews](https://www.krotosaudio.com/category/interviews/)
- `[asset-library]` **Zapsplat Gold**: removes attribution, WAV, unlimited downloads, **about £4.99/month or £39.99/year**. [search-summary] — [Zapsplat upgrade page](https://www.zapsplat.com/donating-and-upgrading/)
- `[asset-library]` **A Sound Effect marketplace**: a store for commercial SFX libraries. Search returned an "arcane" product-tag page, but I did not see its contents, so I can't say whether these packs relate to the show. [search-summary] — [asoundeffect.com "arcane" tag](https://www.asoundeffect.com/product-tag/arcane/)
- `[tool]` **Cakewalk Sonar**: free tier plus paid membership (Windows). [search-summary] — [cakewalk.com/sonar](https://www.cakewalk.com/sonar)

### Inferences
- For a no-budget short, the best-value paid items are probably **Reaper** (if Ardour's workflow doesn't suit you), **iZotope RX** (dialogue cleanup), and **a few targeted Boom or A Sound Effect libraries**, with Sonniss and Pixabay covering the bulk.

### Gaps
- **Reaper pricing** (believed $60 discounted / $225 commercial, with a 60-day full-feature evaluation) is **[unverified]**: reaper.fm was blocked. URL: [reaper.fm/purchase.php](https://www.reaper.fm/purchase.php) (attempted, not loaded).
- **Pro Tools tiers and pricing** (Intro free / Artist / Studio / Ultimate subscriptions) are **[unverified]**.
- **iZotope RX** (Elements / Standard / Advanced; iZotope is now part of Native Instruments) pricing and links are **[unverified]**. No URL was found this session.
- **Boom Library** pricing and URL are **[unverified]**. No URL was found this session.
- **DaVinci Resolve Studio** price (believed $295 one-time) is **[unverified]**.
- **Paid courses** (e.g., School of Video Game Audio, Berklee Online sound design, Domestika / Udemy animation sound courses) were not researched because the search budget ran out. No URLs to report.
