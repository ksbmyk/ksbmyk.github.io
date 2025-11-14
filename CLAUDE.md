# CLAUDE.md - AI Assistant Guide

This document provides comprehensive guidance for AI assistants working with the ksbmyk.github.io repository.

## Project Overview

**Project Name**: chobishiba Portfolio Site
**Type**: Static GitHub Pages Personal Portfolio
**Owner**: ksbmyk (chobishiba)
**Focus**: Creative Coding, Ruby, p5.js, PicoRuby, Physical Computing

This is a personal portfolio website showcasing the work of chobishiba, a Creative Coder & Rubyist who explores expression through code, from screen to physical computing.

## Repository Structure

```
ksbmyk.github.io/
├── index.html              # Main single-page portfolio site
├── assets/                 # All media assets
│   ├── works/
│   │   ├── highlights/    # Recent Highlights section images (1200x800px+)
│   │   ├── sketches/      # Daily Sketches thumbnails (800x800px+)
│   │   └── led/           # PicoRuby LED works images (800x800px+)
│   ├── activities/        # Event/workshop photos
│   └── README.md          # Asset structure documentation
├── .git/                  # Git repository data
└── CLAUDE.md             # This file
```

### Future Planned Structure (noted in index.html comments)

```
/
├── index.html
├── sketch/                # Daily sketches (separate repo/site)
├── projects/              # Detailed project pages (planned)
│   ├── tangible-code.html
│   ├── digital-springboard.html
│   └── fractal-flower.html
└── assets/
```

## Technology Stack

### Core Technologies
- **HTML5**: Semantic markup
- **CSS3**: Custom properties (CSS variables), Flexbox, Grid
- **No Framework**: Pure HTML/CSS, no build process
- **No JavaScript**: Currently static HTML/CSS only

### Design System
```css
CSS Variables (from :root):
--bg-primary: #f8f8f8      /* Primary background */
--bg-secondary: #ffffff     /* Card backgrounds */
--text-primary: #333333     /* Main text */
--text-secondary: #666666   /* Secondary text */
--accent: #00447c          /* Primary accent (deep navy) */
--accent-hover: #003366    /* Hover state */
--border: #e1e4e8          /* Border color */
```

### Responsive Breakpoint
- Mobile breakpoint: `@media (max-width: 768px)`
- Mobile-first grid layouts using `repeat(auto-fit, minmax(...))`

## Content Structure

### Main Sections

1. **Header Navigation** - Social links (GitHub, X/Twitter, Instagram, note)
2. **Hero Section** - Name, tagline, description, quick links
3. **Recent Highlights** - Feature projects with images, tech tags, descriptions
4. **Daily Sketches Preview** - Currently commented out, planned feature
5. **PicoRuby LED Works** - Currently commented out, planned feature
6. **Activities Timeline** - Chronological list of talks, workshops, exhibitions
7. **Footer** - Copyright notice

### Activity Types & Styling
```
.type-exhibition   - Blue (#e3f2fd / #1565c0)
.type-talk         - Pink (#fce4ec / #ad1457)
.type-lt           - Purple (#f3e5f5 / #6a1b9a)
.type-workshop     - Orange (#fff3e0 / #e65100)
.type-award        - Orange (#ffe0b2 / #e65100)
.type-participation - Green (#e8f5e9 / #2e7d32)
.type-coach        - Teal (#e0f2f1 / #00695c)
.type-complete     - Gray (#fafafa / #616161)
```

## Development Workflows

### Git Workflow

1. **Branch Naming Convention**: `claude/[feature-description]-[session-id]`
   - Example: `claude/fix-highlight-viewport-011CV66UTTzfJjWbo6jbUSHj`

2. **Commit Message Style**:
   - Japanese language is acceptable
   - Clear, descriptive messages
   - Examples from history:
     - "ファーストビューにHighlightsセクションが表示されるようレイアウト最適化"
     - "add highlight images"
     - "assetsディレクトリを整理し、画像パスを更新"

3. **Deployment**:
   - GitHub Pages automatic deployment from main branch
   - Changes to main are immediately published to https://ksbmyk.github.io/

### Making Changes

#### Adding New Highlights

1. Add image to `assets/works/highlights/` (recommended: 1200x800px, PNG/JPG)
2. Add new highlight card in the `.highlight-grid` section (around line 620)
3. Follow existing card structure:
   ```html
   <div class="highlight-card">
       <div class="highlight-image">
           <img src="assets/works/highlights/[filename]" alt="[description]">
       </div>
       <div class="highlight-content">
           <div class="highlight-label">[Type] [Year] [Month]</div>
           <div class="highlight-title">[Title]</div>
           <div class="highlight-description">[Description]</div>
           <div class="highlight-tech">
               <span class="tech-tag">[Tech]</span>
           </div>
           <div class="highlight-links">
               <a href="[url]" target="_blank">[Label] ↗</a>
           </div>
       </div>
   </div>
   ```

#### Adding New Activities

1. Locate the appropriate year section (or create new with `<div class="activity-year">[Year]</div>`)
2. Add activity item in chronological order (newest first):
   ```html
   <div class="activity-item">
       <div class="activity-month">[Month]</div>
       <div class="activity-title">
           <span class="activity-type type-[type]">[Type]</span>
           [Title]
       </div>
       <div class="activity-meta">[Description]</div>
       <div class="activity-meta">
           <a href="[url]" class="activity-link" target="_blank">[Label] ↗</a>
       </div>
   </div>
   ```

#### Modifying Styles

- All styles are in `<style>` tag in `<head>` (lines 24-571)
- Use CSS custom properties for colors when possible
- Maintain existing responsive design patterns
- Test on mobile viewport (≤768px)

### Testing Changes

