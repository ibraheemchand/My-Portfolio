# Articles Section & Homepage Slider - Implementation Guide

## 📁 Project Structure

```
portfolio/
├── index.html                    # Home page with embedded slider section
├── articles.html                 # Articles listing page (grid view)
├── articles/                     # Article detail pages
│   ├── understanding-pointers.html
│   ├── sorting-complexity.html
│   └── [article-slug].html       # Follow this pattern
├── data/
│   └── articles.json             # Master articles data (single source of truth)
└── images/
    └── articles/                 # Article thumbnail images
        ├── pointers-thumb.jpg
        ├── sorting-thumb.jpg
        └── [article-slug].jpg
```

---

## 🚀 Quick Start

### 1. View the Articles Slider on Homepage
- The slider automatically loads the **featured articles** from `articles.json`
- It displays:
  - Article title, description, date, reading time
  - Featured image (if available)
  - Tags
  - "Read article" button

### 2. Navigate to Articles Page
- Click **"Articles"** in the navbar
- See all articles in a filterable grid
- Filter by tags (Python, C++, Linux, etc.)
- Click any card to read the full article

---

## ✍️ How to Add New Articles

### Step 1: Add Article Data to `articles.json`

```json
{
  "id": "my-article-slug",
  "slug": "my-article-slug",
  "title": "My Article Title",
  "description": "Short description (1-2 sentences)",
  "date": "2024-02-20",
  "readingTime": 12,
  "featured": true,
  "tags": ["Python", "Web Dev", "Performance"],
  "thumbnail": "/images/articles/my-article-slug.jpg",
  "sections": {
    "problem": "What problem did you solve?",
    "error": "What error or bug did you encounter?",
    "rootCause": "Why did it happen?",
    "solution": "How did you fix it?",
    "keyTakeaway": "What did you learn?"
  }
}
```

**Key Fields:**
- `featured`: Set to `true` for articles to appear in homepage slider (max 6 will show)
- `date`: Use YYYY-MM-DD format (newest articles appear first)
- `slug`: Must match your HTML filename (e.g., `sorting-complexity.html`)
- `readingTime`: Approximate reading time in minutes
- `tags`: For filtering on articles.html

### Step 2: Create Article HTML File

**Create file:** `articles/[slug].html`

The easiest way: Copy `articles/understanding-pointers.html` and modify:

1. **Update `<title>` and `<meta description>`**
   ```html
   <title>My Article Title - Ibraheem Chand</title>
   <meta name="description" content="My article description">
   ```

2. **Update article header:**
   ```html
   <h1 class="article-title">My Article Title</h1>
   <div class="article-date"><span>Feb 20, 2024</span></div>
   <div class="reading-time"><span>12 min read</span></div>
   
   <div class="article-tags-row">
     <span class="article-tag">Python</span>
     <span class="article-tag">Web Dev</span>
   </div>
   ```

3. **Update content sections:**
   ```html
   <div class="article-section">
     <h2><span class="emoji">🧠</span> Problem</h2>
     <p>Your problem description...</p>
   </div>
   
   <div class="article-section">
     <h2><span class="emoji">⚠️</span> Error / Bug</h2>
     <p>Your error...</p>
     <div class="code-block">
       <pre><code>error output here</code></pre>
     </div>
   </div>
   
   <!-- Repeat for: 🔍 Root Cause, 🛠️ Solution, 💡 Key Takeaway -->
   ```

4. **Update related articles links** at the bottom
5. **Save and it's live!** No backend needed.

### Step 3: Add Thumbnail Image

1. Save your article thumbnail to `images/articles/[slug].jpg`
2. Size: ~600x400px recommended
3. Update `articles.json` with `"thumbnail": "/images/articles/[slug].jpg"`

---

## 🎨 Content Components Available

### Code Blocks
```html
<div class="code-block">
  <pre><code class="language-python">
# Your code here
print("Hello")
  </code></pre>
</div>
```

### Images
```html
<img src="/path/to/image.jpg" alt="Description" class="article-image">
<p class="image-caption">Image caption</p>
```

### Callout Boxes
```html
<div class="callout">
  <p><strong>Important:</strong> Key insight here</p>
</div>

<!-- Or warning style: -->
<div class="callout warning">
  <p>⚠️ Watch out for...</p>
</div>
```

### Lists
```html
<ul>
  <li>Point 1</li>
  <li>Point 2</li>
  <li>Point 3</li>
</ul>
```

### Headings
```html
<h3>Subheading</h3>
<p>Content...</p>
```

