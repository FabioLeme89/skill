---
name: talking-head-production
description: "Talking head video production with AI avatars, lipsync, and voiceover. Recommended: P-Video-Avatar (fastest, cheapest, built-in TTS). Also covers OmniHuman, PixVerse, Fabric. Portrait requirements, audio quality, production workflows. Use for: spokesperson videos, course content, social media, presentations, demos. Triggers: talking head, avatar video, lipsync, lip sync, ai spokesperson, virtual presenter, ai presenter, omnihuman, talking avatar, video presenter, ai talking head, presenter video, ai face video, p-video-avatar"
---

# Talking Head Production

Create talking head videos with AI avatars and lipsync.

## Portrait Requirements

The source portrait image is critical. Poor portraits = poor video output.

### Must Have

| Requirement | Why | Spec |
|------------|-----|------|
| **Center-framed** | Avatar needs face in predictable position | Face centered in frame |
| **Head and shoulders** | Body visible for natural gestures | Crop below chest |
| **Eyes to camera** | Creates connection with viewer | Direct frontal gaze |
| **Neutral expression** | Starting point for animation | Slight smile OK, not laughing/frowning |
| **Clear face** | Model needs to detect features | No sunglasses, heavy shadows, or obstructions |
| **High resolution** | Detail preservation | Min 512x512 face region, ideally 1024x1024+ |

### Background Options

| Type | When to Use |
|------|-------------|
| Solid color | Professional, clean, easy to composite |
| Soft bokeh | Natural, lifestyle feel |
| Office/studio | Business context |
| Dynamic (P-Video-Avatar) | Use `video_prompt` to set background |

## Model Selection

**Start with P-Video-Avatar** — it's 18x faster and 6x cheaper than alternatives, with built-in TTS.

| Model | App ID | Built-in TTS | Best For |
|-------|--------|-------------|----------|
| **P-Video-Avatar** | `pruna/p-video-avatar` | **Yes (30 voices, 10 langs)** | **Best overall: speed, cost, quality** |
| OmniHuman 1.5 | `bytedance/omnihuman-1-5` | No | Multi-character, gestures |
| OmniHuman 1.0 | `bytedance/omnihuman-1-0` | No | Single character |
| Fabric 1.0 | `falai/fabric-1-0` | Yes | Image talks with lipsync |
| PixVerse Lipsync | `falai/pixverse-lipsync` | No | Realistic lipsync |

### Cost & Speed Comparison

| Model | Speed (per sec of video) | Cost per second |
|-------|-------------------------|----------------|
| **P-Video-Avatar** | **~1.83s/s** | **$0.025** |
| OmniHuman 1.5 | ~28s/s (15x slower) | $0.16 (6.4x more) |
| Fabric 1.0 | ~34s/s (18x slower) | $0.14 (5.6x more) |

### Simple: Text Script -> Video (P-Video-Avatar)

No separate TTS step needed — P-Video-Avatar has built-in voices:

### Audio-Driven (Any Model)

Provide your own audio file:

### Multi-Character Conversation

OmniHuman 1.5 supports up to 2 characters:

### Long-Form (Stitched Clips)

For content longer than ~60 seconds, split into segments:

### Multilingual Content

P-Video-Avatar supports 10 languages with built-in TTS:

## Audio Quality (for non-TTS workflows)

When providing your own audio, quality directly impacts lipsync accuracy.

| Parameter | Target | Why |
|-----------|--------|-----|
| Background noise | None/minimal | Noise confuses lipsync timing |
| Volume | Consistent throughout | Prevents sync drift |
| Sample rate | 44.1kHz or 48kHz | Standard quality |
| Format | MP3 128kbps+ or WAV | Compatible with all tools |

## Available Voices (P-Video-Avatar)

**Female:** Zephyr, Kore, Leda, Aoede, Callirrhoe, Autonoe, Despina, Erinome, Laomedeia, Achernar, Gacrux, Pulcherrima, Vindemiatrix, Sulafat

**Male:** Puck, Charon, Fenrir, Orus, Enceladus, Iapetus, Umbriel, Algenib, Algieba, Schedar, Achird, Zubenelgenubi, Sadachbia, Sadaltager, Alnilam, Rasalgethi

**Languages:** English (US), English (UK), Spanish, French, German, Italian, Portuguese (Brazil), Japanese, Korean, Hindi

## Framing Guidelines

```
┌─────────────────────────────────┐
│          Headroom (minimal)     │
│  ┌───────────────────────────┐  │
│  │                           │  │
│  │     ● ─ ─ Eyes at 1/3 ─ ─│─ │ ← Eyes at top 1/3 line
│  │    /|\                    │  │
│  │     |   Head & shoulders  │  │
│  │    / \  visible           │  │
│  │                           │  │
│  └───────────────────────────┘  │
│       Crop below chest          │
└─────────────────────────────────┘
```

## Common Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Low-res portrait | Blurry face, poor lipsync | Use 1024x1024+ face region |
| Profile/side angle | Lipsync can't track mouth well | Use frontal or near-frontal |
| Noisy audio | Lipsync drifts, looks unnatural | Use built-in TTS or record clean |
| Too-long clips | Quality degrades | Split into segments, stitch |
| Sunglasses/obstruction | Face features hidden | Clear face required |
| Inconsistent lighting | Uncanny when animated | Even, soft lighting |
