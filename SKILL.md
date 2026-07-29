---
name: generate-case-visual
description: Turn a verified customer use case from Lark Base, a Lark document, or structured text into a brand-aligned one-page illustrated case visual. Use when the user asks to generate a customer-story image, case-study one-pager, presales case visual, website-style customer infographic, or a reusable image prompt from a case record. The workflow researches the customer's official website for visual style, preserves only verified case facts, enforces content and logo permissions, generates the image, and returns the prompt and source list.
---

# Generate Case Visual

## Overview

Create a readable 16:9 customer case visual that combines verified Lark outcomes with the customer's brand personality. Treat the case repository as the factual source and official customer channels as visual-style sources only.

## Defaults

- Language: English unless the user specifies another language.
- Format: one-page 16:9 landscape raster image.
- Use label: `INTERNAL DRAFT` unless verified permissions and the user explicitly request an external-ready output.
- Style: hand-drawn editorial infographic with brand-aligned composition; do not copy a site's exact artwork.
- Research: official customer website and official brand-owned channels only.
- Deliverables: generated image, reusable complete prompt, fact snapshot, and brand-source links.

## Required Input

Accept any one of:

- A Lark Base use-case record or view URL
- A Lark customer-case document URL
- Structured case facts pasted by the user

Optional inputs:

- Customer's official website
- Language
- Intended use: internal presales, speaker briefing, customer visit, website, social, or another channel
- Preferred visual style or a reference image
- Output title or required exact wording

If no official website is supplied, identify it from official sources. Ask before proceeding only when identity is ambiguous.

## Workflow

### 1. Resolve the case source

- For a `/base/` URL, use the Lark Base capability to read the target record, linked customer, linked source document, and permission fields.
- For a `/docx/` or `/wiki/` URL, use the Lark document capability to read the full case content.
- When one document contains multiple use cases, isolate the use case named by the user or the Base record. Do not merge unrelated outcomes.
- If a linked source is unavailable, continue only with facts that are visible and verified in the accessible source.

Read [references/case-data-and-permissions.md](references/case-data-and-permissions.md) whenever the source is a Base record or permissions are not already explicit.

### 2. Run the permission gate

Resolve content scope, customer name/logo authorization, business-data authorization, review status, and intended channel before generation.

- `禁止使用` / prohibited: stop and explain the restriction.
- `内部匿名` / internal anonymous: remove the customer name, logo, identifiable locations, and distinctive branded elements. Use a neutral industry visual system.
- `内部实名` / internal named: customer name and brand-inspired styling may be used internally; use a clear `INTERNAL ONLY` label. Do not use a logo unless logo permission is independently confirmed.
- `可公开` / public: still verify name/logo and business-data permissions separately. Public scope does not automatically authorize a logo or every metric.
- Missing or conflicting permission values: ask the user to confirm; do not infer.

External-ready outputs require all relevant permissions plus explicit user intent. Otherwise produce an internal draft.

### 3. Build a verified fact snapshot

Extract and normalize:

- Customer and industry
- Business context
- Challenge
- Lark solution and products used
- Workflow or adoption scope
- Quantitative results with units and time periods
- Qualitative value
- AI use case and maturity, if explicitly verified
- Approved quote, if present
- Permission and review status
- Source for every claim

Use this factual priority:

1. Structured, reviewed case fields
2. Linked approved case document
3. CSM-confirmed facts provided by the user
4. Public Lark customer story

Do not use the customer's website as evidence for Lark outcomes. Never invent metrics, dates, quotes, product usage, AI adoption, or causal claims.

### 4. Research the brand

Browse the customer's official website and, when useful, official brand-owned social or press pages. Capture:

- Dominant and accent colors
- Typography personality
- Signature shapes, textures, illustration style, or photography style
- Recognizable products, environments, architecture, packaging, vehicles, or operational objects
- Brand tone: premium, playful, technical, warm, minimal, high-energy, and so on

Use the research for art direction, not factual case claims. Prefer interpretation over imitation. Do not reproduce copyrighted hero artwork, campaign compositions, or protected characters.

### 5. Select the visual story

Choose one central visual metaphor that connects the customer's operation to the Lark-enabled transformation. Examples:

- Logistics: connected routes, control tower, or operations blueprint
- Retail: store-to-HQ operating loop
- Manufacturing: factory flow or digital production line
- Professional services: client journey or collaboration map
- Fashion and beauty: editorial spread, atelier, or collection board

Use a clear hierarchy:

1. Outcome-led headline
2. Customer context and central scene
3. Challenge
4. Lark solution
5. Verified outcomes
6. Business value or operating loop

Keep the content selective. A one-page visual should communicate one transformation story, not reproduce the full case document.

### 6. Build the image prompt

Read [references/image-prompt-spec.md](references/image-prompt-spec.md) and create a complete production prompt containing:

- Canvas and medium
- Brand art direction
- Composition and section placement
- Exact on-image copy
- Scene and object descriptions
- Color, typography, texture, and icon direction
- Permission label
- Negative constraints

Use short exact copy. Reduce the number of claims before reducing legibility. Treat all words and numbers as immutable strings.

### 7. Generate

Use the image generation capability to create the visual directly. When the user provides a reference image, inspect it first and use it for layout or medium guidance without copying customer-specific artwork.

Do not put an unapproved customer logo in the prompt. If logo use is approved but accurate rendering is critical, prefer a provided official logo asset; otherwise use the customer name as text.

### 8. Quality check

Inspect the generated image and verify:

- Customer identity matches the selected case
- All numbers, units, dates, and percentages match the fact snapshot
- No unsupported quote, AI claim, product claim, or award appears
- Customer name and logo follow permissions
- Spelling and wording are readable
- Visual elements suit the customer's industry and brand
- The use label is present and correct
- No confidential fields, URLs, record IDs, or internal notes appear

If a critical item is wrong, regenerate with a correction-focused prompt. Do not silently describe the image as correct.

### 9. Deliver

Return:

1. The generated image
2. The complete reusable prompt
3. A compact fact snapshot used in the visual
4. Official brand-source links
5. Any caveat about permissions, missing evidence, or text-rendering risk

Do not write the image or prompt back to Base unless the user explicitly asks.

## Ask Before Continuing Only When

- The case has missing or conflicting permissions.
- The customer identity or official website is ambiguous.
- A number, quote, or AI claim is unverified but the user wants it shown.
- The request requires a real person's likeness.
- The user requests an external-ready asset without sufficient authorization.
- The source does not contain enough verified information for a coherent visual.

Otherwise make reasonable design decisions and generate the first version.

## Example Invocations

- `Use $generate-case-visual on this Base record. English, internal presales, official website auto-discovery.`
- `Use $generate-case-visual to turn this case document into a hand-drawn 16:9 customer story.`
- `Use $generate-case-visual to make a public website-ready one-pager; validate permissions before generation.`

**Appropriate for:** Templates, boilerplate code, document templates, images, icons, fonts, or any files meant to be copied or used in the final output.

---

**Not every skill requires all three types of resources.**
