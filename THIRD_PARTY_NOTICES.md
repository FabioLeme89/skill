# Third-party notices

The following skills are adapted from the `guides/` folder of the inference.sh skills pack
(https://github.com/inference-sh/skills, also mirrored at https://github.com/magentosh/superpowers),
which declares the MIT license (author: inference.sh) in its `plugin.json` and README.

Modifications: removed dependencies on the inference.sh `belt` CLI (frontmatter `allowed-tools`,
install notes, command blocks, documentation links and header images) and dropped empty sections.

Skills: affirmations, ai-marketing-videos, ai-product-photography, ai-social-media-content,
app-store-screenshots, book-cover-design, case-study-writing, character-design-sheet,
competitor-teardown, content-repurposing, customer-persona, data-visualization, email-design,
explainer-video-guide, landing-page-design, linkedin-content, logo-design-guide,
newsletter-curation, og-image-design, pitch-deck-visuals, press-release-writing,
product-changelog, product-hunt-launch, product-photography, prompt-engineering,
seo-content-brief, social-media-carousel, storyboard-creation, talking-head-production,
technical-blog-writing, twitter-thread-creation, video-ad-specs, video-prompting-guide,
youtube-thumbnail-design.

---

## Added 2026-11-08

- **business-growth-mp** (https://github.com/Zuttam/business-growth-mp, MIT, Matan Zutta):
  meta-ads, pulse-hackernews, pulse-instagram, pulse-linkedin, pulse-reddit, pulse-x,
  campaign-creation, campaign-execution, lead-research, list-building.
  Modifications: the five community-pulse skills were renamed with a `pulse-` prefix
  (folder and `name:`) to avoid generic names. Agents and hooks were not included.
  These skills expect a browser-automation MCP (e.g. Claude in Chrome or Playwright MCP).
- **Hedge-Edge-agentic** (https://github.com/Ryko1141/Hedge-Edge-agentic):
  instagram-management (unmodified; written for the "Hedge Edge" prop-firm brand).
- **instagram-agent-skill** (https://github.com/postzen-dev/instagram-agent-skill, MIT, PostZen):
  ig-audit, ig-caption, ig-carousel, ig-comment, ig-dm, ig-human, ig-plan, ig-profile,
  ig-publish, ig-reel, ig-reply, ig-repurpose, ig-story, ig-viral, plus `_extras/postzen-templates/voice.md`.
  The PostZen MCP server (`.mcp.json`) was intentionally NOT installed.
