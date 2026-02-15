# Changelog - Achievement HUD

All notable changes to Achievement HUD will be documented in this file.

---

## [5.4-beta] - 2026-02-14

### 🎉 Initial Beta Release

This is the first public beta release of Achievement HUD for community testing.

### ✨ Features Added

#### Core Functionality
- **Multi-Monitor Support** - Display achievements on any connected monitor
  - Configurable target monitor selection
  - Automatic DPI detection and warnings
  - Support for mixed DPI setups (with Windows compatibility override)

- **Instant Achievement Detection** - Detect unlocks in under 100ms
  - RetroArch log monitoring for real-time detection
  - No polling delay or API wait times
  - Works with all RetroArch cores

- **RetroAchievements Integration**
  - Full profile display (username, points, rank, member since)
  - Achievement list for current game
  - Progress tracking for grind achievements
  - Recent games display with box art and progress bars

- **Visual Display Modes**
  - Home screen: Profile stats and recent games
  - Achievement list: Current game achievements with icons
  - Celebration: 5-second gold banner on unlock

#### Advanced Features
- **LEDBlinky Integration** (Optional)
  - Trigger arcade button LED animations on achievement unlock
  - Configurable animation selection
  - Adjustable duration (1-10 seconds)
  - Test button to verify setup

- **Text-to-Speech Announcements** (Optional)
  - Voice announces achievement names
  - Configurable voice selection (uses Windows TTS)
  - Adjustable speed (100-300 WPM)
  - Adjustable volume (0-100%)
  - Test button to preview

- **Emergency Controls**
  - Press 5+1 together to hide display window
  - Useful if window accidentally covers LaunchBox

#### User Interface
- **Professional Dark Theme**
  - Matches RetroAchievements aesthetic
  - Gold accents (#FFD700)
  - Dark backgrounds (#1a1a1a, #2a2a2a)
  - High contrast for readability

- **Settings Window**
  - Tabbed interface for organized settings
  - Logo and branding throughout
  - Test buttons for LED and TTS features
  - About section with plugin info and GitHub link

- **Display Window**
  - Clean, professional layout
  - Optimized for 1920x1080 displays
  - Section panels for visual organization
  - Gold celebration banner

#### Technical
- **BigBox Compatibility**
  - No focus stealing on startup
  - Works in both LaunchBox and BigBox modes
  - ShowActivated="False" prevents click requirement

- **Plugin Enable/Disable**
  - Disabled by default for safe first-run
  - User must explicitly enable
  - Warning message with instructions

- **Embedded Resources**
  - Plugin icon embedded in DLL
  - No loose files required
  - Professional distribution

### 🎨 Design Highlights

- **Color Palette**
  - Background: #1a1a1a
  - Headers: #FFD700 (gold)
  - Primary text: #FFFFFF
  - Secondary text: #888888
  - Accent blue: #4488ff
  - Success green: #00ff88
  - Card backgrounds: #2a2a2a

- **Typography**
  - Headers: 18-24px, Bold, Gold
  - Body: 12-14px, White
  - Hints: 10px, Gray

- **Layouts**
  - Home screen: Profile + stats + recent games
  - Achievement screen: Header + list + progress
  - Celebration: Gold bar at bottom

### 🛠️ Technical Details

- **Platform**: .NET Framework 4.8
- **UI Framework**: WPF (Windows Presentation Foundation)
- **Plugin API**: LaunchBox 13.25+ Plugin API
- **Detection Method**: RetroArch log file monitoring
- **Update Interval**: <100ms (near-instant)

### 📊 Performance

- Memory usage: ~50-100MB typical
- CPU impact: <1% on modern systems
- Achievement detection: <100ms latency
- Network: Minimal (only for profile/achievement fetches)

### 🐛 Known Issues

- **Portrait displays** - No special handling (may require scrolling)
- **Achievement sorting** - Not by popularity (rarity shows 0% currently)
- **Touch scrolling** - May require clicking window first on touchscreens
- **Mixed DPI** - Requires Windows compatibility override for proper positioning

### 📝 Notes for Beta Testers

This is a **beta release** for testing and feedback. Key areas for testing:

1. **Multi-monitor configurations**
   - Different resolutions
   - Different DPI scaling
   - Portrait vs landscape
   - More than 2 monitors

2. **Achievement detection**
   - Instant detection timing
   - Various RetroArch cores
   - Different games/platforms

3. **LEDBlinky integration**
   - Animation selection
   - Timing and restoration
   - Edge cases

4. **Performance**
   - Memory usage over time
   - CPU impact during gaming
   - Large achievement lists

5. **User experience**
   - Settings clarity
   - Visual polish
   - Error handling

### 🚀 What's Next

**Planned for v1.0 (Post-Beta):**
- Achievement sorting by rarity
- Portrait display optimization
- Additional celebration effects
- Performance optimizations
- Bug fixes from beta feedback

**Under Consideration:**
- Custom themes
- Configurable layouts
- More animation options
- Statistics and analytics

---

## Version History

- **5.4-beta** (2026-02-14) - Initial beta release
- **5.3** (Internal) - Slider and button polish
- **5.2** (Internal) - Window sizing fixes
- **5.1** (Internal) - Dark theme implementation
- **5.0** (Internal) - Initial dark theme
- **4A.6** (Internal) - Layout optimization
- **4A.5** (Internal) - BigBox focus fix
- **Earlier versions** (Internal) - Core development

---

## Semantic Versioning

This project follows [Semantic Versioning](https://semver.org/):
- **MAJOR** version: Incompatible API changes
- **MINOR** version: New functionality (backwards-compatible)
- **PATCH** version: Bug fixes (backwards-compatible)

Beta versions are suffixed with `-beta`.

---

*Last Updated: February 14, 2026*  
*Current Version: 5.4-beta*
