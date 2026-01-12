---
name: converting-md-to-pdf
description: Converts Markdown files to styled PDF using md-to-pdf with professional themes. Use when asked to convert markdown to PDF, generate PDFs from .md files, or export markdown as PDF with custom styling.
---

# Converting Markdown to PDF

Converts Markdown files to professionally styled PDF using the [md-to-pdf](https://github.com/simonhaenisch/md-to-pdf) CLI tool with curated themes.

## Prerequisites

Ensure md-to-pdf is installed globally:

```bash
npm install -g md-to-pdf
```

## Theme Workflow

When converting markdown to PDF with styling:

1. **Analyze content**: Read the markdown file to understand its type and purpose
2. **Suggest a theme**: Based on content analysis, recommend a theme with reasoning:
   - Technical/code-heavy → **Tech Innovation** (high contrast for code blocks)
   - Corporate/business → **Anthropic Brand** or **Ocean Depths** (professional tone)
   - Environmental/nature → **Forest Canopy** or **Botanical Garden** (earth tones)
   - Creative/marketing → **Sunset Boulevard** or **Midnight Galaxy** (vibrant/dramatic)
   - Academic/research → **Modern Minimalist** (clean, distraction-free)
   - Healthcare/pharma → **Arctic Frost** (clinical precision)
   - Fashion/luxury → **Desert Rose** (elegant, sophisticated)
   - Food/hospitality → **Golden Hour** (warm, inviting)
3. **Present recommendation**: Show the suggested theme with reason, plus the full theme list
4. **Get user preference**: Confirm theme choice and page format (A4, A3, Letter, etc.)
5. **Apply theme**: Use the selected theme's CSS file from `themes/` directory
6. **Convert**: Run md-to-pdf with the theme and format options

### Theme Selection Examples

| Content Type | Suggested Themes | Reason |
|--------------|------------------|--------|
| **Technical/Code** | | |
| API documentation | Tech Innovation, Modern Minimalist | High contrast code blocks; clean technical aesthetic |
| Software tutorials | Tech Innovation, Arctic Frost | Code readability; clinical precision for step-by-step guides |
| Hardware/SystemC guides | Tech Innovation, Ocean Depths | Technical blue tones; professional engineering feel |
| Developer guides | Modern Minimalist, Tech Innovation | Distraction-free reading; syntax highlighting focus |
| **Corporate/Business** | | |
| Quarterly reports | Ocean Depths, Anthropic Brand | Trust-building navy; professional corporate identity |
| Business proposals | Anthropic Brand, Modern Minimalist | Brand authority; clean persuasive layout |
| Financial statements | Ocean Depths, Arctic Frost | Professional credibility; clarity and precision |
| Company policies | Modern Minimalist, Anthropic Brand | Clean hierarchy; authoritative tone |
| Investor pitch decks | Sunset Boulevard, Tech Innovation | Attention-grabbing; innovation signaling |
| **Creative/Marketing** | | |
| Product launches | Sunset Boulevard, Midnight Galaxy | Vibrant energy; dramatic impact |
| Brand guidelines | Anthropic Brand, Desert Rose | Identity-focused; sophisticated aesthetics |
| Marketing campaigns | Sunset Boulevard, Golden Hour | Warm engagement; emotional appeal |
| Event invitations | Midnight Galaxy, Desert Rose | Dramatic elegance; romantic sophistication |
| Portfolio showcases | Midnight Galaxy, Sunset Boulevard | Creative flair; visual impact |
| **Academic/Research** | | |
| Research papers | Modern Minimalist, Arctic Frost | Academic clarity; scientific precision |
| Thesis documents | Modern Minimalist, Ocean Depths | Professional scholarship; serious tone |
| Case studies | Ocean Depths, Forest Canopy | Analytical depth; grounded credibility |
| White papers | Anthropic Brand, Modern Minimalist | Authority; clean argumentation |
| **Nature/Environment** | | |
| Sustainability reports | Forest Canopy, Botanical Garden | Earth tones; environmental alignment |
| Outdoor guides | Forest Canopy, Arctic Frost | Natural palette; adventure clarity |
| Wildlife documentation | Botanical Garden, Forest Canopy | Organic colors; nature connection |
| Climate reports | Arctic Frost, Ocean Depths | Cool tones; scientific credibility |
| **Food/Hospitality** | | |
| Restaurant menus | Golden Hour, Botanical Garden | Appetite appeal; fresh organic feel |
| Recipe books | Botanical Garden, Golden Hour | Garden-to-table; warm comfort |
| Hotel brochures | Golden Hour, Desert Rose | Warm welcome; luxurious comfort |
| Café guides | Botanical Garden, Sunset Boulevard | Fresh artisan; cozy vibrancy |
| **Health/Wellness** | | |
| Medical documentation | Arctic Frost, Modern Minimalist | Clinical precision; clean readability |
| Wellness guides | Forest Canopy, Botanical Garden | Calming nature; holistic feel |
| Pharmaceutical content | Arctic Frost, Ocean Depths | Scientific trust; professional authority |
| Fitness programs | Tech Innovation, Sunset Boulevard | Energy; motivation |
| **Fashion/Luxury** | | |
| Fashion lookbooks | Desert Rose, Midnight Galaxy | Elegant sophistication; dramatic style |
| Beauty guides | Desert Rose, Botanical Garden | Soft luxury; natural beauty |
| Jewelry catalogs | Midnight Galaxy, Desert Rose | Opulent drama; refined elegance |
| Interior design | Desert Rose, Golden Hour | Sophisticated warmth; aesthetic harmony |
| Wedding planning | Desert Rose, Botanical Garden | Romantic tones; garden elegance |
| **Education** | | |
| Course materials | Modern Minimalist, Arctic Frost | Learning clarity; focused reading |
| Student handbooks | Ocean Depths, Anthropic Brand | Institutional trust; authority |
| Training manuals | Tech Innovation, Modern Minimalist | Step-by-step clarity; professional training |
| Lesson plans | Botanical Garden, Golden Hour | Engaging warmth; creative learning |

## Available Themes

| Theme | Best For | Primary Colors |
|-------|----------|----------------|
| **Anthropic Brand** | Corporate, professional | Dark `#141413` + Orange `#d97757` |
| **Tech Innovation** | Technical docs, software | Blue `#0066ff` + Cyan `#00ffff` |
| **Ocean Depths** | Financial, consulting | Navy `#1a2332` + Teal `#2d8b8b` |
| **Midnight Galaxy** | Creative, entertainment | Purple `#2b1e3e` + Lavender `#a490c2` |
| **Modern Minimalist** | Academic, clean reports | Black `#1a1a1a` + Red accent |
| **Arctic Frost** | Healthcare, clean tech | Steel Blue `#4a6fa5` + Ice `#d4e4f7` |
| **Botanical Garden** | Food, natural products | Fern `#4a7c59` + Marigold `#f9a620` |
| **Desert Rose** | Fashion, beauty, weddings | Dusty Rose `#d4a5a5` + Burgundy `#5d2e46` |
| **Forest Canopy** | Environmental, sustainability | Forest `#2d4a2b` + Sage `#7d8471` |
| **Golden Hour** | Hospitality, artisan | Mustard `#f4a900` + Terracotta `#c1666b` |
| **Sunset Boulevard** | Marketing, lifestyle | Orange `#e76f51` + Coral `#f4a261` |

For detailed theme specifications, see `themes.md`.

## Page Formats

| Format | Size | Use Case |
|--------|------|----------|
| `A4` | 210 × 297 mm | International standard (default) |
| `A3` | 297 × 420 mm | Large documents, presentations |
| `Letter` | 8.5 × 11 in | US standard |
| `Legal` | 8.5 × 14 in | Legal documents |

## Basic Usage

### Convert with default settings

```bash
md-to-pdf document.md
```

### Convert with theme

```bash
md-to-pdf document.md --stylesheet themes/anthropic-brand.css
```

### Convert with theme and page format

```bash
md-to-pdf document.md --stylesheet themes/tech-innovation.css --pdf-options '{"format": "A3", "margin": "25mm"}'
```

### Convert with code highlighting

```bash
md-to-pdf document.md --stylesheet themes/ocean-depths.css --highlight-style monokai
```

## Common Options

| Option | Description | Example |
|--------|-------------|---------|
| `--stylesheet` | Theme CSS file | `--stylesheet themes/anthropic-brand.css` |
| `--pdf-options` | Page format, margins | `--pdf-options '{"format": "A4", "margin": "20mm"}'` |
| `--highlight-style` | Code syntax theme | `--highlight-style monokai` |
| `--watch` | Live preview mode | `--watch` |

## Front-matter Configuration

Configure options directly in the markdown file:

```yaml
---
pdf_options:
  format: A4
  margin: 25mm
stylesheet: themes/tech-innovation.css
---
```

## Conversion Workflow

1. **Identify content type**: Determine what kind of document (technical, corporate, creative)
2. **Recommend theme**: Suggest appropriate theme based on content
3. **Get user preference**: Confirm theme and page format choice
4. **Copy theme if needed**: Copy CSS from skill's `themes/` to user's workspace
5. **Convert**: Run `md-to-pdf` with selected options
6. **Verify**: Confirm PDF was created successfully

## Creating Custom Themes

To create a custom theme:

1. Start with an existing theme from `themes/` as a base
2. Modify CSS variables in `:root` for colors
3. Update font imports and font-family declarations
4. Adjust element-specific styles (headings, code, tables)
5. Save as new `.css` file

### Theme CSS Structure

```css
/* Font imports */
@import url('https://fonts.googleapis.com/css2?family=...');

/* Color variables */
:root {
  --primary: #000000;
  --accent: #0066ff;
  --background: #ffffff;
}

/* Base styles */
body { font-family: ...; color: var(--primary); }

/* Headings */
h1, h2, h3 { font-family: ...; }

/* Code blocks */
pre { background: ...; }
code { background: ...; }

/* Tables */
table, th, td { ... }

/* Other elements */
a, blockquote, ul, ol { ... }
```

## Examples

### Technical Documentation (SystemC, APIs)

```bash
md-to-pdf api-docs.md --stylesheet themes/tech-innovation.css --pdf-options '{"format": "A4", "margin": "20mm"}' --highlight-style monokai
```

### Corporate Report

```bash
md-to-pdf quarterly-report.md --stylesheet themes/anthropic-brand.css --pdf-options '{"format": "Letter", "margin": "25mm"}'
```

### Creative Portfolio

```bash
md-to-pdf portfolio.md --stylesheet themes/midnight-galaxy.css --pdf-options '{"format": "A3", "margin": "30mm"}'
```

### Academic Paper

```bash
md-to-pdf research-paper.md --stylesheet themes/modern-minimalist.css --pdf-options '{"format": "A4", "margin": "25mm"}'
```
