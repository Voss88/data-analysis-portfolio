# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **static portfolio website** showcasing data analysis and data science projects. The site is hosted on GitHub Pages and uses pure HTML/CSS/JavaScript without any build process or backend. The portfolio demonstrates skills in SQL, BigQuery, Python, R, data visualization, and machine learning.

**Live Site**: https://voss88.github.io/data-analysis-portfolio/
**Domain**: www.thomasvoss.co.uk (via CNAME)

## Repository Structure

```
.
├── main-pages/           # Core website pages
│   ├── index.html       # Homepage with project carousel and about section
│   ├── projects.html    # Projects listing page
│   └── cv.html          # CV/Resume page
├── project-live/        # Individual project article pages
│   ├── project-define-health-metrics.html
│   ├── project-football-transfer-analysis.html
│   └── project-health-metric-gui.html
├── project-templates/   # Template for creating new project pages
│   └── project_article_template.html
├── main-page-image/     # Images for main pages (logos, hero images)
├── project-image/       # Images for project articles
├── icons/               # Icon assets
└── .github/             # GitHub Pages configuration
```

## Design System

The site uses a consistent Apple-inspired design language across all pages:

### Color Scheme
- **Primary Color**: `#0F5741` (dark green)
- **Secondary Color**: `#F5F5F7` (light gray background)
- **Text Color**: `#333333` (dark gray)
- **Nav Background**: `#f1f1f1`
- **Gradient Accent**: Red-to-yellow gradient used for borders and hover effects
  ```
  rgba(253, 9, 6, 1) → rgba(255, 220, 0, 1)
  ```

### Typography
- **Font Family**: San Francisco (`-apple-system, BlinkMacSystemFont, "San Francisco", "Helvetica Neue", sans-serif`)
- **Code Font**: `'SFMono-Regular', 'Menlo', 'Monaco', 'Consolas', 'Liberation Mono', 'Courier New', monospace`

