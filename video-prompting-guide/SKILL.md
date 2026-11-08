---
name: video-prompting-guide
description: "Best practices and techniques for writing effective AI video generation prompts. Covers: Veo, Seedance, Wan, Grok, Kling, Runway, Pika, Sora prompting strategies. Learn: shot types, camera movements, lighting, pacing, style keywords, negative prompts. Use for: improving video quality, getting consistent results, professional video prompts. Triggers: video prompt, how to prompt video, veo prompts, video generation tips, better ai video, video prompt engineering, video prompt guide, video prompt template, ai video tips, video prompt best practices, video prompt examples, cinematography prompts"
---

# Video Prompting Guide

Best practices for writing effective AI video generation prompts.

## Prompt Structure Formula

```
[Shot Type] + [Subject] + [Action] + [Setting] + [Lighting] + [Style] + [Technical]
```

### Example Breakdown

```
"Slow motion close-up of coffee being poured into a white ceramic cup,
steam rising, morning sunlight streaming through window, warm color grading,
cinematic, 4K, shallow depth of field"
```

- **Shot Type**: Slow motion close-up
- **Subject**: Coffee
- **Action**: Being poured
- **Setting**: White ceramic cup, window
- **Lighting**: Morning sunlight
- **Style**: Warm color grading, cinematic
- **Technical**: 4K, shallow depth of field

## Shot Types

| Shot Type | Description | Use For |
|-----------|-------------|---------|
| Wide shot | Shows entire scene | Establishing location |
| Medium shot | Waist-up framing | Conversations, actions |
| Close-up | Face or detail | Emotion, product detail |
| Extreme close-up | Single feature | Drama, texture |
| Aerial shot | Bird's eye view | Landscapes, scale |
| Low angle | Camera looking up | Power, grandeur |
| High angle | Camera looking down | Vulnerability |
| Dutch angle | Tilted camera | Unease, tension |
| POV shot | First person view | Immersion |

## Camera Movements

| Movement | Description | Effect |
|----------|-------------|--------|
| Tracking shot | Camera follows subject | Dynamic, engaging |
| Dolly in/out | Camera moves toward/away | Focus, reveal |
| Pan | Horizontal rotation | Survey scene |
| Tilt | Vertical rotation | Reveal height |
| Crane shot | Vertical + horizontal | Dramatic reveal |
| Handheld | Slight shake | Realism, urgency |
| Steadicam | Smooth following | Professional, cinematic |
| Zoom | Lens zoom in/out | Quick focus change |
| Static | No movement | Contemplation, stability |

## Lighting Keywords

| Keyword | Effect |
|---------|--------|
| Golden hour | Warm, soft, romantic |
| Blue hour | Cool, moody, twilight |
| High key | Bright, minimal shadows |
| Low key | Dark, dramatic shadows |
| Rim lighting | Subject outlined with light |
| Backlit | Light from behind subject |
| Soft lighting | Gentle, flattering |
| Hard lighting | Sharp shadows, contrast |
| Neon | Colorful, urban, cyberpunk |
| Natural lighting | Realistic, documentary |

### Cinematic Styles

```
cinematic, film grain, anamorphic lens, letterbox,
shallow depth of field, bokeh, 35mm film,
color grading, theatrical
```

### Visual Aesthetics

```
minimalist, maximalist, vintage, retro, futuristic,
cyberpunk, steampunk, noir, pastel, vibrant,
muted colors, high contrast, desaturated
```

### Quality Keywords

```
4K, 8K, high resolution, photorealistic,
hyperrealistic, ultra detailed, professional,
broadcast quality, HDR
```

## Common Mistakes to Avoid

| Mistake | Problem | Better Approach |
|---------|---------|-----------------|
| Too vague | "A nice video" | Specify shot, subject, style |
| Too complex | Multiple scenes | One scene per prompt |
| No motion | Static description | Include camera movement or action |
| Conflicting styles | "Minimalist maximalist" | Choose one aesthetic |
| No lighting | Undefined mood | Specify lighting conditions |

### Google Veo

- Excels at realistic, cinematic content
- Supports audio generation (Veo 3+)
- Best with detailed, professional prompts
- Frame interpolation available in 3.1

### Seedance

- Strong at dance and human motion
- First-frame control available
- Good for consistent character motion
- Works well with reference images

### Wan 2.5

- Best for image-to-video
- Animates still images naturally
- Good motion prediction
- Works with any image style

### Grok

- Good general-purpose video
- Configurable duration (5-10s)
- Creative interpretations
- Works well with abstract concepts

