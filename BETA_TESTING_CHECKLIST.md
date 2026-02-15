# Beta Testing Checklist - Achievement HUD v5.4

**Thank you for beta testing Achievement HUD!**

Use this checklist to systematically test the plugin and provide valuable feedback.

---

## 📋 System Information

Before testing, please provide:

- [ ] LaunchBox version: _______________
- [ ] Windows version: _______________
- [ ] Monitor setup: _______________
  - Monitor 1: Resolution _______ DPI _______
  - Monitor 2: Resolution _______ DPI _______
- [ ] RetroArch version: _______________

---

## ✅ Basic Installation

- [ ] Downloaded ZIP file successfully
- [ ] Extracted DLL file
- [ ] Copied to `LaunchBox/Plugins/TrailerVert.DisplayPlugin/`
- [ ] Restarted LaunchBox
- [ ] Plugin appears in Tools menu as "Achievement HUD"
- [ ] Plugin icon shows in menu (arcade cabinet)

---

## ⚙️ Settings Configuration

### Opening Settings
- [ ] Tools → Achievement HUD opens settings window
- [ ] Settings window shows logo in header
- [ ] Window title shows "Achievement HUD Settings"
- [ ] All tabs are visible (Display, RetroAchievements, RetroArch, LEDBlinky, Text-to-Speech, Advanced)

### Display Tab
- [ ] Monitor dropdown shows all connected monitors
- [ ] Can select different monitors
- [ ] Celebration duration slider works (1-10 seconds)
- [ ] Slider shows gold thumb/marker
- [ ] Value updates when sliding

### RetroAchievements Tab
- [ ] Shows RA status (configured/not configured)
- [ ] Username field shows (read-only)
- [ ] API key field shows (read-only)
- [ ] Blue info text is readable

### RetroArch Tab
- [ ] Log path text box is editable
- [ ] Browse button has gold border
- [ ] Can browse and select log file
- [ ] Path saves correctly

### LEDBlinky Tab (if applicable)
- [ ] Enable checkbox works
- [ ] Path browse button works (gold border)
- [ ] Animation dropdown populates
- [ ] Duration slider works (gold thumb)
- [ ] Test button works (gold border, fills on hover)
- [ ] Animation triggers when tested

### Text-to-Speech Tab (if applicable)
- [ ] Enable checkbox works
- [ ] Voice dropdown shows available voices
- [ ] Speed slider works (gold thumb)
- [ ] Volume slider works (gold thumb)
- [ ] Test button works (gold border, fills on hover)
- [ ] Voice announcement plays when tested

### Advanced Tab
- [ ] Debug logging checkbox works
- [ ] About section shows:
  - [ ] Plugin logo (64x64)
  - [ ] "Achievement HUD" title
  - [ ] Version number (5.4)
  - [ ] "by TrailerVert" credit
  - [ ] Description text
  - [ ] GitHub link (blue, clickable)
  - [ ] Opens browser when clicked
  - [ ] Config file path shown
  - [ ] Feature list visible

### Save/Cancel Buttons
- [ ] Cancel button works (dark with gold border on hover)
- [ ] Save button is gold and prominent
- [ ] Save button shows feedback on hover
- [ ] Settings save successfully
- [ ] Confirmation message appears

---

## 🖥️ Display Window

### Home Screen (No Game Running)
- [ ] Display window appears on selected monitor
- [ ] Shows on correct monitor
- [ ] Logo and "RETROACHIEVEMENTS PROFILE" header visible
- [ ] Profile picture shows (if available)
- [ ] Username displays correctly
- [ ] Member since date shows
- [ ] "NOW PLAYING:" shows "Waiting for game..."
- [ ] Stats cards show:
  - [ ] Points
  - [ ] Rank
  - [ ] True Points
- [ ] Recent games section shows:
  - [ ] Game box art (235x235)
  - [ ] Game titles
  - [ ] Achievement counts (e.g., "6/10")
  - [ ] Gold progress bars (fully visible, no scrolling)

### Achievement List (Game Running)
- [ ] Launches when game starts
- [ ] Shows game title and platform
- [ ] Shows overall progress (X of Y completed)
- [ ] Progress bar shows completion
- [ ] Achievement cards display:
  - [ ] Achievement icon (if available)
  - [ ] Achievement title
  - [ ] Description
  - [ ] Points value
  - [ ] Unlock status (✓ for unlocked, 🔒 for locked)
