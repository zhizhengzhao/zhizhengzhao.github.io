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
📚 **Academic Focus** - Dedicated sections for Education, Publications, Blog, and Research
🎨 **Interactive Elements** - Smooth animations and transitions
📱 **Mobile-First Approach** - Touch-friendly interface

**Latest Update**: November 10, 2025 - Complete structural reorganization with 4-section layout (Education, Publications, Blog, Research).

---

## Directory Structure

```
homepage/
├── index.html                     # Main homepage
├── desktop.css                    # Desktop styles (modern design system)
├── mobile.css                     # Mobile responsive styles
├── README.md                      # This file
│
├── assets/                        # Project assets (used in website)
│   ├── images/
│   │   ├── profile/               # Profile photos
│   │   ├── logos/                 # Institution logos
│   │   ├── research/              # Research images
│   │   └── social/                # Social media assets
│   ├── documents/                 # PDF documents (CV, transcripts, blog)
│   └── favicon/                   # Website favicons
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

## Homepage Sections

### Main Navigation Structure

The homepage is organized into 5 main sections:

1. **About** (#Top) - Personal introduction and contact information
2. **Education** (#Education) - University background and visiting experiences
3. **Publications** (#Publications) - Academic papers and research work
4. **Blog** (#Blog) - Blog and notes links (PDF-based)
5. **Research** (#Research) - Current research areas and interests

### About Section
- Profile photo and basic introduction
- Contact links (Email, CV, Transcript, WeChat)

### Education Section
- **Bachelor's Degree**: Peking University (2022-Present)
- **Visiting**: Shenzhen International Quantum Academy
  - Subsection showing visiting experiences

### Publications Section
- Research papers and work
- Includes:
  - CVPR 2025: Chain-of-Thought in Image Generation (PARM)
  - In Preparation: Dark Matter Detection with Muons (PKμ)
- Each paper includes authors, abstract, and links

### Blog Section
- Links to blog/notes PDF file
- Customize by updating the link in `index.html` line 229:
```html
<a href="assets/documents/cv.pdf" target="_blank">[My Blog & Notes]</a>
```

### Research Section
- Overview of active research areas
- Covers:
  - Chain-of-Thought in Image Generation
  - Dark Matter Detection
  - Large Model Reasoning
- References Publications section for detailed papers

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

2. **Edit Content**
   - Update personal information in `index.html`
   - Replace profile image at `assets/images/profile/zzz.png`
   - Update logos in `assets/images/logos/`
   - Edit research images in `assets/images/research/`

3. **Update Publications**
   - Edit paper links and details in the Publications section
   - Add new papers by copying the paper-container structure
   - Update author names and abstracts as needed

4. **Configure Blog Section**
   - Update the PDF link in Blog section (line 229):
     ```html
     <a href="assets/documents/YOUR-BLOG-FILE.pdf" target="_blank">[My Blog & Notes]</a>
     ```
   - Store your blog PDF in `assets/documents/`

5. **Customize Styling**
   - Edit CSS variables in `:root` blocks
   - Modify values in `desktop.css` and `mobile.css`
   - Changes apply site-wide

### Tips

1. **Content Updates**: Edit HTML directly in `index.html`
2. **Image Optimization**: Use optimized images for faster loading
3. **SEO**: Fill in meta descriptions and tags
4. **Responsive Testing**: Test on multiple device sizes
5. **Performance**: Keep animations smooth with CSS transforms
6. **PDF Organization**: Keep blog PDFs in `assets/documents/` directory

---

## Project Statistics

- **Core Files**: 3 (index.html, desktop.css, mobile.css)
- **Total Lines of Code**: 1000+ (HTML + CSS)
- **Asset Categories**: 4 organized directories
- **CSS Variables**: 15+ design system variables
- **Mobile Breakpoints**: Optimized for 4+ screen sizes
- **Pages**: Single-page homepage with smooth navigation

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

### Key URLs & Navigation
- **Homepage**: `/index.html`
- **About Section**: `index.html#Top`
- **Education Section**: `index.html#Education`
- **Publications Section**: `index.html#Publications`
- **Blog Section**: `index.html#Blog`
- **Research Section**: `index.html#Research`

### Editing Quick Tips

**Edit Section Content**
- All content in `index.html` between section `<section id="...">` tags

**Update Paper Links**
- Find paper in Publications section
- Update the `href` in the link tag

**Change Blog PDF Link**
- Find Blog section (around line 229)
- Update: `<a href="assets/documents/FILE.pdf">`

### CSS Variable Usage
```css
/* Use in your custom styles */
color: var(--primary-color);        /* Blue #2563eb */
box-shadow: var(--shadow-lg);       /* Large shadow */
background: var(--bg-secondary);    /* Light gray #f9fafb */
```

### JavaScript Features
```javascript
// Smooth scroll navigation (auto-enabled)
// Google Analytics integration (auto-enabled)
// Responsive menu for mobile/desktop (auto-enabled)
```

---

## Support & Resources

**Documentation Files:**
- `README.md` - This file (English comprehensive guide)

**Core Source Files:**
- `index.html` - Homepage with all sections
- `desktop.css` - Desktop styling (1920px+)
- `mobile.css` - Mobile responsive styling (≤600px)

**Asset Directories:**
- `assets/images/` - Logos, photos, research images
- `assets/documents/` - PDFs (CV, transcripts, blog)
- `assets/favicon/` - Browser icons
- `archive/` - Backup files

---

## Project Status

✅ **Completed**
- Modern design system with CSS variables
- Responsive layout (mobile, tablet, desktop)
- 5-section homepage (About, Education, Publications, Blog, Research)
- Asset organization in `assets/` and `archive/`
- Comprehensive documentation
- Smooth navigation and animations

✨ **Latest Restructuring** (November 10, 2025)
- Reorganized navigation to 5 main sections
- Moved papers to dedicated Publications section
- Added Visiting subsection to Education
- Integrated Blog as inline section with PDF link
- Removed separate blog.html system
- Updated CSS styling for consistency

📋 **Maintained by**
- Claude Code AI
- Last Updated: November 10, 2025

🎯 **Future Enhancements**
- Additional research papers
- Blog PDF content expansion
- Dark mode toggle (optional)
- Enhanced analytics

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
**Version**: 3.0 (Structural Reorganization)
**Status**: ✨ Production Ready

Your academic homepage is now fully structured with dedicated sections for Education, Publications, Blog, and Research. Enjoy your beautiful, modern homepage! ✨
