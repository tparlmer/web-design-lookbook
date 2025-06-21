# Hugo Site Architecture for Pretty Web Design

## Current HTML Pages Inventory

### Typography Experiments
- `page.html` - E-ink reading style (Crimson Text, warm paper tones)
- `gothamink.html` - Gotham font family showcase (all 9 weights)
- `super-serif.html` - Serif fonts love letter (Playfair Display, Crimson Text)
- `psycho-serif.html` - [needs review]

### Brutalist & Experimental
- `brutalist.html` - Web brutalist e-ink (ASCII art, monospace, high contrast)
- `brutalzine.html` - Digital e-zine for architectural ink art (Gotham, minimal 3-color)
- `brutalink.html` - BRUTALINK OS interface (e-ink brutalist OS)

### Style Movements
- `swissinternationalstyle.html` - Swiss International Style (mathematical grids, Gotham)
- `gwernstyle.html` - [needs review]
- `medievaldropcap.html` - [needs review]

### Themed Pages
- `economist.html` & `darkeconomist.html` - News/economics styling
- `hackernews.html` - Tech community styling
- `emojiscript.html` - Emoji-based design
- `timeline.html` - Temporal presentation
- `the-old-internet.html` - Nostalgic web design

## Proposed Hugo Site Structure

### Content Organization
```
content/
├── experiments/
│   ├── typography/
│   │   ├── e-ink-reading.md          # page.html
│   │   ├── gotham-showcase.md        # gothamink.html
│   │   └── serif-love-letter.md     # super-serif.html
│   ├── brutalist/
│   │   ├── web-brutalism.md          # brutalist.html
│   │   ├── digital-zine.md           # brutalzine.html
│   │   └── brutalink-os.md           # brutalink.html
│   └── movements/
│       └── swiss-international.md    # swissinternationalstyle.html
├── gallery/
│   └── architectural-drawings.md     # showcase MU-*.jpg assets
├── about/
│   └── design-philosophy.md
└── _index.md                         # Homepage
```

### Template Strategy

#### 1. Experiment Layout (`layouts/experiments/single.html`)
- Each design experiment gets its own dedicated page
- Preserve exact styling from original HTML
- Include design rationale/explanation
- Navigation between related experiments

#### 2. Gallery Layout (`layouts/gallery/single.html`)
- Showcase architectural ink drawings
- Integrate with typography experiments that reference them
- Clean, minimal presentation matching user's aesthetic preferences

#### 3. Homepage (`layouts/index.html`)
- Visual index of all experiments
- Typography-focused navigation
- Minimal, architectural aesthetic
- Quick preview/thumbnail system

### Asset Management

#### Fonts
- Move Gotham font family to `static/fonts/`
- Create CSS file with all @font-face definitions
- Enable Hugo's asset pipeline for font optimization

#### Images
- Move `assets/MU-*.jpg` to `static/images/`
- Enable Hugo's image processing for responsive delivery
- Maintain high quality for architectural detail

#### Stylesheets
- Convert inline styles to Hugo partials
- Shared Tailwind base with experiment-specific overrides
- Typography-focused CSS organization

### Content Front Matter Structure

```yaml
---
title: "E-ink Reading Experience"
date: 2024-01-15
experiment_type: "typography"
fonts_used: ["Crimson Text"]
color_palette: ["warm_paper", "sepia", "charcoal"]
design_philosophy: "readability, comfort, sustainability"
assets: ["custom-css"]
related_experiments: ["gotham-showcase", "serif-love-letter"]
---
```

### Navigation & Discovery

#### 1. Taxonomies
- **By Typography**: serif, sans-serif, monospace, display
- **By Movement**: brutalist, swiss, e-ink, experimental
- **By Color Approach**: monochrome, minimal-color, warm-tones
- **By Purpose**: reading, showcase, interface, art

#### 2. Cross-References
- Link related experiments (e.g., all Gotham-based designs)
- Typography evolution narratives
- Design philosophy connections

### Hugo-Specific Benefits

#### 1. Content Management
- Markdown for design explanations/philosophy
- Easy updates to experiments
- Version control for design iterations

#### 2. Performance
- Static site generation for fast loading
- Image optimization for architectural drawings
- CSS/JS bundling and minification

#### 3. Development Workflow
- Live reload during design iterations
- Easy A/B testing of design variations
- Consistent templating across experiments

### Implementation Phases

#### Phase 1: Core Structure
1. Set up Hugo site with basic config
2. Create experiment and gallery content types
3. Build homepage with experiment index
4. Convert 3-4 key pages (page.html, gothamink.html, brutalzine.html, swissinternationalstyle.html)

#### Phase 2: Enhanced Features
1. Add remaining experiments
2. Implement taxonomy system
3. Build cross-reference navigation
4. Add design philosophy documentation

#### Phase 3: Polish & Optimization
1. Performance optimization
2. Responsive design improvements
3. Advanced typography features
4. Search/filtering capabilities

### Considerations

#### Maintaining Design Integrity
- Each experiment should preserve its unique aesthetic
- Avoid over-templating that sanitizes the designs
- Keep experimental/artistic elements intact

#### User Experience
- Clear navigation between different design philosophies
- Educational context for each approach
- Respect for typography as art form

#### Technical Debt
- Some HTML pages may need refactoring for Hugo
- Font loading optimization
- Asset pipeline configuration

### Next Steps
1. Initialize Hugo site structure
2. Create basic templates
3. Convert one experiment as proof of concept
4. Iterate based on results
