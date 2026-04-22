# ✅ Articles System - Test Checklist

## Before You Start Testing

1. Open your portfolio's main folder
2. Launch `index.html` in your browser
3. Open Developer Tools (F12) to watch for errors

---

## 🏠 Homepage Tests

### Navbar
- [ ] "Articles" link appears in navbar
- [ ] "Articles" is visible on mobile (in hamburger menu)
- [ ] Clicking "Articles" goes to `articles.html`

### Articles Slider Section
- [ ] "Latest Articles" heading visible below "Currently Learning"
- [ ] "What I'm learning." subtitle visible
- [ ] At least 3 article cards display

### Article Cards (in slider)
- [ ] Each card shows:
  - [ ] Thumbnail image (or placeholder)
  - [ ] Article title
  - [ ] Article date
  - [ ] Description
  - [ ] Reading time
  - [ ] Tags
  - [ ] "Read article →" link
- [ ] Cards have hover effect (slight lift/shadow)

### Slider Navigation
- [ ] Left arrow button works, scrolls previous
- [ ] Right arrow button works, scrolls next
- [ ] Dot indicators show active position
- [ ] Clicking dots jumps to that article
- [ ] Looping works (left arrow at start goes to end)

### Mobile Testing (Slider)
- [ ] Swipe left on mobile slides right
- [ ] Swipe right on mobile slides left
- [ ] Cards stack vertically on small screens
- [ ] Touch doesn't break navigation

### "View All Articles" Button
- [ ] Button appears below slider
- [ ] Clicking goes to `articles.html`

---

## 📖 Articles Listing Page Tests

### Page Load
- [ ] Page loads without errors
- [ ] Layout renders correctly
- [ ] All articles display in grid

### Grid Layout
- [ ] Desktop: 3 columns
- [ ] Tablet (768px): 2 columns  
- [ ] Mobile (640px): 1 column

### Article Cards Display
Each article shows:
- [ ] Thumbnail image (or placeholder)
- [ ] Date
- [ ] Title
- [ ] Description
- [ ] Reading time
- [ ] Tags

### Tag Filtering
- [ ] "All" button shows all articles
- [ ] Clicking tag shows only articles with that tag
- [ ] Active tag is highlighted
- [ ] Article count updates
- [ ] Multiple tags appear as filter options

### Navigation
- [ ] Back link goes to home
- [ ] Hamburger menu works
- [ ] Mobile nav opens/closes

---

## 📄 Article Detail Page Tests

### Article 1: Understanding C++ Pointers

**URL:** `/articles/understanding-pointers.html`

Header:
- [ ] Title displays: "Understanding C++ Pointers..."
- [ ] Date shows: "Feb 15, 2024"
- [ ] Reading time: "8 min read"
- [ ] Tags visible: C++, Memory Management, Pointers

Sections:
- [ ] 🧠 Problem section exists with content
- [ ] ⚠️ Error section with code block
- [ ] 🔍 Root Cause section with explanation
- [ ] 🛠️ Solution section with code examples
- [ ] 💡 Key Takeaway section with callout box

Footer:
- [ ] "Back to articles" link works
- [ ] Related articles show
- [ ] Footer displays

### Article 2: Sorting Algorithm Complexity

**URL:** `/articles/sorting-complexity.html`

- [ ] Same structure as article 1
- [ ] Title correct: "Sorting Algorithm Complexity..."
- [ ] Date: "Feb 10, 2024"
- [ ] Reading time: "10 min read"
- [ ] All sections present and readable

### Links Between Pages
- [ ] Article → "Back to articles" → articles.html ✓
- [ ] Article → related article → another article ✓
- [ ] Article → navbar home → index.html ✓
- [ ] articles.html → article card → article page ✓

---

## 📱 Responsive Testing

### Desktop (1200px+)
- [ ] Slider: 3 -4 columns visible
- [ ] Articles grid: 3 columns
- [ ] Navbar: links visible
- [ ] No horizontal scrolling

### Tablet (768px - 900px)
- [ ] Slider: 2 columns visible
- [ ] Articles grid: 2 columns
- [ ] Hamburger menu visible
- [ ] Touch interactions work

### Mobile (320px - 640px)
- [ ] Slider: 1 column (full width)
- [ ] Articles: 1 column (full width)
- [ ] Text readable (no zoom needed)
- [ ] Buttons clickable (touch-friendly size)
- [ ] Swipe works smoothly

