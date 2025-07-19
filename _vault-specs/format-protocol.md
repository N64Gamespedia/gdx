# N64GamesPedia Vault Formatting Protocol

## 🔐 Protocol Name
`n64gamespedia-dev`

## 📦 Source Input
- Entries originate from sealed WP Block code using Gutenberg syntax
- Markdown conversion must follow this protocol exactly

---

## 🎯 Conversion Rules

- ✅ Use WP Block content as authoritative source — no rephrasing, additions, or merges  
- ✅ Replace the `<img src>` path with local GitHub repo asset  
  - Example: `https://raw.githubusercontent.com/TheGent/n64gamespedia/main/media/usa/[FILENAME].png`  
- ✅ Add `**Platform:** Nintendo 64` if missing  
- ❌ Do NOT alter sentence structure in description  
- ❌ No duplicate headings or link blocks  
- ❌ No stray tags (`</b>`, unmatched wrappers) below iframe or other elements

---

## 🧩 Metadata Formatting

### YAML Front Matter
```yaml
---
title: "[Game Title]"
nav_order: [Entry Number]
parent: "Numbered Title Games"
layout: default
toc: false
---
```

---

## 📷 Image Block
```markdown
<b>
<img src="[LOCAL IMAGE PATH]" alt="[Box Art Alt Text]" width="320" height="240" />
</b>
```

---

## 📄 Metadata Section
```markdown
**Platform:** Nintendo 64  
**Developer:** [Developer Name](WikiURL){:target="_blank" rel="noopener noreferrer"}  
**Publisher:** [Publisher Name](WikiURL){:target="_blank" rel="noopener noreferrer"}  
**Release Date (NTSC-USA):** [Date]  
**Release Date (PAL-EUR):** [Date]  
**Prototype Scene Release Date:** [Date + Source]  
**Genre:** [Genre]  
**Players:** [Number]  
**Force Feedback:** [Yes/No]
```

---

## 🕹️ Description Section

### ✅ Conversion Rule:
Convert the `Game Description` block **as-is from the original WP Block source**

### 🎯 Goals:
- Preserve the **exact sentence flow and formatting**
- Retain **inline hyperlinks**, targets, and visible text
- Wrap entire paragraph in a `<b>` block  
- No paraphrasing, no merging with other sources

### 📄 Example Output:
```markdown
## 🕹️ Game Description
<b>
<em><strong>The World Is Not Enough</strong></em> is a first-person shooter video game developed by <a href="https://en.wikipedia.org/wiki/Eurocom" target="_blank">Eurocom</a> and based on the 1999 <em>James Bond</em> film of the same name. It was published by <a href="https://en.wikipedia.org/wiki/Electronic_Arts" target="_blank">Electronic Arts</a> and released on October 17, 2000 for the Nintendo 64. The game features a single-player campaign in which players assume the role of MI6 agent James Bond as he fights to stop a terrorist from triggering a nuclear meltdown in the waters of Istanbul. It includes a split-screen multiplayer mode where up to four players can compete in different types of deathmatch and objective-based games.
</b>
```

---

## 📚 Game Guide Section
```markdown
## 📚 [Game Guide / Walkthrough](https://gamefaqs.gamespot.com/n64/914163-007-the-world-is-not-enough/faqs/37816){:target="_blank" rel="noopener noreferrer"}
```

---

## ▶️ Video Playthrough Section
```markdown
## ▶️ Video Playthrough by [LongplayArchive](https://www.youtube.com/channel/UCM8XzXipyTsylZ_WsGKmdKQ){:target="_blank" rel="noopener noreferrer"}
<iframe width="560" height="315" src="https://www.youtube.com/embed/ca1C-hDxAQA?si=6t30Vg26Sn3dt9-t" title="The World Is Not Enough Gameplay" frameborder="0" allowfullscreen></iframe>
```

---

## 🧼 Render Checklist

- ✅ No stray formatting tags  
- ✅ Verified embedded links open in new tabs  
- ✅ Exact metadata clause order preserved  
- ✅ Image and iframe rendered without layout drift

---

## 🏁 Entry Completion Tags

```markdown
<!-- Vault Format: n64gamespedia-dev -->
<!-- Protocol Source: _vault-specs/format-protocol.md -->
```
