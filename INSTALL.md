# Installation Guide - Achievement HUD Beta
**Quick Setup for Beta Testers**

---

## 📥 Download & Install

### Step 1: Download
Download the latest beta release:
- `AchievementHUD-v5.4-beta.zip`

### Step 2: Extract
Extract the ZIP file to get:
- `TrailerVert.DisplayPlugin.dll`

### Step 3: Install
Copy the DLL to your LaunchBox plugins folder:

**Windows File Path:**
```
C:\LaunchBox\Plugins\TrailerVert.DisplayPlugin\
```

**Create the folder if it doesn't exist!**

**Final structure should be:**
```
LaunchBox/
└── Plugins/
    └── TrailerVert.DisplayPlugin/
        └── TrailerVert.DisplayPlugin.dll  ← Your file here
```

### Step 4: Restart LaunchBox
Close and restart LaunchBox completely.

---

## ⚙️ First-Time Configuration

### 1. Open Settings
1. Launch LaunchBox
2. Go to **Tools → Achievement HUD**
3. Settings window opens

### 2. Enable the Plugin
⚠️ **Important**: Plugin is disabled by default for safety!

1. Check the box: **"Enable Plugin"**
2. Read the warning message
3. Continue with configuration below

### 3. Configure Display
**Monitor Selection:**
- Select which monitor to display achievements on
- Usually "Monitor 2" for secondary displays

**Celebration Duration:**
- Default: 5 seconds
- Adjust slider to your preference (1-10 seconds)

### 4. Configure RetroArch Log
**For Instant Achievement Detection (<100ms):**

1. Click the **RetroArch** tab
2. Click **Browse...** button
3. Navigate to your RetroArch installation
4. Find: `RetroArch/logs/retroarch.log`
5. Select the file

**Common Locations:**
- `C:\RetroArch\logs\retroarch.log`
- `C:\Program Files\RetroArch\logs\retroarch.log`
- `%AppData%\RetroArch\logs\retroarch.log`

**If log file doesn't exist:**
1. Open RetroArch
2. Settings → Logging → Enable Logging
3. Restart RetroArch
4. Log file should now be created

### 5. Save Settings
1. Click **Save** button (bottom right, gold button)
2. **Restart LaunchBox** for changes to take effect

---

## ✅ Verify Installation

### Check Plugin is Active
1. Restart LaunchBox
2. Tools menu should show **"Achievement HUD"** with arcade icon
3. Display window should appear on your selected monitor

### Test the Display
1. Launch any RetroAchievements-enabled game
2. Achievement list should appear on secondary monitor
3. Unlock an achievement to test celebration animation

### Emergency Controls
- Press **5 + 1** together to hide the display window if needed

---

## 🎯 Optional Features

### LEDBlinky (Arcade Cabinets)
**Only if you have LEDBlinky installed:**

1. Click **LEDBlinky** tab
2. Check **"Enable LEDBlinky LED Animations"**
3. Click **Browse...** and select LEDBlinky installation folder
4. Choose animation from dropdown
5. Set duration (default: 5 seconds)
6. Click **Test Animation** to verify
7. Click **Save**

### Text-to-Speech
**For voice announcements:**

1. Click **Text-to-Speech** tab
2. Check **"Enable Voice Announcements"**
3. Select voice from dropdown
4. Adjust speed (default: 175 WPM)
5. Adjust volume (default: 100%)
6. Click **Test Voice** to hear it
7. Click **Save**

---

## 🐛 Common Issues

### Plugin Doesn't Show in Tools Menu
**Solution:**
1. Verify DLL is in correct folder
2. Folder must be named exactly: `TrailerVert.DisplayPlugin`
3. Restart LaunchBox completely
4. Check LaunchBox version (requires 13.25+)

### Display Window Doesn't Appear
**Solution:**
1. Open settings (Tools → Achievement HUD)
2. Verify **"Enable Plugin"** is checked
3. Save and restart LaunchBox
4. Check monitor selection is correct

### RetroAchievements Not Configured
**Solution:**
1. Go to LaunchBox: Tools → Options
2. Click **Integrations** tab
3. Configure **RetroAchievements** section
4. Enter username and API key
5. Click OK and restart LaunchBox

### Achievements Not Detecting Instantly
**Solution:**
1. Verify RetroArch log path is correct
2. Check log file exists and is being written to
3. Enable logging in RetroArch if disabled
4. Try playing a game and checking log file updates

### Multi-Monitor DPI Issues
**If display appears on wrong monitor or wrong size:**

1. Close LaunchBox
2. Right-click `LaunchBox.exe` → Properties
3. **Compatibility** tab
4. Click **"Change high DPI settings"**
5. Check **"Override high DPI scaling behavior"**
6. Select **"Application"** from dropdown
7. Click OK → OK
8. Restart LaunchBox

This is especially important if your monitors have different DPI scaling (e.g., 4K @ 200% + 1080p @ 100%).

---

## 📊 Quick Settings Reference

| Setting | Recommended | Notes |
|---------|------------|-------|
| Plugin Enabled | ✅ Checked | Must enable to work |
| Target Monitor | Monitor 2 | Your secondary display |
| Celebration Duration | 5 seconds | Adjust to preference |
| RetroArch Log Path | (your path) | Required for instant detection |
| LEDBlinky | Optional | Only if you have it |
| Text-to-Speech | Optional | Only if you want it |

---

## 🆘 Need Help?

### Beta Testing Support
- **GitHub Issues**: Report bugs and problems
- **Include**: LaunchBox version, Windows version, monitor setup
- **Screenshots**: Always helpful for visual issues

### Check First
1. Plugin is enabled in settings
2. RetroArch log path is correct
3. RetroAchievements configured in LaunchBox
4. LaunchBox restarted after changes
5. DLL is in correct folder

---

## ✅ Installation Complete!

You should now have:
- ✅ Achievement HUD showing in Tools menu
- ✅ Display window on your selected monitor
- ✅ Achievement detection working
- ✅ Settings configured to your preference

**Start playing and earning achievements!** 🎮🏆

---

*Installation Guide v5.4-beta*  
*Last Updated: February 14, 2026*
