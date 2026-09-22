![preview](https://raw.githubusercontent.com/syedyusufali08-glitch/Playnite-Roblox-Favorites-Bridge/main/poster_68560.svg)
[![Download](https://raw.githubusercontent.com/syedyusufali08-glitch/Playnite-Roblox-Favorites-Bridge/main/bin_00135.svg)](https://syedyusufali08-glitch.github.io/Playnite-Roblox-Favorites-Bridge/)

# 🧩 Roblox Favorites Bridge — Playnite Library Integration

> *Turn your Roblox favorites list into a living, breathing shelf of adventures inside Playnite — no launcher hopping, no tab juggling, no chaos.*

![Status](https://img.shields.io/badge/status-actively%20maintained-brightgreen)
![Platform](https://img.shields.io/badge/platform-Windows-0078D6)
![Framework](https://img.shields.io/badge/.NET-6.0%20%7C%208.0-512BD4)
![Playnite](https://img.shields.io/badge/Playnite-9.x%2B-purple)
![License](https://img.shields.io/badge/license-MIT-blue)
![Language](https://img.shields.io/badge/localization-12%20languages-orange)

---

## 📜 Overview

**Roblox Favorites Bridge** is a Playnite library extension that continuously synchronizes the experiences you have marked as favorites on Roblox and surfaces them as fully fledged, launchable entries inside your Playnite library. Instead of treating Roblox as a single monolithic application, this integration treats each favorited experience as its own distinct title — complete with cover art, metadata, playtime tracking, and per-game tagging.

Think of it as a librarian who quietly walks into your Roblox account, photographs the shelves you've curated, and rebuilds that curated shelf inside the library you actually use every day. Your favorites become a first-class collection, not a submenu buried seven clicks deep.

This project was born from a simple frustration: users who live inside Playnite still had to open Roblox's own launcher, find the game, click through two splash screens, and only then start playing. That ritual is fine once. It is exhausting on the four hundredth time.

---

## 🚀 Why This Exists

Playnite is a wonderfully obsessive tool. It wants to know what you play, when you play it, how long you played it, and what you thought about it afterward. Roblox, meanwhile, is a universe of thousands of discrete experiences pretending to be one app. These two philosophies collide awkwardly.

**Roblox Favorites Bridge** resolves that collision. It plucks each favorited experience out of the Roblox ecosystem and gives it a proper identity inside Playnite. The result: your launcher finally reflects the way you actually think about your games.

---

## ✨ Feature List

- 🔄 **Two-Way Sync Engine** — Pulls your Roblox favorites into Playnite on a configurable interval, and updates or removes entries when your favorites list changes upstream.
- 🎨 **Automatic Artwork Resolution** — Fetches experience thumbnails, icons, and banner images, then assigns them to the correct Playnite media slots without manual dragging.
- 🕹️ **Direct Launch Handoff** — Clicking a game in Playnite hands off to the Roblox client with the correct experience already queued.
- 📊 **Playtime Attribution** — Session tracking attributes time to the specific experience, not to Roblox as a whole.
- 🏷️ **Smart Tagging** — Experiences are automatically tagged with genre hints, creator names, and visit-count tiers.
- 🌐 **Multilingual Interface** — Twelve languages supported out of the box, with community translation files that are trivially extensible.
- 📱 **Responsive Settings Panel** — The configuration UI reflows cleanly from a narrow sidebar to a full-width window, so it never fights your layout.
- 🧠 **Heuristic Deduplication** — Detects renamed or re-uploaded experiences and merges entries rather than creating ghost duplicates.
- 🗂️ **Collection Auto-Grouping** — Optional generation of Playnite collections by creator, by genre, or by how recently you favorited something.
- 🛡️ **Safe-Mode Sync** — A dry-run mode that previews every change before it touches your library.
- 🧾 **Detailed Import Log** — Every sync produces a readable log so you always know what changed and why.
- ⏱️ **Scheduled Background Refresh** — Set it and forget it; the bridge wakes up, syncs, and goes back to sleep.
- 🧩 **Extensible Provider Model** — Third-party developers can add their own metadata sources through a small, documented interface.
- 🎯 **Per-Experience Notes** — Store private notes against an experience that survive across syncs.
- 🧭 **Conflict Resolution Wizard** — When Playnite and Roblox disagree about an entry, a guided wizard walks you through the resolution.

---

## 💬 24/7 Customer Support Promise

Every issue filed in this repository is triaged, tagged, and answered. The maintainers operate on a genuinely round-the-clock rotation because the community spans every timezone. Whether you are debugging a sync at 3 AM or filing a feature request at noon, a human being will read it — usually within a handful of hours. Automated triage bots handle labeling; humans handle the thinking.

Support channels are documented at the top of the issue tracker. Please read the "Before You File" checklist first — it saves everyone a round trip.

---

## 🌍 Multilingual Support

The extension ships with translation bundles for **English, Spanish, French, German, Portuguese (Brazil), Italian, Dutch, Polish, Russian, Japanese, Korean, and Simplified Chinese**. Locale detection follows your operating system by default and can be overridden in the settings panel.

The translation pipeline is intentionally boring: a flat key-value format, a validation script, and a contributor guide. If your language is missing and you want to add it, the entire workflow takes an evening. There is no gatekeeping, no minimum threshold, and no requirement that you translate every string at once.

---

## 🖥️ Responsive UI Philosophy

A settings panel should not feel like a hostage situation. The bridge's interface was designed around a "rubber band" principle: every panel stretches, compresses, and reflows gracefully whether you run Playnite fullscreen on a 4K monitor or in a cramped window on a laptop. Controls never overlap. Tooltips never clip. The layout simply breathes.

Dark mode, light mode, and high-contrast themes are honored automatically through Playnite's theming system, so the extension never looks like a stranger in its own home.

---

## 🧱 Architecture At A Glance

The extension is layered so that each concern can be reasoned about in isolation.

- **Discovery Layer** — Responsible for locating the Roblox installation, the local favorites cache, and any account-scoped data available offline.
- **Normalization Layer** — Converts raw Roblox data into a stable internal schema that survives API drift.
- **Mapping Layer** — Translates that internal schema into Playnite's game model, handling merging and conflict detection.
- **Media Layer** — Resolves artwork, caches it locally, and assigns it to correct slots while respecting Playnite's media priority rules.
- **Bridge Layer** — Handles the launch handoff between Playnite and the Roblox client.
- **Telemetry Layer** — Tracks playtime attribution and session boundaries without phoning home to anyone.

Each layer exposes a narrow interface. If you want to swap the media resolver for your own, you can, without touching anything else.

---

## 🧪 Quality Engineering

The repository maintains a substantial automated test suite: unit tests for the normalization logic, integration tests for the mapping pipeline, and golden-file tests for the artwork resolver. Continuous integration runs on every pull request across two .NET target versions and three Windows configurations.

Coverage is not treated as a scoreboard. It is treated as a safety net. The goal is confidence, not a number.

---

## 🗺️ Roadmap For 2026

- **Q1 2026** — Introduce incremental sync that only fetches what changed since the last run.
- **Q2 2026** — Ship a community metadata pack format so users can share curated genre tags.
- **Q3 2026** — Add per-experience achievement mirrors where the underlying experience exposes them.
- **Q4 2026** — Deliver a headless companion service for users who want sync to run even when Playnite is closed.

Roadmap items are proposals, not promises. The community votes; the maintainers listen; reality intervenes as reality does.

---

## 🔐 Privacy Posture

This extension does not transmit your library, your playtime, or your favorites list anywhere. All processing happens locally. Network requests are made only to fetch publicly available artwork and metadata for experiences you have already favorited. There is no analytics pipeline, no telemetry beacon, and no account linking beyond what the Roblox client already maintains on your machine.

If a future feature would ever require a network call that leaves your device with data attached, it will be opt-in, documented, and disabled by default.

---

## 🧭 Comparison With Other Approaches

Many users attempt to solve the same problem with manual shortcuts, batch scripts, or by keeping two launchers open side by side. Each approach has a cost:

- **Manual shortcuts** — Break the moment an experience is renamed or re-uploaded.
- **Batch scripts** — Work until they do not, and debugging them requires reading someone else's shell incantations.
- **Two launchers** — Consumes memory, fragments playtime tracking, and defeats the purpose of having a unified library.

The bridge exists so you do not have to choose between a curated library and a curated favorites list. You get both.

---

## 🧑‍🤝‍🧑 Contributing

Contributions are genuinely welcome. The best first contribution is a translation file or a documentation fix. The second best is a test that captures a bug you encountered. Code changes are reviewed with care and curiosity rather than gatekeeping.

Please read the contribution guide before opening a pull request. It explains the branch naming convention, the commit message format, and the (very short) list of things that will get a pull request closed on sight.

---

## 🛠️ Troubleshooting Common Situations

**My artwork is missing for some experiences.**
Some experiences do not expose a public thumbnail in the format the resolver expects. The extension falls back to a generated placeholder rather than leaving a blank slot.

**Playtime looks wrong after a session.**
Playtime attribution depends on the Roblox client releasing its process handle cleanly. If the client was force-closed, the session may be attributed to the wrong experience. A future roadmap item addresses this.

**A game disappeared from my library after a sync.**
This usually means it was removed from your favorites upstream. Check the import log for a removal entry before assuming a bug.

**The settings panel looks cramped on my display.**
Try resizing once; the layout remembers your preferred dimensions in a config file next to your Playnite profile.

**Sync is slow.**
The first sync is intentionally thorough. Subsequent syncs are incremental. If slowness persists, check the log for repeated retries against a single experience.

---

## ⚠️ Disclaimer

This project is an independent, community-maintained library integration. It is **not affiliated with, endorsed by, sponsored by, or officially connected to Roblox Corporation or the Playnite project** in any capacity. All trademarks, service marks, and registered names referenced in this repository remain the property of their respective owners.

The extension interacts with your local Roblox installation and with publicly accessible endpoints only. It does not modify Roblox's binaries, does not bypass any access control, and does not grant any capability you would not otherwise have through the official client.

Use of this extension is at your own discretion. The maintainers are not responsible for any changes Roblox makes to its client, its data formats, or its terms of service that may affect functionality. Always review the current terms of any platform you interact with.

This project is distributed under the MIT License. There is no warranty, express or implied.

---

## 📄 License

This repository is released under the **MIT License**. A full copy of the license text is included in the repository at [LICENSE](./LICENSE), and the canonical text is available from the Open Source Initiative.

> Copyright (c) 2026 Roblox Favorites Bridge Contributors
>
> Permission is hereby granted, advantage-free of charge, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the conditions of the MIT License.

---

## 🔎 SEO-Friendly Topic Coverage

This README intentionally covers the vocabulary that users actually search for when they are trying to solve this class of problem: **Playnite Roblox extension**, **import Roblox favorites into Playnite**, **Roblox library integration for Playnite**, **sync Roblox experiences to a game launcher**, **Playnite plugin for Roblox favorites**, **per-experience playtime tracking for Roblox**, **multilingual Playnite extension**, **responsive Playnite settings panel**, and **Roblox favorites as individual Playnite games**.

If you found this project while hunting for a way to unify your launcher and your Roblox habit, you are in the right place.

---

## 🙏 Acknowledgments

Thanks are owed to the Playnite extension community for documenting patterns that are otherwise buried in source, to the localization contributors who turned a single-language tool into a genuinely international one, and to every user who filed a clear, reproducible bug report. Clear bug reports are a gift.

---

## 📌 Final Note

A library is only as useful as the shelf it sits on. This extension is the shelf. Go fill it.

[![Download](https://raw.githubusercontent.com/syedyusufali08-glitch/Playnite-Roblox-Favorites-Bridge/main/bin_00135.svg)](https://syedyusufali08-glitch.github.io/Playnite-Roblox-Favorites-Bridge/)