### UI Components
- **Cards**: White background, 16px border-radius, subtle box-shadow
- **Hover Effects**: Gradient borders appear on hover using pseudo-elements
- **Navigation**: Fixed navbar (15vh height) with gradient bottom border
- **Code Blocks**: Dark theme (#1E1E1E background) with syntax highlighting via highlight.js

## Adding New Projects

### 1. Create Project Page
Use `project-templates/project_article_template.html` as the starting point:
- Copy template to `project-live/project-[name].html`
- Update page title, hero image, and content sections
- Follow the existing structure: TL;DR → Prerequisites → Steps with alternating text/code/photo sections

### 2. Add to Homepage Carousel
Edit `main-pages/index.html` and add a new carousel card:
```html
<a href="project-[name].html" class="carousel-card-link">
    <div class="carousel-card">
        <div class="carousel-card-background" style="background-image: url('project-image/[image].jpg'); background-size: cover;"></div>
        <div class="carousel-card-content">
            <h3>[Project Title]</h3>
            <p>[Project Description]</p>
        </div>
    </div>
</a>
```

### 3. Update Projects Page
Add project listing to `main-pages/projects.html` if it exists.

## Page Structure Patterns

### Navigation Bar (Consistent Across All Pages)
- Fixed position at top (15vh height on desktop, responsive on mobile)
- Three elements: "Projects" link, Logo (center), "View CV" link
- Desktop logo vs mobile logo (different aspect ratios)
- Links use icons from Font Awesome 6.4.0

### Project Article Pages
1. **Hero Section**: Full-width image with overlaid title card
2. **TL;DR Section**: Project overview and objectives
3. **Prerequisites & Packages**: Visual badges showing R/Python/other tools
4. **Step-by-step Content**: Alternating between:
   - `.text-section` - Explanatory text
   - `.code-section` - Code blocks with syntax highlighting
   - `.photo-section` - Images with captions

### Homepage (`index.html`)
1. **Navigation Bar**
2. **Card Carousel**: Horizontal scrolling showcase of projects
3. **About Section**: Three-card layout introducing the portfolio owner
4. **Photo Section**: Hero image

## Responsive Design

The site has four breakpoints:
- **Desktop (1200px+)**: Full layout, large logos
- **Laptop (992px-1199px)**: Slightly smaller elements
- **iPad (768px-991px)**: Adjusted spacing, 15vh navbar
- **Mobile (≤767px)**: Icon-only navigation, mobile logo, stacked layout
- **Small Mobile (≤480px)**: Further compressed spacing

### Key Mobile Adaptations
- Navigation text hidden, icons only (`.nav-text { display: none }`)
- Logo switches from desktop to mobile version
- Carousel cards resize (90-100% width on mobile vs 45-80% on desktop)
- Reduced padding on all sections
- Smaller hero images (35-40vh on mobile vs 60vh on desktop)

## External Dependencies

All dependencies are loaded via CDN (no npm/build process):
- **Bootstrap 5.3.0**: CSS framework
- **Font Awesome 6.4.0**: Icons
- **Highlight.js 11.7.0**: Code syntax highlighting (atom-one-dark theme)
- **Google Analytics**: Tracking ID `G-WSS3DYFH3Z`

## File Naming Conventions

- Main pages: `kebab-case.html` in `main-pages/`
- Project pages: `project-[name].html` in `project-live/`
- Images: `project-image-[description].jpg` or `fig-[n]-[description].png`
- Logo files: `logo.png` (desktop), `mobile-logo.png` (mobile)

## Git Workflow

- **Main branch**: `main` (use for PRs and as base branch)
- **Current branch**: `datacamp-update`
- Recent work includes restructuring directories and adding new health metrics projects

## Navigation Paths

All navigation links use **relative paths** from the root level (since files may be in different directories):
- From project pages to main pages: `../main-pages/index.html`
- To images: `../project-image/[name]` or `../main-page-image/[name]`
- Logo images referenced directly: `logo.png` (adjust path based on current file location)

**Important**: When creating new pages, verify image and link paths based on the file's directory location.

## Code Highlighting

For code blocks, wrap code in:
```html
<div class="code-section">
    <pre><code class="python">
# Your code here
    </code></pre>
</div>
```

Supported languages (via highlight.js): `python`, `r`, `sql`, `javascript`

## Package Buttons

Display technology stack using package buttons:
```html
<div class="package-buttons">
    <div class="package-button">
        <i class="fab fa-r-project fa-lg me-2" style="color: #276DC3;"></i>
        R
    </div>
    <div class="package-button">
        <i class="fa-brands fa-python fa-lg me-2" style="color: #276DC3;"></i>
        Python
    </div>
</div>
```

## Testing & Deployment

Since this is a static site on GitHub Pages:
1. No build/test commands required
2. Changes pushed to `main` branch automatically deploy
3. Test locally by opening HTML files in a browser
4. Check responsive design at different viewport sizes
5. Verify all relative paths work correctly

## Common Tasks

### Preview locally
```bash
# Open any HTML file directly in browser
open main-pages/index.html
# or
python -m http.server 8000  # Then visit http://localhost:8000
```

### Check git status
```bash
git status
git log --oneline -5
```

### Stage changes and commit
```bash
git add .
git commit -m "Description of changes"
```

### Push to GitHub Pages
```bash
git push origin main
```

## Styling Guidelines

When editing styles, maintain consistency:
- Use CSS custom properties (`:root` variables) for colors
- Keep border-radius at 16px for cards, 25px for buttons
- Maintain gradient border hover effects on interactive elements
- Ensure mobile-first responsive adjustments
- Test across all four breakpoints

## Content Guidelines

- Projects showcase data analysis work (Python, R, SQL, BigQuery)
- Focus areas: data visualization, machine learning, statistical modeling
- Emphasis on football/sports analytics as a passion project area
- Professional tone with clear technical explanations
- Code should include explanatory comments in project articles
