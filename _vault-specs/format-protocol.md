# N64GamesPedia Vault Formatting Protocol

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
------ Example: parent: "Numbered Title Games", parent: "A-Titles", parent: "B-Titles", parent: "C-Titles" etc -----------------
------ Every New Section A, B, C etc starts fresh with the first Alphabetical Letter as nav_order: 1 and so on until the next Sectioon  -----------------

# "[Game Title]"

## 📷 Image Block
```markdown
<b>
<img src="[IMAGEURL]" alt="[Box Art Alt Text]" width="320" height="240" />
</b>
```

------ If more than 2 then like This -----------------

```markdown
<b>
<img src="[IMAGEURL]" alt="[Box Art Alt Text]" width="320" height="240" />
<img src="[IMAGEURL]" alt="[Box Art Alt Text]" width="320" height="240" />
</b>
```

## 📄 Metadata Section
```markdown
**Platform:** Nintendo 64  
**Developer:** [Developer Name](WikiURL){:target="_blank" rel="noopener noreferrer"}  
**Publisher:** [Publisher Name](WikiURL){:target="_blank" rel="noopener noreferrer"}  
```
------ If Developer or Publisher is followed by a (region) in Brackets, we leave that on the same line followed by 4 spaces after it like:    ----------------- 
------ This allows a next line without a big gap -----------------

```markdown
**Release Date (NTSC-USA):** [Date]  
**Release Date (PAL-EUR):** [Date]  
**Prototype Scene Release Date:** [Date + Source]  
```
------ If Release Date: [Date]  is followed by an alternative (region name) in Brackets, then we drop that down to the next line followed by 4 spaces after it like:     -----------------
------ This allows a next line without a big gap -----------------

------ Extra Gateway System Section if present -----------------
```markdown
[**Nintendo Gateway System:**](#gateway-system) 1993  
(1-player only)   
```
------ Extra Language Patch Section if present -----------------
```markdown
[**Language Patch Available:**](#translations-available)<br>
🇺🇸 [English](#english-translation)<br>
```
------ If there are more than one Language then we do like this: -----------------

```markdown
🇫🇷 [French](#language-french) / 🇮🇹 [Italian](#language-italian) / 🇵🇱 [Polish](#language-polish) / 🇪🇸 [Spanish](#language-spanish)<br>
```

------ If there is no flag we add it, If the Language name arrears in brackets (Language) then we remove the Brackets. -----------------

------ Extra Texture Pack Section if present -----------------
```markdown
[**Texture Pack Available:**](#texture-packs-available)<br>
[Jabo 1.7 Format](#jabo-17-format)<br>
[GlideN64 Format](#gliden64-format)   
```
------ No big gaps between extra sections. Just a paragraph space from last Release date Any Extra Sections and then Genre -----------------

```markdown
**Genre:** [Genre]  
**Players:** [Number]  
**Force Feedback:** [Yes/No]
```

## 🕹️ Description Section

### ✅ Conversion Rule:
Convert the `Game Description` block **as-is from the original WP Block source**

### 🎯 Goals:
- Preserve the **exact sentence flow and formatting**
- Retain **inline hyperlinks**, targets, and visible text
- No paraphrasing, no merging with other sources

### 📄 Example Output:
```markdown
## 🕹️ Game Description
<em><strong>The World Is Not Enough</strong></em> is a first-person shooter video game developed by <a href="https://en.wikipedia.org/wiki/Eurocom" target="_blank">Eurocom</a> and based on the 1999 <em>James Bond</em> film of the same name. It was published by <a href="https://en.wikipedia.org/wiki/Electronic_Arts" target="_blank">Electronic Arts</a> and released on October 17, 2000 for the Nintendo 64. The game features a single-player campaign in which players assume the role of MI6 agent James Bond as he fights to stop a terrorist from triggering a nuclear meltdown in the waters of Istanbul. It includes a split-screen multiplayer mode where up to four players can compete in different types of deathmatch and objective-based games.
```
------ Extra Gateway System Section if present -----------------
```markdown
<a name="gateway-system"></a>
This game was also available through the Nintendo Gateway System, a specialized platform for airlines and hotels. As part of a partnership between Nintendo and LodgeNet from late 1993 up until the late 2000s, about 40,000 airline seats and 955,000 hotel rooms featured a modified version of the game. LodgeNet partnered with Nintendo to bring video games directly into guest hotel rooms through streaming over the LodgeNet server, with the special LodgeNet controller plugging directly into the television or LodgeNet set-top box, transmitting the game over phone lines connected to a central game server. Pricing was usually $6.95 plus tax for 1 hour of video games. After 1 hour, the game would immediately stop and prompt the user to purchase more play time. Many games were modified for single-player play only.
```
------ Extra Language Patch Section if present -----------------
```markdown
## Translations Available {#translations-available}  
### 🇺🇸 English Translation {#english-translation}  
*Dobutsu no Mori* has been fan-translated into English by [Zoinkity](https://www.romhacking.net/community/803/){:target="_blank" rel="noopener noreferrer"}. The patch uses `.ups` or `.xdelta` formats and was released on December 2, 2010. It includes extensive hacking work and game data.  
Patch details available at [ROMHacking.net](https://www.romhacking.net/translations/1581/){:target="_blank" rel="noopener noreferrer"}.
```
------ Extra Texture Pack Section if present -----------------
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

## 🎥 Video Playthrough Section
```markdown
## 🎥 Video Playthrough by [LongplayArchive](https://www.youtube.com/channel/UCM8XzXipyTsylZ_WsGKmdKQ){:target="_blank" rel="noopener noreferrer"}
<br />  
<iframe width="560" height="315" src="https://www.youtube.com/embed/ca1C-hDxAQA?si=6t30Vg26Sn3dt9-t" title="The World Is Not Enough Gameplay" frameborder="0" allowfullscreen></iframe>
```

## 🧼 Render Checklist

- ✅ No stray formatting tags  
- ✅ Verified embedded links open in new tabs  
- ✅ Exact metadata clause order preserved  
- ✅ Image and iframe rendered without layout drift


## 🏁 Entry Completion Tags

```markdown

🕹️ Created by Gent & CP of n64gamespedia-dev 🕹️

<!-- Vault Format: n64gamespedia-dev -->
<!-- Protocol Source: _vault-specs/format-protocol.md -->
```

------  Before generating the Final MD Format CodeBox, Normal Chat print the Slugname.md with a - replacing any spaces. -----------------
