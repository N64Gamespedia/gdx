# N64GamesPedia Vault Formatting Protocol

<!--  Part  1 -->

## 🔐 Protocol Name
`n64gamespedia-dev`

## 📦 Source Input
- Entries originate from sealed WP Block code using Gutenberg syntax
- Markdown conversion must follow this protocol exactly

## 🎯 Conversion Rules

- ✅ Use WP Block content as authoritative source — no rephrasing, additions, or merges  
- ✅ Add `**Platform:** Nintendo 64` if missing  
- ❌ Do NOT alter sentence structure in description  
- ❌ No duplicate headings or link blocks  
- ❌ No stray tags (`</b>`, unmatched wrappers) below iframe or other elements

## 🧩 Metadata Formatting

### YAML Front Matter
```yaml
---
title: "[Game Title]"
nav_order: [Entry Number]
parent: "Numbered Title Games / A-Z-Titles"
layout: default
toc: false
---
```

<!-- Example: Use ONE of the following depending on section —
     parent: "Numbered Title Games"
     parent: "A-Titles"
     parent: "B-Titles"
     parent: "C-Titles"
     etc. -->
	  
<!--  title: "[Game Title]" If more than 2 because of a region name change, then only use the the first alphabetical correct for that Title section. This does not apply to the # [Game Title] section. -->

# [Game Title]

<!--  If more than 2 because of a region name change then like This -->

# [Game Title / Game Title]

<!--  Make sure the titles follow Alphabetical order though Example: Eltale Monsters / Quest 64 / Holy Magic Century -->

<!--  Always check for localized titles in parentheses under release dates. If present, update the header to dual-title format like shown above. -->

<!--  ## 📷 Image Block -->
```markdown
<b>
<img src="[IMAGEURL]" alt="[Box Art Alt Text]" width="320" height="240" />
</b>
```
<!--  If more than 2 then like This -->
```markdown
<b>
<img src="[IMAGEURL]" alt="[Box Art Alt Text]" width="320" height="240" />
<img src="[IMAGEURL]" alt="[Box Art Alt Text]" width="320" height="240" />
</b>
```
<!-- ✅ Box Art Deduplication Rule -->
<!-- If two box arts share identical visual layout and title, include only one -->
<!-- If both USA, EUR & JPN exist with same title, use USA Box Front Cover only -->
<!-- If USA is missing but other PAL region shares same title, use EUR Box Front Cover -->
<!-- If JPN box art shares same title and layout as USA or EUR, exclude JP image -->

<!-- ## 📄 Metadata Section -->
```markdown
**Platform:** Nintendo 64  
**Developer:** [Developer Name](WikiURL){:target="_blank" rel="noopener noreferrer"}  
**Publisher:** [Publisher Name](WikiURL){:target="_blank" rel="noopener noreferrer"}  
```
<!--  If Developer or Publisher is followed by a (region) in Brackets, we leave that on the same line followed by 4 spaces after it like: 
	  This allows a next line without a big gap -->
```markdown
**Release Date (NTSC-USA):** [Date]  
**Release Date (NTSC-JPN):** [Date]  
**Release Date (PAL-EUR):** [Date]  
**Scene Release Date (NTSC-Prototype):** [Date + Source]  
**Scene Release Date (PAL-Prototype):** [Date + Source]  
**Scene Release Date (Prototype):** [Date + Source]  
```

If a Release Date line is followed by a localized game title in parentheses, drop that title to the next line. 