---

## 🎠 Homepage Slider Configuration

The slider in `index.html` automatically:
- ✅ Fetches articles from `data/articles.json`
- ✅ Filters for `featured: true` articles
- ✅ Shows up to 6 cards
- ✅ Supports left/right arrow navigation
- ✅ Supports touch swipe on mobile
- ✅ Has dot indicators for current position
- ✅ Links to individual article pages

**To control slider:**

Edit the filter in `index.html` JavaScript:
```javascript
articlesData = data.filter(article => article.featured).slice(0, 6);
//                              ↑ Set featured: true in JSON
//                                                      ↑ Max 6 articles
```

---

## 📋 Best Practices

### Article Structure
1. **Problem** - What were you trying to do?
2. **Error/Bug** - What went wrong? Include error messages
3. **Root Cause** - Why did it fail? Include reasoning
4. **Solution** - How did you fix it? Show code
5. **Key Takeaway** - What did you learn? Make it transferable

### Content Tips
- **Keep it real:** Show actual errors, real code, real debugging
- **Add visuals:** Screenshots of errors, diagrams, code output
- **Be specific:** "Segmentation fault when accessing deleted memory" > "Pointer problem"
- **Optimize for learning:** Someone should gain a skill from reading it
- **Tag wisely:** Use consistent tags across articles for easy filtering

### SEO/Sharing
- Use descriptive titles (not "Learning Log #5")
- Meta descriptions auto-include in article cards
- Social share buttons are ready in article footer
- Each article has Open Graph meta tags for link previews

---

## 🔧 Customization

### Change Slider Title
In `index.html`, find:
```html
<p class="section-eyebrow reveal">Latest Articles</p>
<h2 class="section-title reveal">What I'm <em>learning</em>.</h2>
```

### Change Slider Colors
Edit CSS variables in article styles (they inherit from root):
```css
:root {
  --accent:    #5b4ef5;   /* Primary color */
  --accent2:   #2ec4b6;   /* Secondary */
  --bg:        #ffffff;
  /* ... */
}
```

### Auto-scroll Articles
Add to slider initialization (in `index.html` script):
```javascript
// Auto-scroll every 5 seconds
setInterval(() => slideRight(), 5000);
```

### Show Only Featured Articles in Grid
In `articles.html`, change:
```javascript
renderArticles(allArticles);
// to:
renderArticles(allArticles.filter(a => a.featured));
```

---

## 📊 Data Flow

```
articles.json (single source)
    ↓
    ├─→ index.html (slider loads via fetch)
    │
    └─→ articles.html (grid loads + filters)

articles/[slug].html (manually created HTML)
    └─→ User reads full article
```

**Important:** Update `articles.json` first, then create HTML file.

---

## 🐛 Troubleshooting

### Slider not showing on homepage
- Check browser console for errors
- Verify `data/articles.json` exists
- Ensure at least 1 article has `"featured": true`
- Check that JSON syntax is valid (use jsonlint.com)

### Article doesn't appear in grid
- Verify `slug` in JSON matches filename (without `.html`)
- Check article date format: `YYYY-MM-DD`
- Browser cache: Hard refresh (Ctrl+Shift+R)

### Images not loading
- Check image path is correct (case-sensitive on Linux)
- Verify file exists in `images/articles/`
- Try absolute path: `/images/articles/my-image.jpg`

### Slider navigation not working
- Check JavaScript console for errors
- Ensure article cards have `data-index` attribute
- Verify dots are being created

---

## 📈 Next Steps (Optional Enhancements)

1. **Add Search:** Add search input to `articles.html` to filter by title/content
2. **Comments:** Add Disqus or similar to article pages
3. **Analytics:** Track which articles are most read
4. **Newsletter signup:** Add CTA to subscribe
5. **Categories:** Expand from tags to article categories
6. **Archive:** Show articles by year on `articles.html`
7. **Social buttons:** Make share buttons actually work
8. **Reading progress:** Add progress bar to top of article
9. **Table of Contents:** Auto-generate from H2/H3 headings
10. **Syntax highlighting:** Add Prism.js for better code highlighting

---

## 🎯 Key Takeaway

**Your portfolio + articles = proof of work.**

Instead of just listing projects, you're now showing:
- How you think
- How you debug
- How you learn
- Real problems + real solutions

This positions you as someone who **solves problems systematically**, not just writes code.

---

**Happy writing! 🚀**

For questions or to add features, check the code comments in:
- `index.html` (slider JS section)
- `articles.html` (filter logic)
- Individual article templates
