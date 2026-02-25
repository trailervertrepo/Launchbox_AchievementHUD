# V6.7 Development Progress Log
**Date:** February 25, 2026  
**Status:** TESTER BUILD READY  
**Session:** Phase 6.7 — Multiset Support + Rarity Colors + Cursor Investigation

---

## COMPLETED THIS SESSION

### T2 — Multiset / Subset Support
**Status:** COMPLETE  
**Files:** `RetroAchievementService.cs`, `Achievement.cs`

The most significant feature this session. When a subset ROM is launched (e.g. `Super Mario Bros. (Subset - Bonus)`), the HUD now shows the full combined achievement list instead of only the subset achievements.

**Root cause investigation spanned three builds:**

**Build 1 — Architecture discovery**  
Established that the LaunchBox API does NOT return a flat mixed list of 77 achievements. It returns only the subset's 34 achievements when given the subset's RA game ID (16561). The 8/77 count on the home screen comes from `GetUserSummary` which queries the RA server directly. The plugin was missing 43 base game achievements entirely.

**Build 2 — First merge attempt (failed)**  
Added `ParseSubsetLabel` / `StripSubsetLabel` / `FindBaseGameId` to detect subset titles and fetch the base game separately. Detection and title parsing worked correctly. Merge failed because `FindBaseGameId` used `GetConsoles()` + `GetGamesForConsole()` with a hardcoded platform name map. Two problems: (1) the RA API returns `"NES/Famicom"` not `"NES"`, (2) users can name consoles anything in LaunchBox — a hardcoded map is fundamentally wrong. Also caused a performance bug: the full API lookup was firing on every achievement poll cycle (10+ times per session).

**Build 3 — DataManager approach (success)**  
Replaced `FindBaseGameId` entirely. Instead of calling the RA API, it now uses `PluginHelper.DataManager.GetAllGames()` to search the LaunchBox library directly and reads `RetroAchievementsId` off the matching `IGame` entry — the same field `FindGameId` Strategy 0 already uses. No console name mapping, no RA API calls, no platform string assumptions. Added `_baseGameIdCache` so the library search only runs once per title+platform.

**Result confirmed in debug log:**
```
[OK] Loaded 77 achievements from ID 1446 (set: Base Set)
[OK] Loaded 34 achievements from ID 16561 (set: Bonus)
[OK] Merged 77 base + 34 subset = 111 total
```

Note: 111 is the correct count. The home screen shows 8/77 because `GetUserSummary` only tracks base game progress server-side. The in-game HUD showing 111 is the accurate combined view matching what RetroArch loads.

Added `SetName` property to `Achievement.cs` — each achievement now carries its set membership ("Base Set" or subset label e.g. "Bonus"). This is the foundation for section headers in a future display pass.

---

### Priority 2 #3 — Rarity Badge Colors
**Status:** COMPLETE — Confirmed working by developer  
**Files:** `AchievementListItem.cs`, `DisplayWindow.xaml`

Achievement list items now use color coding driven by `WonByPercentage`:

| Rarity | Threshold | Left Border | Background Tint |
|--------|-----------|-------------|-----------------|
| Unlocked | — | Green `#00ff88` | Dark green |
| Common | 50%+ | Blue `#4488ff` | Dark blue |
| Uncommon | 20–50% | Gold `#FFD700` | Dark gold |
| Rare | 5–20% | Orange `#FF9800` | Dark orange |
| Very Rare | <5% | Red `#F44336` | Dark red |

A small rarity chip label (e.g. `RARE`, `VERY RARE`) appears below the description on locked achievements with matching border color. Hidden on unlocked achievements and when no WonBy data is available.

---

### T1 — Mouse Cursor in BigBox (Investigated, Deferred)
**Status:** DEFERRED — not worth pursuing  
**Files:** `DisplayWindow.xaml`, `DisplayWindow_xaml.cs`

Added `Cursor="Arrow"` to the Window element (WPF level) and a `WM_SETCURSOR` Win32 message hook via `HwndSource.AddHook` that intercepts cursor messages before WPF processes them and calls `SetCursor(arrow)` at the OS level.

Neither approach worked. Investigation determined that RetroArch (or BigBox) is calling `ShowCursor(false)` at the system level while a game is running, which hides the cursor globally across all monitors regardless of what individual windows request. The cursor reappears on the taskbar and after the game exits, confirming system-level suppression.

Scroll wheel functionality confirmed working. Cursor visibility during gameplay is not worth fighting — it would require a polling timer calling `ShowCursor(true)` which could interfere with gameplay on the primary monitor. Deferred indefinitely.

---

## KNOWN ISSUE — DisplayWindow_xaml.cs Corrupted Debug Strings

The original project file contains corrupted UTF-8 multi-byte characters in many `Debug.WriteLine` strings (legacy emoji characters that were not cleaned up when the file was originally written). These do not affect runtime behavior but cause `str_replace` to fail on those lines during development, requiring Python line-range replacements as a workaround.

**Planned fix:** Full clean rewrite of `DisplayWindow_xaml.cs` in a future dedicated cleanup session, matching the approach used for `RetroAchievementService.cs` in V6.6.

---

## PENDING — V6.7 Remaining Items

| Item | Description | Status |
|------|-------------|--------|
| B | Mastery notification | Not started |
| A | Game placard on launch | Not started |
| Priority 2 #1 | Completion bar in game header | Not started |
| Priority 2 #2 | Points display in game header | Not started |
| C + D | Challenge indicators + live progress popup | Not started |
| E | Leaderboard tracker | Not started |

---

## ARCHITECTURAL NOTES FOR FUTURE SESSIONS

**DataManager pattern established:** `PluginHelper.DataManager.GetAllGames()` is the correct way to cross-reference any LaunchBox game data. Always prefer this over RA API calls when the data may already be in the library. Platform name strings on `IGame` are user-defined and cannot be used for matching against external systems.

**Multiset detection pattern:** `ParseSubsetLabel(title)` returns the subset label string or null. `StripSubsetLabel(title)` returns the base game title. Both use regex matching on `(Subset - X)` and `[Subset - X]` formats. These are stable utilities for any future multiset display work.

**SetName on Achievement:** Every achievement now carries `SetName` ("Base Set" or subset label). Section header display in `UpdateAchievementList()` can group by this field without any additional data fetching.

**Cache pattern:** `_baseGameIdCache` on `RetroAchievementService` stores base game ID lookups keyed by `"title|platform"`. Empty string = confirmed not found (avoids re-querying). This pattern should be applied to any other expensive per-poll lookups discovered in future sessions.

---

*Build delivered to testers February 25, 2026.*
