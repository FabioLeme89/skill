---
name: data-visualization
description: "Data visualization with chart selection, color theory, and annotation best practices. Covers chart types (bar, line, scatter, heatmap), axes rules, and storytelling with data. Use for: charts, graphs, dashboards, reports, presentations, infographics, data stories. Triggers: data visualization, chart, graph, data chart, bar chart, line chart, scatter plot, data viz, visualization, dashboard chart, infographic data, data presentation, chart design, plot, heatmap, pie chart alternative"
---

# Data Visualization

Create clear, effective data visualizations.

### Which Chart for Which Data?

| Data Relationship | Best Chart | Never Use |
|------------------|-----------|-----------|
| **Change over time** | Line chart | Pie chart |
| **Comparing categories** | Bar chart (horizontal for many categories) | Line chart |
| **Part of a whole** | Stacked bar, treemap | Pie chart (controversial but: bar is always clearer) |
| **Distribution** | Histogram, box plot | Bar chart |
| **Correlation** | Scatter plot | Bar chart |
| **Ranking** | Horizontal bar chart | Vertical bar, pie |
| **Geographic** | Choropleth map | Bar chart |
| **Composition over time** | Stacked area chart | Multiple pie charts |
| **Single metric** | Big number (KPI card) | Any chart (overkill) |
| **Flow / process** | Sankey diagram | Bar chart |

### The Pie Chart Problem

Pie charts are almost always the wrong choice:

```
❌ Pie chart problems:
   - Hard to compare similar-sized slices
   - Can't show more than 5-6 categories
   - 3D pie charts are always wrong
   - Impossible to read exact values

✅ Use instead:
   - Horizontal bar chart (easy comparison)
   - Stacked bar (part of whole)
   - Treemap (hierarchical parts)
   - Just a table (if precision matters)
```

### Axes

| Rule | Why |
|------|-----|
| Always start Y-axis at 0 (bar charts) | Prevents misleading visual |
| Line charts CAN start above 0 | When showing change, not absolute values |
| Label both axes | Reader shouldn't have to guess units |
| Remove unnecessary gridlines | Reduce visual noise |
| Use horizontal labels | Vertical text is hard to read |
| Sort bar charts by value | Don't use alphabetical order unless there's a reason |

### Color

| Principle | Application |
|-----------|------------|
| **Max 5-7 colors** per chart | More becomes unreadable |
| **Highlight one thing** | Grey everything else, color the focus |
| **Sequential** for magnitude | Light → dark for low → high |
| **Diverging** for positive/negative | Red ← neutral → blue |
| **Categorical** for groups | Distinct hues, similar brightness |
| **Colorblind-safe** | Avoid red/green only — add shapes or labels |
| **Consistent meaning** | If blue = revenue, keep it blue everywhere |

### Good Color Palettes

```python
# Sequential (low to high)
sequential = ["#eff6ff", "#bfdbfe", "#60a5fa", "#2563eb", "#1d4ed8"]

# Diverging (negative to positive)
diverging = ["#ef4444", "#f87171", "#d1d5db", "#34d399", "#10b981"]

# Categorical (distinct groups)
categorical = ["#3b82f6", "#f59e0b", "#10b981", "#8b5cf6", "#ef4444"]

# Colorblind-safe
cb_safe = ["#0077BB", "#33BBEE", "#009988", "#EE7733", "#CC3311"]
```

### Text and Labels

| Element | Rule |
|---------|------|
| **Title** | States the insight, not the data type. "Revenue doubled in Q2" not "Q2 Revenue Chart" |
| **Annotations** | Call out key data points directly on the chart |
| **Legend** | Avoid if possible — label directly on chart lines/bars |
| **Font size** | Minimum 12px, 14px+ for presentations |
| **Number format** | Use K, M, B for large numbers (42K not 42,000) |
| **Data labels** | Add to bars/points when exact values matter |

### The Narrative Arc

| Step | What to Do | Example |
|------|-----------|---------|
| 1. **Context** | Set up what the reader needs to know | "We track customer acquisition cost monthly" |
| 2. **Tension** | Show the problem or change | "CAC increased 40% in Q3" |
| 3. **Resolution** | Show the insight or solution | "But LTV increased 80%, so unit economics improved" |

### Title as Insight

```
❌ Descriptive titles (what the chart shows):
   "Q3 Revenue by Product Line"
   "Monthly Active Users 2024"
   "Customer Satisfaction Survey Results"

✅ Insight titles (what the chart means):
   "Enterprise product drives 70% of revenue growth"
   "User growth accelerated after the free tier launch"
   "Support response time is the #1 satisfaction driver"
```

### Annotation Techniques

| Technique | When to Use |
|-----------|------------|
| **Call-out label** | Highlight a specific data point ("Peak: 320K") |
| **Reference line** | Show target/benchmark ("Goal: 100K") |
| **Shaded region** | Mark a time period ("Product launch window") |
| **Arrow + text** | Draw attention to trend change |
| **Before/after line** | Show impact of an event |

## Common Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Pie charts | Hard to compare, always misleading | Use bar charts or treemaps |
| Y-axis not starting at 0 (bar charts) | Exaggerates differences | Start at 0 for bars, OK to truncate for lines |
| Too many colors | Visual noise, confusing | Max 5-7 colors, highlight only what matters |
| No title or generic title | Reader doesn't know the insight | Title = the takeaway, not the data type |
| 3D charts | Distorts data, looks unprofessional | Always use 2D |
| Dual Y-axes | Misleading, hard to read | Use two separate charts |
| Alphabetical sort on bar charts | Hides the story | Sort by value (largest first) |
| No labels on axes | Reader can't interpret | Always label with units |
| Chartjunk (decorative elements) | Distracts from data | Remove everything that doesn't convey information |
| Red/green only for color coding | Colorblind users can't read | Use shapes, patterns, or colorblind-safe palettes |
