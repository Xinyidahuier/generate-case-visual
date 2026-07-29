# Image Prompt Specification

Use this structure to turn a verified fact snapshot and brand brief into a production-ready image prompt.

## Prompt Structure

### 1. Objective

State the deliverable in one sentence:

```text
Create a polished 16:9 landscape, single-page illustrated customer case infographic for [intended channel].
```

### 2. Visual medium

Choose one coherent medium and describe it precisely. Preferred default:

```text
Hand-drawn editorial infographic with tactile marker, colored-pencil, and light watercolor textures; clean professional finish; generous negative space; crisp information hierarchy.
```

Do not mix more than two strong style families. Avoid generic “corporate infographic” language without a distinctive medium.

### 3. Brand art direction

Translate official brand observations into:

- Primary, secondary, and accent colors
- Typography personality, not a copyrighted typeface requirement
- Shapes, line style, texture, and whitespace
- Brand-relevant objects and environments
- Emotional tone

Example:

```text
Use deep navy and white as the base, with restrained red route lines and warm kraft-paper accents. The scene should feel operational, reliable, cross-border, and human.
```

Do not claim that an inferred palette is an official brand guideline unless a guideline source confirms it.

### 4. Composition

Specify positions and hierarchy. A reliable layout:

```text
- Top 18%: customer name, outcome-led headline, short subtitle, use label.
- Middle 42%: one panoramic hero scene showing the operating context and transformation.
- Bottom 40%: three or four bordered modules for challenge, solution, outcomes, and business value.
```

Alternative layouts may use an editorial spread, circular operating loop, journey map, or control-tower blueprint when they better fit the brand story.

### 5. Exact copy

Put every required string in quotation marks. Keep:

- Headline: 6–12 words
- Subtitle: up to 18 words
- Module heading: 1–4 words
- Module body: 3 bullets, ideally 3–8 words each
- Metric callout: one number plus a short descriptor

Write:

```text
Render the following text exactly as written. Do not paraphrase, translate, add, or invent text.
```

Then list the complete copy by region.

### 6. Scene and objects

Describe a small set of meaningful objects. Each should help tell the transformation story. Good examples include stores, warehouses, factories, desks, mobile devices, delivery routes, approval stamps, dashboards, task cards, or collaboration nodes.

Avoid decorative objects that imply unverified products, geography, scale, or results.

### 7. Data visualization

Use simple visual devices:

- Large metric numerals
- Before/after timeline
- Process arrows
- Connected operating loop
- Small icon-and-label modules

Do not generate detailed charts unless underlying data points exist.

### 8. Permission label

Include exactly one:

- `INTERNAL DRAFT`
- `INTERNAL ONLY`
- `INTERNAL ONLY · ANONYMIZED`
- `DRAFT`

Place it unobtrusively but legibly in a top or bottom corner.

### 9. Negative constraints

Always include:

```text
No invented numbers, quotes, awards, locations, product claims, or AI claims. No tiny illegible copy. No extra logos. No watermark. No stock-photo collage. No copied website artwork. Do not alter the required text.
```

Add case-specific exclusions, including any confidential information or prohibited identity element.

## Recommended Narrative Patterns

### Operations blueprint

Best for logistics, manufacturing, and multi-location operations. Use a central control point with routes or process flows feeding modules around it.

### Editorial spread

Best for fashion, beauty, design, and premium consumer brands. Use strong negative space, product or environment sketches, oversized headline typography, and restrained metrics.

### Store-to-HQ loop

Best for retail, food service, and franchise businesses. Show frontline signals flowing to HQ decisions and back to execution.

### Transformation journey

Best when the case has a clear before/after process or time reduction. Use three to five stages and one dominant verified outcome.

## Prompt Template

```text
Create a polished 16:9 landscape, single-page illustrated customer case infographic for [INTENDED USE].

VISUAL MEDIUM
[MEDIUM AND FINISH]

BRAND ART DIRECTION
[COLORS, TYPOGRAPHY PERSONALITY, SHAPES, TEXTURES, OBJECTS, TONE]

COMPOSITION
[REGIONS, HIERARCHY, HERO SCENE, MODULE POSITIONS]

EXACT COPY
Render the following text exactly as written. Do not paraphrase, translate, add, or invent text.

Top:
- "[CUSTOMER OR ANONYMOUS LABEL]"
- "[HEADLINE]"
- "[SUBTITLE]"
- "[PERMISSION LABEL]"

Module 1 — "[HEADING]":
- "[BULLET]"
- "[BULLET]"
- "[BULLET]"

Module 2 — "[HEADING]":
- "[BULLET]"
- "[BULLET]"
- "[BULLET]"

Outcomes:
- "[VERIFIED METRIC OR OUTCOME]"
- "[VERIFIED METRIC OR OUTCOME]"

SCENE AND OBJECTS
[CENTRAL METAPHOR AND VERIFIED OPERATIONAL ELEMENTS]

DATA VISUALIZATION
[METRICS, PROCESS FLOW, OR OPERATING LOOP]

NEGATIVE CONSTRAINTS
No invented numbers, quotes, awards, locations, product claims, or AI claims. No tiny illegible copy. No extra logos. No watermark. No stock-photo collage. No copied website artwork. Do not alter the required text. [CASE-SPECIFIC EXCLUSIONS]
```

## Image QA Checklist

After generation, compare the image with the prompt and fact snapshot:

- Required copy is present and correctly spelled.
- Each number and unit is exact.
- The central scene matches the customer's real industry.
- Brand cues are recognizable without copying source artwork.
- The layout remains readable at typical laptop width.
- The permission label is visible.
- No unrequested logo, location, person, quote, or AI symbol appears.

Regenerate if a core number, customer identity, permission label, or headline is wrong. For minor decorative differences, keep the image if they do not introduce a factual implication.
