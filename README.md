# Zhizheng Zhao's Homepage - Complete Documentation

Welcome to the complete documentation for Zhizheng Zhao's personal homepage. This guide covers the project structure, design system, and instructions for managing content.

## Table of Contents

- [Project Overview](#project-overview)
- [Directory Structure](#directory-structure)
- [Design System](#design-system)
- [Blog System](#blog-system)
- [Getting Started](#getting-started)
- [FAQ](#faq)

---

## Project Overview

This is a modern, professional personal homepage featuring:

✨ **Modern Design System** - Unified color scheme and component design
🎯 **Responsive Layout** - Optimized for desktop, tablet, and mobile devices
📝 **Blog System** - Easy-to-manage blog platform with article management
🎨 **Interactive Elements** - Smooth animations and transitions
📱 **Mobile-First Approach** - Touch-friendly interface

**Latest Update**: November 10, 2025 - Complete design system overhaul with modern aesthetics.

---

## Directory Structure

```
homepage/
├── index.html                     # Main homepage
├── blog.html                      # Blog listing page
├── desktop.css                    # Desktop styles (modern design system)
├── mobile.css                     # Mobile responsive styles
├── README.md                      # This file
├── BLOG_GUIDE.md                  # Blog system user guide (Chinese)
├── DESIGN_UPGRADE.md              # Design upgrade report (Chinese)
│
├── blog/                          # Blog articles directory
│   ├── 001-欢迎来到我的博客.html          # Welcome article
│   ├── 002-链式思维研究.html              # CoT research article
│   └── 003-暗物质探测.html                # Dark matter detection article
│
├── assets/                        # Project assets (used in website)
│   ├── images/
│   │   ├── profile/               # Profile photos
│   │   ├── logos/                 # Institution logos
│   │   ├── research/              # Research images
│   │   └── social/                # Social media assets
│   ├── documents/                 # PDF documents (CV, transcripts)
│   ├── favicon/                   # Website favicons
│   └── blog-assets/               # Blog-specific assets
│       ├── thumbnails/            # Article thumbnails (optional)
│       └── styles/                # Blog custom styles (optional)
│
└── archive/                       # Archived/unused files
    ├── unused-images/             # Old image versions
    └── email-materials/           # Email attachments & applications
```

---

## Design System

### Color Palette

A modern, professional color scheme combining blue and gold accents:

| Purpose | Color | Usage |
|---------|-------|-------|
| Primary | #2563eb | Main interactive elements |
| Dark | #1e40af | Hover states |
| Light | #3b82f6 | Borders and emphasis |
| Accent | #f59e0b | Highlights and decorations |
| Text | #1f2937 | Primary text |
| Secondary Text | #6b7280 | Secondary text |
| Background | #ffffff | Primary background |
| Light BG | #f9fafb | Secondary background |

### CSS Variables

All colors and spacing are defined as CSS variables in the `:root` block:

```css
:root {
  --primary-color: #2563eb;
  --primary-dark: #1e40af;
  --primary-light: #3b82f6;
  --accent-color: #f59e0b;
  --text-primary: #1f2937;
  --text-secondary: #6b7280;
  --shadow-lg: 0 10px 20px rgba(0, 0, 0, 0.15);
  /* ... more variables */
}
```

### Design Features

**Navigation Bar**
- Glass Morphism effect with blur backdrop
- Smooth hover animations with underline effect
- Fixed positioning for easy navigation

**Cards & Components**
- Consistent border-radius (12px)
- Unified shadow system
- Gradient top border on hover (scales from 0 to 100%)
- Smooth elevation effect on hover

**Profile Section**
- Large, prominent profile image (160x160px)
- Blue border around image
- Rotation effect on hover
- Modern button styling with background colors

**Responsive Design**
- Mobile-first approach
- Optimized for 375px - 1920px+ screens
- Touch-friendly interface
- Flexible layouts using Flexbox

### Typography

- **Font Family**: Lato (imported from Google Fonts)
- **Headings**: Font weight 700, increased letter spacing
- **Body Text**: Font weight 400, optimized line height (1.6-1.9)
- **Code**: Courier New with syntax highlighting

---

## Blog System

### Quick Start

**Access the Blog**
- Blog listing: Visit `blog.html`
- Individual articles: Click blog cards
- From homepage: Click "📝 Blog" in navigation

### Adding New Articles

#### Method 1: Copy Existing Template

1. Copy `blog/001-欢迎来到我的博客.html`
2. Rename to `blog/XXX-your-title.html`
3. Edit content
4. Add entry to `blogPosts` array in `blog.html`

#### Method 2: Use Article Template

```html
<!DOCTYPE HTML>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Your Article Title - Zhizheng Zhao</title>
  <link rel="shortcut icon" href="../assets/favicon/android-chrome-512x512.png">
  <link rel="stylesheet" href="../desktop.css" media="screen and (min-width: 601px)">
  <link rel="stylesheet" href="../mobile.css" media="screen and (max-width: 600px)">

  <style>
    /* Include article styles from existing articles */
    :root { /* Design system variables */ }
    .article-container { /* ... */ }
    /* ... more styles ... */
  </style>
</head>
<body>
  <div class="article-container">
    <div class="article-header">
      <h1 class="article-title">Your Title</h1>
      <div class="article-meta">
        <span>📅 2025-11-15</span>
        <span>✍️ Zhizheng Zhao</span>
        <span>🏷️ Category</span>
      </div>
      <div class="tags">
        <span class="tag">tag1</span>
        <span class="tag">tag2</span>
      </div>
    </div>

    <div class="article-content">
      <h2>Section Title</h2>
      <p>Your content here...</p>
    </div>

    <div class="article-footer">
      <a href="../blog.html" class="back-link">← Back to Blog</a>
    </div>
  </div>
</body>
</html>
```

### Managing Blog Posts

Edit the `blogPosts` array in `blog.html`:

```javascript
const blogPosts = [
  {
    id: 1,                          // Unique ID (increment)
    title: "Article Title",
    date: "2025-11-15",             // YYYY-MM-DD format
    category: "Technology",         // Category name
    excerpt: "Brief summary...",
    tags: ["tag1", "tag2"],         // 3-5 tags per article
    url: "blog/001-your-title.html" // File path
  },
  // ... more articles
];
```

### Article Categories

Recommended categories:
- **Technology** - Deep learning, AI, programming
- **Physics** - Dark matter, particle physics
- **Research** - Research progress, paper sharing
- **Personal** - Learning insights, life reflections
- **Notes** - Study notes, tutorials

### Content Formatting

**Headings**
```html
<h2>Section Title (Main sections)</h2>
<h3>Subsection Title</h3>
```

**Text Elements**
```html
<p>Regular paragraph</p>
<ul><li>Unordered list</li></ul>
<ol><li>Ordered list</li></ol>
<blockquote>Quotation</blockquote>
<code>Inline code</code>
<pre><code>Code block</code></pre>
```

### FAQ - Blog Management

**Q: How do I delete an article?**
- Delete the corresponding `.html` file
- Remove entry from `blogPosts` array in `blog.html`

**Q: How do I change article order?**
- Reorder elements in the `blogPosts` array
- New articles typically go at the beginning

**Q: How do I modify blog styles?**
- Edit `<style>` section in `blog.html`
- Or edit styles in individual article HTML files

**Q: Can I add comments?**
- Currently a static site
- Integrate third-party services like Disqus or Utterances for comments

**Q: How do I add article thumbnails?**
- Save images to `assets/blog-assets/thumbnails/`
- Add `thumbnail` field to `blogPosts` entry
- Modify blog card HTML to display thumbnail

---

## Design Improvements

### Modern Design System Implementation

**Complete Redesign Features:**

✅ Unified color scheme and typography
✅ Modern shadow system for depth
✅ Smooth animations and transitions
✅ Glass Morphism effects on navigation
✅ Gradient accents on hover
✅ Responsive card elevations

### Desktop Layout Enhancements

- Navigation with blur backdrop and smooth animations
- Profile card with gradient background
- Card components with gradient top border
- Improved logo treatment with grayscale-to-color transition
- Modern button styling with hover effects

### Mobile Optimization

- Responsive card layouts (vertical stacking)
- Touch-friendly interface
- Optimized navigation for small screens
- Flexible spacing for mobile constraints
- Performance-optimized animations

### Color Scheme Highlights

**Before vs After:**

| Element | Before | After |
|---------|--------|-------|
| Navigation | Plain white, basic hover | Glass effect, smooth animations |
| Cards | Simple left border | Full border, gradient bar, elevation |
| Links | Text only | Button style, background, hover effect |
| Tags | Plain background | Border design, color transitions |

---

## Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Text editor for content editing
- Basic HTML knowledge for customization

### Setup Steps

1. **View the Homepage**
   - Open `index.html` in your browser
   - Test responsive design with browser DevTools

2. **Add Content**
   - Edit personal information in `index.html`
   - Replace profile image at `assets/images/profile/zzz.png`
   - Update logos in `assets/images/logos/`

3. **Start Blogging**
   - Copy article template from `blog/001-*`
   - Create new article files
   - Add entries to `blogPosts` array

4. **Customize Styling**
   - Edit CSS variables in `:root` blocks
   - Modify values in `desktop.css` and `mobile.css`
   - Changes apply site-wide

### Tips

1. **Date Format**: Always use `YYYY-MM-DD` for correct sorting
2. **Image Optimization**: Use optimized images for faster loading
3. **SEO**: Fill in meta descriptions and tags
4. **Responsive Testing**: Test on multiple device sizes
5. **Performance**: Keep animations smooth with CSS transforms

---

## Project Statistics

- **Total Files**: 20+ HTML/CSS files
- **Articles**: 3 sample articles (expandable)
- **Asset Categories**: 6 organized directories
- **CSS Variables**: 15+ design system variables
- **Mobile Breakpoints**: Optimized for 4+ screen sizes

---

## Asset Organization

**Golden Rule**:
- Use `assets/` for website resources (images, documents, etc.)
- Use `archive/` for unused/backup files
- Always reference `assets/` paths in HTML

**Resource Types:**

| Directory | Purpose | Size |
|-----------|---------|------|
| `assets/images/` | Website images | ~500KB |
| `assets/documents/` | PDFs (CV, etc.) | ~1MB |
| `assets/favicon/` | Browser icons | ~100KB |
| `archive/` | Backups (unused) | ~50MB |

---

## Responsive Design

Optimized breakpoints:
- **Desktop**: 1920px+ (full layout)
- **Laptop**: 1024px - 1920px (optimized columns)
- **Tablet**: 768px - 1024px (adjusted spacing)
- **Mobile**: 375px - 768px (stacked layout)

---

## Performance Considerations

**Optimizations Implemented:**

✅ CSS variables for efficient styling
✅ GPU-accelerated animations (transform, opacity)
✅ Minimal reflow/repaint triggers
✅ Responsive images and scaling
✅ Optimized font loading (Lato via Google Fonts)

**Best Practices:**

- Keep images under 500KB
- Minimize nested selectors in CSS
- Use CSS transforms for animations
- Lazy load images for blogs (optional)

---

## Browser Compatibility

**Supported Browsers:**
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

**Features Used:**
- CSS Grid & Flexbox
- CSS Variables (custom properties)
- CSS Animations & Transitions
- Modern JavaScript (ES6+)

---

## Future Enhancements

**Optional Features to Add:**

1. **Dark Mode**
   - Toggle theme button
   - localStorage persistence
   - Automatic schedule based on time

2. **Search Functionality**
   - Blog search by title/tags
   - Filter by category

3. **Analytics**
   - Google Analytics (already included)
   - Page visit tracking
   - Article engagement metrics

4. **Social Features**
   - Share buttons
   - Social media links
   - Comment system (Disqus/Utterances)

5. **Advanced Content**
   - Gallery lightbox
   - Video embeds
   - Interactive demos

---

## File Management

### When Adding New Resources

✅ **Use `assets/` for:**
- Profile images
- Research images
- Documents (PDFs)
- Logo files
- Favicons

❌ **Don't reference `archive/` in HTML:**
- Archive is backup only
- Always use `assets/` paths

### File Naming Conventions

- Images: `lowercase-with-dashes.png`
- Articles: `001-article-title.html`
- CSS: `lowercase.css`
- Dates: `YYYY-MM-DD` format

---

## Troubleshooting

**Issue: Images not showing**
- Check file paths use `assets/` directory
- Verify file extensions (.png, .jpg, etc.)
- Ensure relative paths are correct

**Issue: Styles not applying**
- Clear browser cache (Ctrl+Shift+Delete)
- Check CSS variables are defined in `:root`
- Verify CSS file is linked in `<head>`

**Issue: Blog post not appearing**
- Add entry to `blogPosts` array in `blog.html`
- Verify file path matches actual file location
- Check date format is `YYYY-MM-DD`

**Issue: Mobile layout broken**
- Test with browser DevTools (F12)
- Check viewport meta tag is present
- Verify media query breakpoints

---

## Quick Reference

### Key URLs
- Homepage: `/index.html`
- Blog List: `/blog.html`
- Blog Article: `/blog/XXX-title.html`

### CSS Variable Usage
```css
/* Use in your custom styles */
color: var(--primary-color);
box-shadow: var(--shadow-lg);
background: var(--bg-secondary);
```

### JavaScript Hooks
```javascript
// Smooth scroll on navigation links
// Auto-loads blog posts from array
// Google Analytics auto-integrated
```

---

## Support & Resources

**Documentation Files:**
- `README.md` - This file (English overview)
- `BLOG_GUIDE.md` - Blog system detailed guide (Chinese)
- `DESIGN_UPGRADE.md` - Design system documentation (Chinese)

**Related Files:**
- `desktop.css` - Desktop styling with design system
- `mobile.css` - Mobile responsive styling
- `index.html` - Homepage source code
- `blog.html` - Blog listing source code

---

## Project Status

✅ **Completed**
- Modern design system
- Responsive layout (mobile, tablet, desktop)
- Blog system with 3 sample articles
- Asset organization
- Design documentation

📋 **Maintained by**
- Claude Code AI
- Last Updated: November 10, 2025

🎯 **Future Vision**
- Enhanced content management
- Advanced analytics
- Community features
- Extended functionality

---

## License & Attribution

This homepage was created for **Zhizheng Zhao**, an undergraduate student at Peking University's School of Physics, focused on Physics and Artificial Intelligence.

**Design Credits:**
- Modern design system implementation: Claude Code
- Responsive layout: CSS Flexbox & Media Queries
- Fonts: Lato (Google Fonts)
- Icons: Unicode Emoji

---

## Contact Information

📧 **Email**: zhizhengzhao@outlook.com
💬 **WeChat**: Available on homepage
🔗 **Links**: CV, Transcript, Research details on main page

---

**Last Updated**: November 10, 2025
**Version**: 2.0 (Design System Overhaul)
**Status**: ✨ Production Ready

Enjoy your beautiful, modern homepage! ✨
