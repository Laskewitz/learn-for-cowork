---
name: learn-deck
description: |
  Creates a PowerPoint presentation on a Microsoft technology topic using Microsoft
  Learn documentation as the researched source. Use when user asks to "create a deck",
  "make a presentation", "build slides", "PowerPoint about", or "slide deck on" a
  Microsoft technology, service, or concept — where the content should be grounded in
  Microsoft Learn.
  Do NOT use for one-page summary documents (use learn-onepager instead), or for
  building a deck from content the user already supplies or from non-Learn sources
  (use the built-in pptx skill instead). This skill is specifically Learn-researched decks.
license: MIT
metadata:
  author: Daniel Laskewitz
  version: "1.1"
---

# Learn Deck

A skill for creating PowerPoint presentations based on thorough research from Microsoft Learn documentation.

## Workflow

### Step 1: Clarify the Topic

Ask the user what topic they want a presentation on. Help them narrow it down:

- "What Microsoft technology or topic would you like me to create a deck about?"
- If the topic is broad (e.g., "Azure"), ask them to be more specific (e.g., "Azure Functions" or "Microsoft Copilot Studio")
- Ask about the target audience (technical, business, mixed)
- Ask about the desired length (5-10 slides, 10-15 slides, etc.)

### Step 2: Research the Topic

Use the `microsoft-learn` connector to thoroughly research the topic. Perform **multiple searches** to gather comprehensive information:

- Search for the main topic overview
- Search for key features and capabilities
- Search for architecture or how it works
- Look for code samples and practical examples
- Search for best practices and common patterns
- Look for getting started guides and prerequisites

**Important:** Perform at least 3-5 searches to ensure thorough coverage. Each search should explore a different angle.

### Step 3: Structure the Presentation

Organize your research into a logical slide structure:

1. **Title Slide** — Topic name and subtitle
2. **Overview** — What it is and why it matters
3. **Key Features/Capabilities** — Main highlights (use bullet points)
4. **How It Works** — Architecture or workflow (suggest a diagram if applicable)
5. **Getting Started** — Prerequisites and first steps
6. **Demo/Example** — Code samples or walkthrough
7. **Best Practices** — Tips and recommendations
8. **Resources** — Links to key documentation pages

### Step 4: Create the Deck

Use the PowerPoint skill to generate the presentation with:

- Clear, concise bullet points (not walls of text)
- One key idea per slide
- Speaker notes with additional detail from the research
- Links to source documentation in the notes

## When NOT to Use

- The user wants a **one-page Word summary**, not slides → use `learn-onepager`.
- The user already has the content and just needs it formatted into a deck, or the
  source is not Microsoft Learn → use the built-in `pptx` skill directly.
- The topic is not a Microsoft technology, service, or concept.

## Guardrails

- **Ground every claim in retrieved Microsoft Learn content.** Do not state features,
  limits, pricing, or capabilities that did not appear in a search result.
- **Never fabricate** API names, version numbers, code samples, or links. If research
  doesn't cover a planned slide, drop the slide or mark it `[needs verification]`.
- Include the source documentation URL (verbatim from search results) in speaker notes
  for each researched claim.
- If research returns little or nothing on the topic, tell the user and ask whether to
  narrow or change the topic rather than filling gaps from memory.

## Guidelines

- Always let the user choose the topic — never assume
- Be thorough in research: multiple searches are better than one
- Keep slides concise — detail goes in speaker notes
- Include source links for credibility
- Ask if they want any specific sections added or removed
- Prioritize official Microsoft documentation