---

## 🔧 Technical Tests

### Console (F12 → Console Tab)
- [ ] No JavaScript errors
- [ ] Articles data loads (check Network tab)
- [ ] Network: `data/articles.json` Status 200

### Performance
- [ ] Page loads in < 2 seconds
- [ ] Slider scrolls smoothly
- [ ] No lag when clicking filters
- [ ] Mobile interactions responsive

### Browser Compatibility
- [ ] Chrome: ✓
- [ ] Firefox: ✓
- [ ] Safari: ✓
- [ ] Edge: ✓

---

## 📊 Data Integration Tests

### data/articles.json
- [ ] File exists at `data/articles.json`
- [ ] File is valid JSON (no parsing errors)
- [ ] Has at least 1 article with `"featured": true`
- [ ] Thumbnails paths point to real images (or use placeholders)

### Slider Integration
- [ ] Slider fetches only featured articles
- [ ] Shows max 6 articles
- [ ] Links in slider cards work
- [ ] Clicking article goes to correct page

### Grid Integration
- [ ] Grid shows all articles (featured or not)
- [ ] Sorting works (newest first by date)
- [ ] Tags extracted correctly
- [ ] Filter by tag works

---

## 🎨 Visual/Design Tests

### Colors & Styling
- [ ] Accent color (purple) used consistently
- [ ] Hover states visible on cards
- [ ] Active dot is purple
- [ ] Tags styled correctly
- [ ] Borders and spacing consistent

### Typography
- [ ] Headings clear (Bricolage Grotesque)
- [ ] Body text readable (Lora)
- [ ] Code blocks formatted well
- [ ] No text cutoff or overflow

### Animations
- [ ] Smooth slide transitions
- [ ] Hover effects on buttons
- [ ] Fade-in animations on reveal
- [ ] No janky movements

---

## 🐛 Error Scenarios

### What if...

**JSON file missing?**
- [ ] Slider doesn't crash
- [ ] Graceful error handling
- [ ] No console errors

**Article file missing?**
- [ ] Link in slider/grid still works (404 on click)
- [ ] Other articles still load

**Invalid date format?**
- [ ] Articles still display
- [ ] Date formatting doesn't break

**No articles with `featured: true`?**
- [ ] Slider still loads
- [ ] No articles show but no crash

---

## 🎯 User Experience Tests

### First-time User (no fresh visit)
- [ ] Homepage loads
- [ ] Discovers "Latest Articles" section
- [ ] Slider is obvious and interactive
- [ ] Can click to read articles
- [ ] Can find all articles from navbar or button

### Mobile User
- [ ] Can see articles on phone
- [ ] Swipe works intuitively
- [ ] Text is readable
- [ ] No tiny buttons

### Content Creator (adding articles)
- [ ] Can easily follow template
- [ ] JSON format makes sense
- [ ] Creating HTML from template is straightforward
- [ ] New article appears in slider/grid after editing JSON

---

## ✨ Final Verification

### Core Functionality
- [ ] Homepage slider works ✓
- [ ] Articles listing works ✓
- [ ] Individual articles load ✓
- [ ] Navigation works between pages ✓
- [ ] All links are correct ✓

### Content Quality
- [ ] Sample articles are high-quality ✓
- [ ] Structure follows Problem→Solution ✓
- [ ] Code examples include ✓
- [ ] Readable and well-formatted ✓

### Responsiveness
- [ ] Desktop experience ✓
- [ ] Tablet experience ✓
- [ ] Mobile experience ✓

### Performance
- [ ] Fast load time ✓
- [ ] Smooth interactions ✓
- [ ] No console errors ✓

---

## 📋 Sign Off

Once all tests pass, you can confidently:

✅ Share your portfolio
✅ Add more articles
✅ Showcase your debugging skills
✅ Demonstrate systematic thinking

---

## 🐛 If a Test Fails

1. Check browser console (F12) for errors
2. Check file paths (case-sensitive on Linux)
3. Verify JSON is valid (use jsonlint.com)
4. Clear browser cache (Ctrl+Shift+R hard refresh)
5. Check file exists in right location
6. See troubleshooting section in ARTICLES_README.md

---

**Good luck! Your articles system is ready to launch!** 🚀