- [ ] Unlocked achievements have green checkmark
- [ ] Locked achievements have gray lock
- [ ] Cards are readable and properly spaced

### Celebration Animation
- [ ] Triggers when achievement unlocks
- [ ] Shows gold banner at bottom
- [ ] Displays "ACHIEVEMENT UNLOCKED!"
- [ ] Shows achievement name
- [ ] Lasts configured duration (default 5 seconds)
- [ ] Disappears after duration
- [ ] Returns to achievement list

---

## 🎮 Achievement Detection

### Instant Detection
- [ ] Achievement unlocks detected within 1 second
- [ ] Multiple achievements in quick succession detected
- [ ] Detection works across different games
- [ ] Detection works across different cores

### Log Monitoring
- [ ] Works with configured log path
- [ ] Still works if log file is deleted/recreated
- [ ] No lag or delay in detection

---

## 🎨 Visual Quality

### Color Scheme
- [ ] Dark backgrounds (#1a1a1a, #2a2a2a)
- [ ] Gold headers and accents (#FFD700)
- [ ] White primary text (readable)
- [ ] Gray secondary text (readable)
- [ ] High contrast throughout

### UI Elements
- [ ] All sliders have visible gold thumb markers
- [ ] Progress bars are gold and visible
- [ ] Buttons have proper styling:
  - [ ] Save = gold
  - [ ] Cancel/Browse = dark with gold border
  - [ ] Test = thick gold border
- [ ] ComboBox dropdowns are dark with white text
- [ ] Section panels visible and properly spaced
- [ ] No overlapping elements
- [ ] No cut-off text

### Typography
- [ ] All text is readable
- [ ] No font rendering issues
- [ ] Headers stand out
- [ ] Hint text is de-emphasized but visible

---

## 🔧 Functionality

### Emergency Hotkey
- [ ] Press 5+1 together hides window
- [ ] Works with keyboard
- [ ] Works with numpad
- [ ] Works with arcade encoder (if applicable)

### Multi-Monitor
- [ ] Display appears on selected monitor
- [ ] Can switch monitors in settings
- [ ] Window positions correctly on selected monitor
- [ ] DPI scaling handled correctly (if mixed DPI)

### BigBox Compatibility
- [ ] Works in BigBox mode
- [ ] Doesn't steal focus from BigBox
- [ ] BigBox remains clickable after plugin loads
- [ ] No need to click BigBox to use it

---

## 🐛 Issues & Bugs

Please report any issues you encounter:

### Visual Issues
- Describe: ____________________________________
- Screenshot: [ ] Attached

### Functional Issues
- Describe: ____________________________________
- Steps to reproduce: ____________________________________

### Performance Issues
- Memory usage: ____________________________________
- CPU usage: ____________________________________
- Lag/stuttering: ____________________________________

### Edge Cases
- Unusual behavior: ____________________________________
- Specific games/cores: ____________________________________

---

## 💡 Feedback & Suggestions

### What Works Well
- ____________________________________

### What Could Be Improved
- ____________________________________

### Feature Requests
- ____________________________________

### Overall Experience
- [ ] Excellent
- [ ] Good
- [ ] Average
- [ ] Needs Work

---

## 📊 Performance Testing

### Long-Term Usage
- [ ] Tested for 1+ hour gaming session
- [ ] Memory usage stable (no leaks)
- [ ] CPU usage minimal
- [ ] No crashes or freezes

### Large Achievement Lists
- [ ] Tested games with 50+ achievements
- [ ] Scrolling works smoothly
- [ ] All achievements load correctly
- [ ] Performance remains good

---

## ✨ Optional Features Testing

### LEDBlinky (if equipped)
- [ ] Animations trigger correctly
- [ ] Timing is accurate
- [ ] Buttons restore to normal after animation
- [ ] No conflicts with other LED software

### Text-to-Speech (if enabled)
- [ ] Voice quality is acceptable
- [ ] Timing doesn't interrupt gameplay
- [ ] Volume level is appropriate
- [ ] Multiple voices work

---

## 📝 Final Notes

**Overall Rating:** _____ / 5 stars

**Would you recommend to others?** [ ] Yes [ ] No

**Additional Comments:**
____________________________________
____________________________________
____________________________________

---

**Thank you for your thorough testing!** 🎮🏆

Please submit this checklist along with any screenshots or logs to:
- GitHub Issues (for bugs)
- GitHub Discussions (for feedback)

*Beta Testing Checklist v5.4*  
*Achievement HUD by TrailerVert*
