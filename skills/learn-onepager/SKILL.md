---
name: learn-onepager
description: |
  Creates a concise single-page Word document on a Microsoft technology topic using
  Microsoft Learn documentation as the researched source. Use when user asks to
  "create a one-pager", "make a summary document", "write a one-page overview",
  "one-page brief on", or wants a concise single-page reference about a Microsoft
  technology, service, or concept — grounded in Microsoft Learn.
  Do NOT use for slide decks or presentations (use learn-deck instead), for multi-page
  reports, or for formatting content the user already supplies / non-Learn sources
  (use the built-in docx skill instead). This skill is specifically Learn-researched
  one-pagers.
license: MIT
cowork:
  category: productivity
  icon: DocumentOnePage
metadata:
  author: Daniel Laskewitz
  version: "1.1"
---

# Learn One-Pager

A skill for creating concise Word one-pager documents based on thorough research from Microsoft Learn documentation.

## Workflow

### Step 1: Clarify the Topic

Ask the user what topic they want a one-pager on. Help them scope it:

- "What Microsoft technology or topic would you like me to create a one-pager about?"
- If the topic is broad (e.g., "Power Platform"), ask them to be more specific (e.g., "Power Automate cloud flows" or "Dataverse for Teams")
- Ask about the target audience (developers, decision makers, IT admins, mixed)
- Ask if there's a specific angle (overview, comparison, getting started, best practices)

### Step 2: Research the Topic

Use the `microsoft-learn` connector to thoroughly research the topic. Perform **multiple searches** to gather comprehensive information:

- Search for the main topic overview and description
- Search for key benefits and value proposition
- Search for technical details and how it works
- Look for requirements and prerequisites
- Search for pricing or licensing information if relevant
- Look for common use cases and customer scenarios

**Important:** Perform at least 3-5 searches to ensure thorough coverage. Each search should explore a different angle.

### Step 3: Structure the One-Pager

Organize your research into a clear one-page format:

1. **Title and Tagline** — Clear name with a one-sentence value proposition
2. **What Is It?** — 2-3 sentence overview
3. **Key Benefits** — 3-5 bullet points highlighting the main advantages
4. **How It Works** — Brief explanation of the core mechanism or architecture
5. **Use Cases** — 2-3 concrete scenarios where this applies
6. **Getting Started** — Quick steps or prerequisites to begin
7. **Learn More** — 2-3 links to the most important documentation pages

### Step 4: Create the Document

Use the Word document skill to generate a polished one-pager with:

- Professional formatting with clear headings
- Concise content that fits on a single page
- Bullet points for scanability
- Bold key terms for emphasis
- A clean, readable layout
- Source links at the bottom

## When NOT to Use

- The user wants **slides or a presentation**, not a document → use `learn-deck`.
- The user wants a multi-page report, or already has the content / a non-Learn source
  → use the built-in `docx` skill directly.
- The topic is not a Microsoft technology, service, or concept.

## Guardrails

- **Ground every claim in retrieved Microsoft Learn content.** Do not state benefits,
  requirements, pricing, or capabilities that did not appear in a search result.
- **Never fabricate** product names, numbers, quotes, or links. If a planned section
  isn't supported by research, omit it or mark it `[needs verification]`.
- Place source documentation URLs (verbatim from search results) in the "Learn More"
  section.
- If research returns little or nothing, tell the user and ask whether to narrow or
  change the topic rather than filling gaps from memory.

## Guidelines

- Always let the user choose the topic — never assume
- Be thorough in research: multiple searches are better than one
- Keep it to ONE page — be ruthless about brevity
- Every sentence must earn its place
- Use plain language appropriate for the audience
- Include source links for credibility
- Ask the user if they want any sections adjusted
- Prioritize official Microsoft documentation
