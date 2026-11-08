---
name: og-image-design
description: "Open Graph and social sharing image design with platform specs, text placement, and branding. Covers OG meta tags, Twitter cards, LinkedIn previews, and dynamic generation. Use for: social sharing images, blog thumbnails, link previews, social cards. Triggers: og image, open graph, social sharing image, twitter card, social card, link preview image, og meta, sharing preview, social thumbnail, meta image, og:image, twitter:image, linkedin preview"
---

# OG Image Design

Create social sharing images (Open Graph).

## Platform Specifications

| Platform | Dimensions | Aspect Ratio | File Size | Format |
|----------|-----------|--------------|-----------|--------|
| **Facebook** | 1200 x 630 px | 1.91:1 | < 8 MB | JPG, PNG |
| **Twitter/X (summary_large_image)** | 1200 x 628 px | 1.91:1 | < 5 MB | JPG, PNG, WEBP, GIF |
| **Twitter/X (summary)** | 800 x 418 px | 1.91:1 | < 5 MB | JPG, PNG |
| **LinkedIn** | 1200 x 627 px | 1.91:1 | < 5 MB | JPG, PNG |
| **Discord** | 1200 x 630 px | 1.91:1 | < 8 MB | JPG, PNG |
| **Slack** | 1200 x 630 px | 1.91:1 | — | JPG, PNG |
| **iMessage** | 1200 x 630 px | 1.91:1 | — | JPG, PNG |

**Universal safe bet: 1200 x 630 px, PNG or JPG, under 5 MB.**

## The Golden Layout

```
┌──────────────────────────────────────────────────┐
│                                                  │
│  ┌─────────────────────────────────┐  ┌───────┐  │
│  │                                 │  │       │  │
│  │  Title Text (max 60 chars)      │  │ Logo/ │  │
│  │  ───────────────────            │  │ Visual│  │
│  │  Subtitle (max 100 chars)       │  │       │  │
│  │                                 │  │       │  │
│  │  author / site name             │  └───────┘  │
│  └─────────────────────────────────┘             │
│                                                  │
└──────────────────────────────────────────────────┘
  1200 x 630 px
```

### Text

| Rule | Value |
|------|-------|
| Title font size | 48-64px |
| Subtitle font size | 20-28px |
| Max title length | 60 characters (gets truncated on some platforms) |
| Max subtitle length | 100 characters |
| Line height | 1.2-1.3 for titles |
| Font weight | Bold/Black for title, Regular for subtitle |
| Text contrast | WCAG AA minimum (4.5:1 ratio) |

### Safe Zones

```
┌──────────────────────────────────────────────────┐
│  ┌──────────────────────────────────────────────┐│
│  │ 40px padding from all edges                  ││
│  │                                              ││
│  │  Content lives here                          ││
│  │                                              ││
│  │                                              ││
│  └──────────────────────────────────────────────┘│
└──────────────────────────────────────────────────┘
```

- 40px minimum padding from all edges
- Some platforms crop edges or add rounded corners
- Never put critical text in the outer 5%

### Colors

| Background Type | When to Use |
|----------------|-------------|
| Solid brand color | Consistent series, corporate |
| Gradient | Modern, eye-catching |
| Photo with overlay | Blog posts, editorial |
| Dark background | Better contrast, stands out in feeds |

**Dark backgrounds outperform light** in social feeds — most feeds have white/light backgrounds, so dark OG images pop.

## OG Meta Tags Reference

```html
<!-- Essential (Facebook, LinkedIn, Discord, Slack) -->
<meta property="og:title" content="Title here (60 chars max)" />
<meta property="og:description" content="Description (155 chars max)" />
<meta property="og:image" content="https://yoursite.com/og-image.png" />
<meta property="og:url" content="https://yoursite.com/page" />
<meta property="og:type" content="article" />

<!-- Twitter/X specific -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Title here" />
<meta name="twitter:description" content="Description" />
<meta name="twitter:image" content="https://yoursite.com/og-image.png" />

<!-- Image dimensions (optional but recommended) -->
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
```

### Twitter Card Types

| Card Type | Image Size | Use When |
|-----------|-----------|----------|
| `summary` | 800 x 418 (small thumbnail) | Short updates, links |
| `summary_large_image` | 1200 x 628 (full width) | Blog posts, articles, announcements |

**Always use `summary_large_image`** unless you have a specific reason not to — the large image gets significantly more clicks.

## Consistency System

For a blog or site with many pages, create a template system:

| Element | Keep Consistent | Vary |
|---------|----------------|------|
| Background style | Same gradient or brand colors | — |
| Font family | Same font | — |
| Layout | Same positioning | — |
| Logo/branding | Same placement (corner) | — |
| Category badge | Same style | Color per category |
| Title text | Same size/weight | Content changes |

## Testing OG Images

| Tool | URL |
|------|-----|
| Facebook Debugger | developers.facebook.com/tools/debug/ |
| Twitter Card Validator | cards-dev.twitter.com/validator |
| LinkedIn Post Inspector | linkedin.com/post-inspector/ |
| OpenGraph.xyz | opengraph.xyz |

## Common Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| No OG image at all | Platform shows random page element or nothing | Always set og:image |
| Text too small | Unreadable on mobile previews | Title minimum 48px at 1200px width |
| Light background | Gets lost in white/light feeds | Use dark or saturated backgrounds |
| Too much text | Cluttered, overwhelming | Max: title + subtitle + brand |
| Image too large (>5MB) | Some platforms won't load it | Optimize to under 1MB ideally |
| No safe zone padding | Text cropped on some platforms | 40px padding from all edges |
| Different image per platform | Inconsistent sharing experience | Use 1200x630 for everything |
| HTTP image URL | Many platforms require HTTPS | Always serve OG images over HTTPS |
| Relative image path | Won't resolve when shared | Use full absolute URL |