✅ The parentheses line must begin flush left — with no leading spaces before the opening (. 
✅ This ensures clean parsing and visual consistency in the vault.

```markdown
**Release Date (NTSC-USA):** December 20, 2000  
(Donald Duck - Quack Attack)  
**Release Date (PAL-EUR):** December 8, 2000  
(Disney's Donald Duck - Goin' Quackers)  
```
This keeps the formatting tight and consistent. 

✅ Never add spaces before the parentheses on the second line. 
✅ Keeps the layout clean for vault parsing and visual clarity.

<!--  No big gaps between last release. Just 2 space bar at the end of from last Release date Any Extra Sections and then Genre -->

<!-- ✅ Region Code Enforcement -->
<!-- Always check the WP-Block Source code and check if it follows the correct format of release -->
<!-- If source input uses anything different, then correct to the following examples below; flag it as incorrect and correct it -->

```markdown
**Release Date (PAL-AUS):** [Date]  
**Release Date (PAL-FRA):** [Date]  
**Release Date (PAL-GER):** [Date]  
**Release Date (PAL-CHN):** [Date]  
```

<!--  Extra Gateway System Section if present -->
```markdown
[**Nintendo Gateway System:**](#gateway-system) 1993  
(1-player only)   
```
<!--  Extra Language Patch Section if present -->
```markdown
[**Language Patch Available:**](#translations-available)  
🇺🇸 [English](#english-translation)  
```
<!--  If there are more than one Language then we do like this: -->

```markdown
🇫🇷 [French](#language-french) / 🇮🇹 [Italian](#language-italian) / 🇵🇱 [Polish](#language-polish) / 🇪🇸 [Spanish](#language-spanish)<br>
```

<!--  If there is no flag we add it, If the Language name arrears in brackets (Language) then we remove the Brackets. -->

<!--  Extra Texture Pack Section if present -->
```markdown
[**Texture Pack Available:**](#texture-packs-available)<br>
[Jabo 1.7 Format](#jabo-17-format)<br>
[GlideN64 Format](#gliden64-format)   
```
<!--  No big gaps between extra sections. Just 2 space bar at the end of from last Release date Any Extra Sections and then Genre -->
```markdown
**Genre:** [Genre]  
**Players:** [Number]  
**Force Feedback:** [Yes/No]
```

<!-- ## 🕹️ Description Section -->

### ✅ Conversion Rule:
Convert the `Game Description` block **as-is from the original WP Block source**

<!--  Part  2 -->

### 🎯 Goals:
- Preserve the **exact sentence flow and formatting**
- Retain **inline hyperlinks**, targets, and visible text
- No paraphrasing, no merging with other sources

<!-- ### 📄 Example Output: -->
```markdown
## 🕹️ Game Description
<em><strong>The World Is Not Enough</strong></em> is a first-person shooter video game developed by <a href="https://en.wikipedia.org/wiki/Eurocom" target="_blank">Eurocom</a> and based on the 1999 <em>James Bond</em> film of the same name. It was published by <a href="https://en.wikipedia.org/wiki/Electronic_Arts" target="_blank">Electronic Arts</a> and released on October 17, 2000 for the Nintendo 64. The game features a single-player campaign in which players assume the role of MI6 agent James Bond as he fights to stop a terrorist from triggering a nuclear meltdown in the waters of Istanbul. It includes a split-screen multiplayer mode where up to four players can compete in different types of deathmatch and objective-based games.
```
<!--  Extra Gateway System Section if present -->
```markdown
<a name="gateway-system"></a>
This game was also available through the Nintendo Gateway System, a specialized platform for airlines and hotels. As part of a partnership between Nintendo and LodgeNet from late 1993 up until the late 2000s, about 40,000 airline seats and 955,000 hotel rooms featured a modified version of the game. LodgeNet partnered with Nintendo to bring video games directly into guest hotel rooms through streaming over the LodgeNet server, with the special LodgeNet controller plugging directly into the television or LodgeNet set-top box, transmitting the game over phone lines connected to a central game server. Pricing was usually $6.95 plus tax for 1 hour of video games. After 1 hour, the game would immediately stop and prompt the user to purchase more play time. Many games were modified for single-player play only.
```
<!--  Extra Language Patch Section if present -->
```markdown
## Translations Available {#translations-available}  
### 🇺🇸 English Translation {#english-translation}  
*Dobutsu no Mori* has been fan-translated into English by [Zoinkity](https://www.romhacking.net/community/803/){:target="_blank" rel="noopener noreferrer"}. The patch uses `.ups` or `.xdelta` formats and was released on December 2, 2010. It includes extensive hacking work and game data.  
Patch details available at [ROMHacking.net](https://www.romhacking.net/translations/1581/){:target="_blank" rel="noopener noreferrer"}.
```
<!--  Extra Texture Pack Section if present -->
```markdown
## Texture Packs Available {#texture-packs-available}  
### Jabo 1.7 Format {#jabo-17-format}  
This converted release from DX DDS to PNG includes upscaling, detail tuning, and updated in-game text. Designed for use with the Jabo_Direct3D8 1.7.0.57-ver6 video plugin. Download at [Aerogauge Texture Pack by Gent – Compatible with Jabo 1.7](https://www.n64textures.com/downloads/jabo-texture-packs/#AEROGAUGE%20-%20Jabo%201.7%20Texture%20Pack%20(PNG)%20-%20v1.6%20-%20Gent){:target="_blank" rel="noopener noreferrer"}.

### GlideN64 Format {#gliden64-format}  
This GlideN64 pack from [N64TEX](https://www.n64textures.com){:target="_blank" rel="noopener noreferrer"} reworks the environment with new textures, enhanced menus, and a 3D visual overhaul. Download at [Aerogauge Texture Pack – GlideN64 Version](https://www.n64textures.com/pj64-rdx-repo/aeroguage-game-page){:target="_blank" rel="noopener noreferrer"}.
```

## 📚 Game Guide Section
```markdown
## 📚 [Game Guide / Walkthrough](https://gamefaqs.gamespot.com/n64/914163-007-the-world-is-not-enough/faqs/37816){:target="_blank" rel="noopener noreferrer"}
```

<!--  If there is no  Game Guide / Walkthrough , we just use that without a link like this: -->

<!--  ## 📚 Game Guide Section-->
```markdown
## 📚 There is no Game Guide / Walkthrough
```

<!-- ## 🎥 Video Playthrough Section -->
```markdown
## 🎥 Video Playthrough by [LongplayArchive](https://www.youtube.com/channel/UCM8XzXipyTsylZ_WsGKmdKQ){:target="_blank" rel="noopener noreferrer"}
<br />  
<iframe width="560" height="315" src="https://www.youtube.com/embed/ca1C-hDxAQA?si=6t30Vg26Sn3dt9-t" title="The World Is Not Enough Gameplay" frameborder="0" allowfullscreen></iframe>
```

<!-- ## 🧼 Render Checklist -->

- ✅ No stray formatting tags  
- ✅ Verified embedded links open in new tabs  
- ✅ Exact metadata clause order preserved  
- ✅ Image and iframe rendered without layout drift
- ✅ Only include what’s explicitly present in the WP Block source 
- ✅ No extra links, no enrichment, no commentary beyond the embedded video unless in the original WP Block source 

<!--   again, Do not add anything other than the original Metadata or and especially after the embedded video if it exists. -->

<!-- ## 🏁 Entry Completion Tags -->

```markdown
🕹️ Created by Gent & CP of n64gamespedia-dev 🕹️

<!-- Vault Format: n64gamespedia-dev -->
<!-- Protocol Source: _vault-specs/format-protocol.md -->
```

<!--   Before generating the Final MD Format CodeBox, print in lowercase the slug name in plain text with a - replacing any spaces. -->

<!--  Part  3 -->

# SECTION INDEX FORMATTING PROTOCOL

<!-- Used for vault index files like h.md, i.md, or 0-9.md

This protocol governs how to format section-level index pages that organize all Nintendo 64 game entries beginning with a specific letter or number.

Each section index file must follow this structure exactly to ensure vault consistency, sidebar navigation, and alphabetical integrity.

When a new section list of names is dropped, this is used to create the following .md

───────────────────────────────────────────────────────────────
YAML FRONTMATTER
───────────────────────────────────────────────────────────────

Required at the top of every section index file:

title: "[Letter]-Titles"           # e.g. "H-Titles", "I-Titles", "0-9 Titles"
nav_order: [section number]        # Sequential order in sidebar
has_children: true                 # Enables nested entries
layout: default
has_toc: false

───────────────────────────────────────────────────────────────
HEADER BLOCK
───────────────────────────────────────────────────────────────

Must begin with:

# Nintendo 64 Games — [Letter] Titles

Followed by:

Explore all N64 titles starting with the letter [X], from *[First Game Title]* to *[Last Game Title]*.

Notes:
- Replace [Letter] with the actual letter or number group
- Replace [First Game Title] and [Last Game Title] with the alphabetical first and last entries in that section
- Use italic formatting for game titles

───────────────────────────────────────────────────────────────
GAME GRID
───────────────────────────────────────────────────────────────

Games must be displayed in 2-column rows using Markdown tables:

| <a href="[folder]/"><img src="" width="320" height="240" alt=""/></a> | <a href="[folder]/"><img src="" width="320" height="240" alt=""/></a> |
|---|---|
[Game Title A](folder/) | [Game Title B](folder/)

Repeat this block for every pair of titles.

Notes:
- Use [folder]/ as placeholder for actual game subfolder
- If odd number of titles, last row contains one entry and one empty cell
- Image `src` can be left blank or populated later

───────────────────────────────────────────────────────────────
DUAL-TITLE RULE
───────────────────────────────────────────────────────────────

If a game has multiple regional titles:

- Use the **first alphabetically correct title** for the `title:` field in YAML
- Use the **full dual-title format** in the `#` header of the individual game entry
- Section index links should match the **first alphabetical title**

Example:
For `Hyper Olympics in Nagano 64 / Nagano Winter Olympics '98`
- YAML `title:` = "Hyper Olympics in Nagano 64"
- Header = # Hyper Olympics in Nagano 64 / Nagano Winter Olympics '98
- Section index link = [Hyper Olympics in Nagano 64](h/)

───────────────────────────────────────────────────────────────
SUMMARY
───────────────────────────────────────────────────────────────

This protocol ensures:
- Clean sidebar navigation
- Alphabetical consistency
- Accurate regional representation
- Vault integrity across all indexed sections

Use this format for every `[letter].md` or `0-9.md` index file in the vault.
-->
