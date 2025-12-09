# GitHub Deployment Guide

## 📁 Complete File Structure

Here's how to organize your files for GitHub Pages deployment:

```
engine-lubrication-program/
│
├── index.html                              # Main landing page (root)
├── README.md                               # GitHub documentation
├── TEACHER-GUIDE.md                        # Teacher instructions
├── LICENSE                                 # MIT License file
│
├── activities/
│   └── identify-friction-areas.html        # Interactive identifier activity
│
├── quizzes/
│   ├── single-player-quiz.html             # Individual assessment quiz
│   └── multiplayer-quiz.html               # WebRTC multiplayer quiz
│
└── resources/
    ├── engine-lubrication-presentation.pptx    # PowerPoint slides
    └── engine-lubrication-handout.docx         # Student handout
```

---

## 🚀 Deployment Instructions

### Option 1: GitHub Pages (Recommended)

#### Step 1: Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click the "+" icon → "New repository"
3. Name it: `engine-lubrication-program`
4. Description: "Complete learning program for teaching engine lubrication"
5. Choose "Public"
6. Click "Create repository"

#### Step 2: Upload Files

**Method A: Using GitHub Web Interface**

1. Click "uploading an existing file"
2. Drag all files maintaining folder structure:
   - Drag `index.html`, `README.md`, etc. to root
   - Create `activities` folder, upload files there
   - Create `quizzes` folder, upload files there
   - Create `resources` folder, upload files there
3. Commit changes

**Method B: Using Git Command Line**

```bash
# Navigate to your folder containing all files
cd path/to/your/files

# Initialize git repository
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: Complete engine lubrication program"

# Connect to GitHub
git remote add origin https://github.com/yourusername/engine-lubrication-program.git

# Push to GitHub
git branch -M main
git push -u origin main
```

#### Step 3: Enable GitHub Pages

1. Go to repository Settings
2. Scroll to "Pages" section (left sidebar)
3. Under "Source":
   - Select branch: `main`
   - Select folder: `/ (root)`
4. Click "Save"
5. Wait 1-2 minutes for deployment

#### Step 4: Access Your Site

Your site will be live at:
```
https://yourusername.github.io/engine-lubrication-program/
```

Share this URL with teachers and students!

---

### Option 2: School Network Deployment

#### For IT Administrators:

1. **Create Shared Folder**
   ```
   \\school-server\resources\engine-lubrication\
   ```

2. **Copy All Files**
   - Maintain folder structure exactly as shown above
   - Ensure students have read access

3. **Create Shortcut**
   - On student desktops
   - Points to: `\\school-server\resources\engine-lubrication\index.html`

4. **Set Permissions**
   - Read-only for students
   - Read/write for teachers (for customization)

#### Browser Considerations:
- Works best in Chrome or Edge
- Enable JavaScript
- Allow local file access if needed
- Whitelist domain if using content filter

---

### Option 3: USB Drive Distribution

Perfect for offline use or schools with limited network access:

1. **Copy entire folder structure to USB drive**
2. **Include instructions:**
   ```
   1. Copy folder to C:\Temp\ (or desktop)
   2. Open index.html in browser
   3. All activities work offline (except multiplayer quiz)
   ```

3. **Label USB clearly**
   - "Engine Lubrication Program"
   - "Open index.html in browser"

---

## 🔧 Customization Guide

### Changing Colors

All HTML files use consistent color scheme. To change:

**In each HTML file, find:**
```css
:root {
    --primary: #FF6B35;    /* Orange - change here */
    --secondary: #1A2332;  /* Dark blue - change here */
    --accent: #F39C12;     /* Gold - change here */
    --success: #2ECC71;    /* Green - change here */
}
```

### Modifying Questions

**Quiz files contain questions as JavaScript arrays:**

```javascript
const quizQuestions = [
    {
        question: "Your question here?",
        answers: ["Option 1", "Option 2", "Option 3", "Option 4"],
        correct: 1  // Index of correct answer (0-3)
    },
    // Add more questions...
];
```

### Editing Downloadable Resources

- Open `.docx` in Microsoft Word
- Open `.pptx` in PowerPoint
- Make changes
- Save
- Re-upload to GitHub or network

---

## 🔒 Security & Privacy

### Student Data:
- ✅ No student data is collected
- ✅ No cookies or tracking
- ✅ No external analytics
- ✅ Multiplayer quiz uses peer-to-peer connections only
- ✅ No server-side storage

### GDPR Compliance:
- ✅ No personal information collected
- ✅ No account creation required
- ✅ Names entered in quiz are not stored
- ✅ All data is client-side only

