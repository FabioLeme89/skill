---
name: prompt-engineering
description: "Master prompt engineering for AI models: LLMs, image generators, video models. Techniques: chain-of-thought, few-shot, system prompts, negative prompts. Models: Claude, GPT-4, Gemini, FLUX, Veo, Stable Diffusion prompting. Use for: better AI outputs, consistent results, complex tasks, optimization. Triggers: prompt engineering, how to prompt, better prompts, prompt tips, prompting guide, llm prompting, image prompt, ai prompting, prompt optimization, prompt template, prompt structure, effective prompts, prompt techniques"
---

# Prompt Engineering Guide

Master prompt engineering for AI models.

## Quick Start

python\nuser_input = request.args.get(\"query\")\nresult = db.execute(f\"SELECT * FROM users WHERE name = {user_input}\")\n```\n\nProvide specific issues and fixes."
}'
```

### Basic Structure

```
[Role/Context] + [Task] + [Constraints] + [Output Format]
```

### Task Clarity

```bash
# Bad: vague
"Help me with my code"

# Good: specific
"Debug this Python function that should return the sum of even numbers from a list, but returns 0 for all inputs:

def sum_evens(numbers):
    total = 0
    for n in numbers:
        if n % 2 == 0:
            total += n
        return total

Identify the bug and provide the corrected code."
```

### Basic Structure

```
[Subject] + [Style] + [Composition] + [Lighting] + [Technical]
```

### Quality Keywords

```
photorealistic, 8K, ultra detailed, sharp focus, professional,
masterpiece, high quality, best quality, intricate details
```

### Basic Structure

```
[Shot Type] + [Subject] + [Action] + [Setting] + [Style]
```

### Temporal Keywords

```
slow motion, timelapse, real-time, smooth motion,
continuous shot, quick cuts, frozen moment
```

### Claude

- Excels at nuanced instructions
- Responds well to role-playing
- Good at following complex constraints
- Prefers explicit output formats

### GPT-4

- Strong at code generation
- Works well with examples
- Good structured output
- Responds to "let's think step by step"

### FLUX

- Detailed subject descriptions
- Style references work well
- Lighting keywords important
- Negative prompts supported

### Veo

- Camera movement keywords
- Cinematic language works well
- Action descriptions important
- Include temporal context

## Common Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Too vague | Unpredictable output | Add specifics |
| Too long | Model loses focus | Prioritize key info |
| Conflicting | Confuses model | Remove contradictions |
| No format | Inconsistent output | Specify format |
| No examples | Unclear expectations | Add few-shot |

### Code Review

```
Review this [language] code for:
1. Bugs and logic errors
2. Security vulnerabilities
3. Performance issues
4. Code style/best practices

Code:
[code]

For each issue found, provide:
- Line number
- Issue description
- Severity (high/medium/low)
- Suggested fix
```

### Content Writing

```
Write a [content type] about [topic].

Audience: [target audience]
Tone: [formal/casual/professional]
Length: [word count]
Key points to cover:
1. [point 1]
2. [point 2]
3. [point 3]

Include: [specific elements]
Avoid: [things to exclude]
```

### Image Generation

```
[Subject with details], [setting/background], [lighting type],
[art style or photography style], [composition], [quality keywords]
```