1. **Local Preview**: Open `index.html` in browser
2. **Check Responsive Design**: Test at mobile width (≤768px)
3. **Validate Links**: Ensure all external links work and open in new tabs
4. **Image Optimization**: Ensure images are web-optimized (compressed, appropriate size)
5. **Accessibility**: Check alt text on images, semantic HTML

## Key Conventions & Best Practices

### Content Guidelines

1. **Language**: Mixed Japanese/English content is standard
   - UI labels often in English
   - Descriptions often in Japanese
   - External links labeled in Japanese (e.g., "サイト ↗", "スライド ↗")

2. **External Link Pattern**: Always include:
   - `target="_blank"` for external links
   - `rel="noopener noreferrer"` for security (on social icons)
   - Arrow indicator: ↗

3. **Image Alt Text**: Always provide descriptive alt text in Japanese

### Code Style

1. **HTML**:
   - 4-space indentation
   - Semantic HTML5 elements
   - Comments in Japanese acceptable
   - Keep structure flat and simple

2. **CSS**:
   - 4-space indentation
   - Use CSS custom properties for colors
   - Mobile-first responsive approach
   - Class names: kebab-case (e.g., `.highlight-card`)
   - Organize by component/section with comments

3. **File Organization**:
   - Single HTML file approach
   - Assets organized by purpose in subdirectories
   - No build process or dependencies

### Assets Management

1. **Image Guidelines**:
   - Highlights: 1200x800px+ (landscape)
   - Sketches: 800x800px+ (square)
   - LED works: 800x800px+ (square)
   - Format: JPG (photos), PNG (graphics with transparency)
   - Optimize for web before adding

2. **Naming Convention**:
   - Lowercase
   - Underscores for spaces
   - Descriptive names
   - Example: `mrubygirls_matsue1st.png`

## Common Tasks

### Task: Add a New Project Highlight

1. Prepare image (1200x800px+) and save to `assets/works/highlights/`
2. Edit `index.html`
3. Find the `.highlight-grid` section (around line 620)
4. Add new card at the beginning (before existing cards)
5. Fill in all content fields
6. Test locally
7. Commit with descriptive message

### Task: Update Activities Section

1. Edit `index.html`
2. Find the appropriate year section (or create new)
3. Add activity item in chronological order (newest first)
4. Use appropriate `.type-[type]` class
5. Include relevant links
6. Commit changes

### Task: Modify Design/Layout

1. Edit CSS in `<style>` block
2. Use existing CSS custom properties
3. Test both desktop and mobile views
4. Ensure changes don't break existing sections
5. Commit with description of visual changes

### Task: Add New Section

1. Study existing section structure in HTML
2. Create matching CSS following existing patterns
3. Add section in logical position within page flow
4. Update navigation if needed
5. Test responsive behavior
6. Commit changes

## Deployment

### GitHub Pages Configuration
- **Source**: Main branch (root directory)
- **Custom Domain**: None (uses default github.io)
- **Build**: None required (static HTML)
- **URL**: https://ksbmyk.github.io/

### Deployment Process
1. Merge changes to main branch via PR
2. GitHub Pages automatically rebuilds (usually within 1-2 minutes)
3. Verify changes at https://ksbmyk.github.io/

### Deployment Checklist
- [ ] All links tested and working
- [ ] Images load correctly
- [ ] Responsive design works on mobile
- [ ] No console errors
- [ ] Meta tags accurate (title, description)
- [ ] External links have target="_blank"

## Important Notes for AI Assistants

### Do's ✅

1. **Maintain existing design language**: Use established color scheme and styling patterns
2. **Preserve bilingual content**: Keep Japanese/English mix consistent with existing content
3. **Follow HTML structure**: Maintain semantic HTML and existing class naming
4. **Test responsive design**: Always consider mobile viewport
5. **Optimize images**: Ensure web-optimized images before adding
6. **Use descriptive commits**: Clear messages (Japanese or English both acceptable)
7. **Validate HTML**: Ensure valid HTML5 structure
8. **Check links**: Verify external links work and include proper attributes

### Don'ts ❌

1. **Don't add frameworks**: Keep it pure HTML/CSS, no JavaScript frameworks
2. **Don't add build process**: No bundlers, preprocessors, or build tools
3. **Don't break single-file structure**: Keep all CSS in `<style>` tag
4. **Don't change color scheme**: Use existing CSS custom properties
5. **Don't remove comments**: Keep planning comments (e.g., future structure notes)
6. **Don't ignore responsive**: Always maintain mobile-first approach
7. **Don't add JavaScript**: Currently a static HTML/CSS site
8. **Don't change git workflow**: Follow existing branch naming conventions

### When in Doubt

1. **Study existing patterns**: Look at how similar content is structured
2. **Match existing style**: Maintain consistency with current design
3. **Preserve functionality**: Don't break existing features
4. **Ask for clarification**: When requirements are ambiguous
5. **Test thoroughly**: Especially responsive behavior and links

## Contact & External Resources

### Owner's Links
- **GitHub**: https://github.com/ksbmyk
- **X/Twitter**: https://x.com/chobishiba
- **Instagram**: https://www.instagram.com/chobishiba.rb/
- **note**: https://note.com/chobishiba
- **Daily Sketches**: https://ksbmyk.github.io/sketch/

### Related Projects
- **mruby Girls**: https://mrubygirls.github.io/
- **Speaker Deck**: https://speakerdeck.com/chobishiba
- **NEORT**: https://neort.io/ (various artworks)

## Version History

- **2025-11-14**: Initial CLAUDE.md created
  - Documented repository structure
  - Defined development workflows
  - Established conventions and best practices

---

*This document is maintained for AI assistants working with this repository. Keep it updated as the project evolves.*