### Safe for Schools:
- ✅ No external content loading (except fonts and PeerJS)
- ✅ No ads or tracking
- ✅ No inappropriate content
- ✅ Works behind school firewalls (except multiplayer)

---

## 🌐 Network Requirements

### For Web Activities:
- **Bandwidth:** Minimal (mostly static HTML/CSS/JS)
- **Ports:** Standard HTTP/HTTPS (80/443)
- **Protocols:** HTTP/HTTPS only

### For Multiplayer Quiz:
- **Additional requirement:** WebRTC
- **Ports needed:** UDP ports for peer connections
- **Firewall:** May need WebRTC whitelisting
- **Alternative:** Use personal hotspot if blocked

### Offline Capabilities:
- ✅ Presentation (offline)
- ✅ Handout (offline)
- ✅ Interactive identifier (offline)
- ✅ Single-player quiz (offline)
- ❌ Multiplayer quiz (requires internet)

---

## 📱 Device Compatibility

### Tested & Working:
- ✅ Windows 10/11 (Chrome, Edge, Firefox)
- ✅ macOS (Safari, Chrome, Firefox)
- ✅ iPad/iOS 12+ (Safari, Chrome)
- ✅ Android tablets (Chrome, Firefox)
- ✅ Chromebooks (Chrome)

### Minimum Requirements:
- Screen resolution: 768px width
- JavaScript enabled
- Modern browser (2019+)
- 100MB free space for download

### Not Supported:
- ❌ Internet Explorer
- ❌ Very old mobile devices
- ❌ Text-only browsers

---

## 🐛 Common Issues & Solutions

### Issue: Files won't open
**Solution:**
- Ensure file structure is maintained
- Check file permissions
- Try different browser
- Clear cache and refresh

### Issue: Multiplayer quiz won't connect
**Solution:**
- Check internet connection
- Verify WebRTC isn't blocked
- Try different network (mobile hotspot)
- Use single-player quiz instead

### Issue: Activities look wrong
**Solution:**
- Enable JavaScript
- Update browser to latest version
- Check zoom level (should be 100%)
- Try incognito/private mode

### Issue: Can't download resources
**Solution:**
- Right-click → "Save link as"
- Check download folder permissions
- Disable pop-up blocker
- Try different browser

---

## 📊 Analytics (Optional)

If you want to track usage (optional):

### Google Analytics Setup:

1. Create Google Analytics account
2. Get tracking code
3. Add to each HTML file before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR-ID');
</script>
```

**Note:** Ensure compliance with privacy policies if tracking student use.

---

## 🔄 Updates & Maintenance

### Updating Content:

1. **Make changes locally**
2. **Test thoroughly**
3. **Update version number in README**
4. **Commit and push to GitHub:**
   ```bash
   git add .
   git commit -m "Update: description of changes"
   git push
   ```
5. **GitHub Pages auto-updates in 1-2 minutes**

### Versioning:
Use semantic versioning: `v1.0.0`
- Major: Breaking changes
- Minor: New features
- Patch: Bug fixes

---

## 📞 Support Resources

### For Technical Issues:
- GitHub Issues: Report bugs on repository
- Email: support@codeedai.com
- Documentation: README.md and TEACHER-GUIDE.md

### For Educational Support:
- Teacher guide included
- Example lesson plans
- Assessment guidance
- Differentiation strategies

---

## ✅ Pre-Launch Checklist

Before sharing with teachers/students:

- [ ] All files uploaded to GitHub
- [ ] File structure is correct
- [ ] GitHub Pages is enabled
- [ ] Site loads correctly
- [ ] All links work
- [ ] Resources download properly
- [ ] Interactive activities function
- [ ] Multiplayer quiz tested
- [ ] Mobile layout checked
- [ ] README updated with correct URL
- [ ] Teacher guide accessible
- [ ] License file included

---

## 🎉 You're Ready!

Your complete learning program is now ready to use!

**Next Steps:**
1. Share GitHub Pages URL with teachers
2. Provide teacher guide
3. Test with small group first
4. Gather feedback
5. Iterate and improve

**Your URL will be:**
```
https://yourusername.github.io/engine-lubrication-program/
```

---

## 📝 Quick Reference Commands

```bash
# Clone repository
git clone https://github.com/yourusername/engine-lubrication-program.git

# Check status
git status

# Add changes
git add .

# Commit changes
git commit -m "Description of changes"

# Push to GitHub
git push origin main

# Pull latest changes
git pull origin main
```

---

**Need help? Open an issue on GitHub or contact support@codeedai.com** 🚀
