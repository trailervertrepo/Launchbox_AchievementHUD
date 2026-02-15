# Achievement HUD
**RetroAchievements Display Plugin for LaunchBox & BigBox**

![Version](https://img.shields.io/badge/version-5.4--beta-blue)
![LaunchBox](https://img.shields.io/badge/LaunchBox-13.25%2B-green)
![Status](https://img.shields.io/badge/status-beta-orange)

Display your RetroAchievements on a secondary monitor with instant detection, multi-monitor support, and arcade cabinet integration.

---

## ✨ Features

### Core Functionality
- **Instant Achievement Detection** - Detects unlocks in under 100ms via RetroArch log monitoring
- **Multi-Monitor Support** - Configurable display on any connected monitor
- **RetroAchievements Profile Display** - Shows your stats, points, rank, and recent games
- **Achievement List View** - Complete game achievement list with progress tracking
- **Celebration Animations** - 5-second gold banner when achievements unlock

### Advanced Features
- **LEDBlinky Integration** - Trigger arcade button LED animations on achievement unlock
- **Text-to-Speech Announcements** - Voice announces achievement names (optional)
- **Emergency Hotkey** - Press 5+1 together to hide the display window
- **BigBox Compatible** - Works seamlessly in both LaunchBox and BigBox modes
- **Professional Dark Theme** - Matches RetroAchievements gold/dark aesthetic

---

## 📸 Screenshots

> <img width="1920" height="1080" alt="Screenshot 2026-02-15 121425" src="https://github.com/user-attachments/assets/a353d891-e783-4d42-ac2c-f9801e2761e3" />
  <img width="1920" height="1080" alt="Screenshot 2026-02-15 081032" src="https://github.com/user-attachments/assets/c1803b0f-44cf-43a2-8e43-b24b5c497ef7" />


---

## 🎯 Target Audience

This plugin is perfect for:
- **Arcade Cabinet Builders** - Display achievements on a vertical marquee screen
- **Multi-Monitor Gaming Setups** - Dedicated achievement display
- **RetroAchievements Enthusiasts** - Show off your progress while gaming
- **LaunchBox/BigBox Users** - Seamless integration with your existing setup

---

## 📋 Requirements

### Minimum Requirements
- **LaunchBox** version 13.25 or higher
- **RetroAchievements Account** - Configure credentials in LaunchBox
- **RetroArch** - For instant achievement detection
- **.NET Framework** 4.8 or higher (usually already installed)
- **Windows** 10/11

### Recommended Setup
- **Second Monitor** - For dedicated achievement display (1920x1080 recommended)
- **RetroArch Log Enabled** - For instant detection (path configured in settings)

### Optional
- **LEDBlinky** - For arcade button LED animations
- **Text-to-Speech Voices** - For voice announcements (Windows built-in)

---

## 📥 Installation

### Quick Install
1. **Download** the latest release:
2. **Extract** the ZIP file
3. **Copy** `AchievementHUD.dll` to:
   ```
   LaunchBox/Plugins/TrailerVert.DisplayPlugin/
   ```
   (Create the folder if it doesn't exist)
4. **Restart LaunchBox**
5. **Configure** via Tools → Achievement HUD

### First-Time Setup
1. Open LaunchBox
2. Go to **Tools → Achievement HUD**
3. Check **"Enable Plugin"** (disabled by default for safety)
4. Configure your settings:
   - Select target monitor
   - Set RetroArch log path (usually `RetroArch/logs/retroarch.log`)
   - Adjust celebration duration (default: 5 seconds)
5. Click **Save**
6. **Restart LaunchBox** for changes to take effect

---

## ⚙️ Configuration

### Display Settings
- **Target Monitor** - Choose which monitor displays achievements
- **Celebration Duration** - How long the achievement banner shows (1-10 seconds)

### RetroAchievements
- Credentials configured in LaunchBox (Tools → Options → Integrations → RetroAchievements)
- Plugin reads your existing LaunchBox RA configuration

### RetroArch Log Monitoring
- **Log File Path** - Point to your `retroarch.log` file for instant detection
- **Default Location**: `RetroArch/logs/retroarch.log`
- Enable logging in RetroArch settings if not already on

### LEDBlinky (Optional)
- **Enable LED Animations** - Toggle arcade button effects
- **Installation Folder** - Path to LEDBlinky.exe
- **Animation** - Choose which LED pattern to play
- **Duration** - How long LEDs animate (1-10 seconds)

### Text-to-Speech (Optional)
- **Enable Voice Announcements** - Toggle TTS on/off
- **Voice** - Select from installed Windows voices
- **Speed** - Adjust speech rate (100-300 WPM)
- **Volume** - Control announcement volume (0-100%)

---

## 🎮 Usage

### Automatic Display
The plugin automatically shows:
1. **Home Screen** - When LaunchBox starts (shows your profile and stats)
2. **Game Achievements** - When you launch a RetroAchievements-enabled game
3. **Celebration Banner** - When you unlock an achievement (5-second gold bar)

### Manual Controls
- **Emergency Hide** - Press `5` and `1` keys together to hide the display window
- **Settings** - Tools → Achievement HUD in LaunchBox menu

### Display Modes
- **Home Screen** - RetroAchievements profile with stats and recent games
- **Achievement List** - Current game's achievements with unlock status
- **Celebration** - Brief gold banner overlay when achievement unlocks

---

## 🐛 Known Issues (Beta)

### Current Limitations
- **Portrait Mode** - No special handling for vertical displays (may require scrolling)
- **Achievement Sorting** - Not sorted by popularity (all show 0% rarity currently)
- **Touch Scrolling** - May require clicking window first to scroll on touchscreens

### Workarounds
- **Multi-Monitor DPI Issues** - If monitors have different DPI scaling:
  1. Right-click `LaunchBox.exe` → Properties
  2. Compatibility → Change High DPI Settings
  3. Check "Override high DPI scaling behavior"
  4. Select "Application"
  5. Restart LaunchBox

---

## 🔧 Troubleshooting

### Display Window Doesn't Show
1. Check plugin is **enabled** in settings
2. Verify RetroAchievements configured in LaunchBox
3. Restart LaunchBox after enabling plugin
4. Check correct monitor selected in settings

### Achievements Not Detecting Instantly
1. Verify RetroArch log path is correct
2. Enable logging in RetroArch settings
3. Test that log file is being written to
4. Check file permissions on log directory

### Window Covers LaunchBox
1. Press `5` and `1` keys together (emergency hide)
2. Check target monitor setting
3. Verify multi-monitor configuration

### LEDBlinky Not Working
1. Verify LEDBlinky installation path is correct
2. Test animation using "Test Animation" button
3. Check LEDBlinky.exe exists in specified folder
4. Ensure animation files are present

---

## 📊 Performance

- **Achievement Detection** - Under 100ms (via log monitoring)
- **Memory Usage** - ~50-100MB (typical)
- **CPU Impact** - Minimal (<1% on modern systems)
- **Network** - Only when fetching profile/achievement data (minimal)

---

## 🤝 Contributing

This is currently a **beta release** for testing. Feedback is greatly appreciated!

### How to Help
- **Test the plugin** on your setup
- **Report bugs** via GitHub Issues
- **Share screenshots** of your display setup
- **Suggest features** for future versions

### Beta Feedback Needed
- Multi-monitor configurations (different resolutions/DPI)
- Portrait/vertical display testing
- LEDBlinky integration testing
- Performance on various hardware
- Edge cases and unusual setups

---

## 📝 Changelog

### Version 5.4-beta (Current)
**Initial Beta Release**
- ✅ Multi-monitor support with configurable target
- ✅ Instant achievement detection (<100ms)
- ✅ RetroAchievements profile display
- ✅ Achievement list with progress tracking
- ✅ 5-second celebration animation
- ✅ LEDBlinky integration (optional)
- ✅ Text-to-Speech announcements (optional)
- ✅ Emergency hotkey (5+1 to hide)
- ✅ Professional dark theme UI
- ✅ BigBox focus fix (no click needed)

---

## 🛠️ Technical Details

### Architecture
- **Plugin Type**: LaunchBox ISystemMenuItemPlugin + ISystemEventsPlugin
- **Framework**: .NET Framework 4.8 / C# / WPF
- **Detection Method**: RetroArch log file monitoring
- **API Integration**: LaunchBox RetroAchievements API

### File Structure
```
LaunchBox/Plugins/TrailerVert.DisplayPlugin/
├── TrailerVert.DisplayPlugin.dll  (Main plugin - icon embedded)
└── settings.json                  (Created on first run)
```

### Settings Storage
Settings are stored in JSON format at:
```
%AppData%\LaunchBox\Plugins\TrailerVert.DisplayPlugin\settings.json
```

---

## 📜 License

> *License information to be added*

---

## 👤 Author

**TrailerVert**
- GitHub: [@trailervertrepo](https://github.com/trailervertrepo)

---

## 🙏 Acknowledgments

- **LaunchBox/BigBox** - For the excellent plugin API
- **RetroAchievements** - For the amazing achievement tracking service
- **RetroArch** - For log-based achievement detection
- **LEDBlinky** - For arcade LED integration support
- **Beta Testers** - For helping refine this plugin!

---

## 📞 Support

### For Beta Testers
- **Issues**: Open a GitHub Issue with detailed information
- **Questions**: Post in GitHub Discussions
- **Feedback**: Submit via Issues or Discussions

### Information to Include in Bug Reports
- LaunchBox version
- Windows version
- Monitor setup (resolutions, DPI scaling)
- Steps to reproduce
- Screenshots/logs if applicable

---

## 🚀 Roadmap

### Planned Features (Post-Beta)
- Achievement sorting by rarity/popularity
- Portrait display optimization
- Custom theme support
- Additional celebration effects
- Configurable layout options
- More LEDBlinky animation options

### Under Consideration
- Steam achievement support
- Custom achievement sound effects
- Achievement statistics/analytics
- Integration with other emulators
- Mobile companion app

---

## ⚠️ Beta Testing Notice

This is a **beta release** intended for testing and feedback. While fully functional, there may be:
- Minor bugs or edge cases
- Performance variations on different setups
- UI refinements needed
- Feature additions based on feedback

**Please report any issues you encounter!** Your feedback helps make this plugin better for everyone.

---

**Thank you for testing Achievement HUD!** 🎮🏆

---

*Last Updated: February 14, 2026*  
*Version: 5.4-beta*
