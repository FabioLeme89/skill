---
name: logo-design-guide
description: "Logo design principles and AI image generation best practices for creating logos. Covers logo types, prompting techniques, scalability rules, and iteration workflows. Use for: brand identity, startup logos, app icons, favicons, logo concepts. Triggers: logo design, create logo, brand logo, logo generation, ai logo, logo maker, icon design, brand mark, logo concept, startup logo, app icon logo"
---

# Logo Design Guide

Design effective logos with AI image generation.

## Logo Types

| Type | Description | When to Use | Example |
|------|-------------|-------------|---------|
| **Wordmark** | Company name styled as logo | Strong brand name, short (< 10 chars) | Google, Coca-Cola |
| **Lettermark** | Initials only | Long company name, formal | IBM, HBO, CNN |
| **Pictorial** | Recognizable icon/symbol | Universal brand, works without text | Apple, Twitter bird |
| **Abstract** | Geometric/non-literal shape | Tech companies, conceptual brands | Nike swoosh, Pepsi |
| **Mascot** | Character illustration | Friendly brands, food/sports | KFC Colonel, Pringles |
| **Combination** | Icon + wordmark together | New brands needing both recognition and name | Burger King, Adidas |

## Critical AI Limitation

**AI image generators cannot reliably render text.** Letters will be distorted, misspelled, or garbled.

Strategy:
1. Generate the **icon/symbol only** with AI
2. Add text/wordmark in a design tool (Figma, Canva, Illustrator)
3. Or use a combination approach: AI icon + manually set typography

### Keywords That Work

```
flat vector logo, simple minimal icon, single color silhouette,
geometric logo mark, clean lines, negative space design,
line art logo, flat design icon, minimalist symbol
```

### Keywords That Fail

```
❌ photorealistic logo (contradiction — logos aren't photos)
❌ 3D rendered logo (too complex, won't scale down)
❌ gradient logo (inconsistent results, hard to reproduce)
❌ logo with text "Company Name" (text rendering fails)
```

### Prompt Structure

```
flat vector logo of [subject], [style], [color constraint], [background], [additional detail]
```

## Scalability Rules

A logo must work at every size:

| Context | Size | What Must Work |
|---------|------|----------------|
| Favicon | 16x16 px | Silhouette recognizable |
| App icon | 1024x1024 px | Full detail visible |
| Social avatar | 400x400 px | Clear at a glance |
| Business card | ~1 inch | Clean print reproduction |
| Billboard | 10+ feet | No pixelation, simple enough |

### Scalability Checklist

- [ ] Recognizable as a 16px favicon (squint test)
- [ ] Works in single color (black on white)
- [ ] Works inverted (white on black)
- [ ] No tiny details that disappear at small sizes
- [ ] No thin lines that vanish when shrunk
- [ ] Clear silhouette without color

## Color Guidelines

- **Maximum 2-3 colors** for the primary logo
- Must work in **single color** (black, white, or brand primary)
- Consider **color psychology**:
  - Blue: trust, professional (finance, tech, healthcare)
  - Red: energy, urgency (food, entertainment, retail)
  - Green: growth, nature (health, sustainability, finance)
  - Orange: friendly, creative (startups, youth brands)
  - Purple: luxury, wisdom (beauty, education)
  - Black: premium, elegant (fashion, luxury, tech)
- Test on both light and dark backgrounds

## Common Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Too much detail | Loses clarity at small sizes | Simplify to essential shapes |
| Relies on color | Fails in B&W contexts | Design in black first |
| Text in AI generation | Garbled/misspelled letters | Generate icon only, add text manually |
| Trendy effects (glows, shadows) | Dates quickly, reproduction issues | Stick to flat, timeless design |
| Too many colors | Hard to reproduce, expensive printing | Max 2-3 colors |
| Asymmetric without purpose | Looks unfinished | Use intentional asymmetry or stay balanced |

## File Format Delivery

| Format | Use Case |
|--------|----------|
| SVG | Scalable vector, web, editing |
| PNG (transparent) | Digital use, presentations |
| PNG (white bg) | Documents, email signatures |
| ICO / Favicon | Website favicon (16, 32, 48px) |
| High-res PNG (4096px+) | Print, billboards |

Note: AI generates raster images (PNG). For true vector SVG, use the AI output as a reference and trace in a vector tool, or use AI-to-SVG conversion tools.
