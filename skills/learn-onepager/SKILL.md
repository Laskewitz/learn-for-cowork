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
metadata:
  author: Daniel Laskewitz
  version: "1.2"
---

# Learn One-Pager

A skill for creating concise Word one-pager documents based on thorough research from Microsoft Learn documentation.

## Workflow

### Step 1: Confirm Topic, Size, and Audience

**Do not start researching until the user has confirmed all three of the following.**
Ask about any that are missing, then briefly restate them back and get explicit
confirmation before moving on.

1. **Topic** — What Microsoft technology or topic the one-pager should cover.
   - If the topic is broad (e.g., "Power Platform"), ask them to be more specific (e.g., "Power Automate cloud flows" or "Dataverse for Teams").
2. **Size** — How much detail and length the document should have. Offer these options:
   - **1 page** — a single concise summary page
   - **Medium** — a fuller single page (denser sections)
   - **Large** — roughly two pages
   - **Extra large** — a multi-page brief (3+ pages)
3. **Audience** — Who the document is for. Offer these options:
   - **Business decision makers**
   - **IT pros**
   - **Developers**
   - Or another audience the user specifies (e.g., mixed)

Only proceed to research once the topic, size, and audience are all confirmed.

### Step 2: Research the Topic

Use the `microsoft-learn` connector's `search` and `get_page` tools to thoroughly research the topic. Perform **multiple tool calls** to gather comprehensive information:

- Call `search` for the main topic overview and description
- Call `search` for key benefits and value proposition
- Call `search` for technical details and how it works
- Call `search` for requirements and prerequisites
- Call `search` for pricing or licensing information if relevant
- Call `get_page` on the most relevant results to fetch full article content

**Important:** Perform at least 3-5 `search` calls to ensure thorough coverage. Each call should explore a different angle. Follow up with `get_page` on the top results.

### Step 3: Structure the One-Pager

Organize your research into a clear format. **Tailor the depth and length to the
confirmed size**, and pitch the content to the confirmed audience (e.g., business
decision makers want value and outcomes; developers want technical detail):

For a **1 page** document, keep every section tight. For **Medium / Large / Extra
large**, expand the sections below with more detail and examples to fill the length:

1. **Title and Tagline** — Clear name with a one-sentence value proposition
2. **What Is It?** — 2-3 sentence overview
3. **Key Benefits** — 3-5 bullet points highlighting the main advantages
4. **How It Works** — Brief explanation of the core mechanism or architecture
5. **Use Cases** — 2-3 concrete scenarios where this applies
6. **Getting Started** — Quick steps or prerequisites to begin
7. **Learn More** — 2-3 links to the most important documentation pages

### Step 4: Create the Document

Use the `docx` skill to generate a polished one-pager with:

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
- Confirm topic, size, and audience before researching
- Be thorough in research: multiple searches are better than one
- Match the length to the confirmed size — be ruthless about brevity for a 1 page document
- Every sentence must earn its place
- Use plain language appropriate for the audience
- Include source links for credibility
- Ask the user if they want any sections adjusted
- Prioritize official Microsoft documentation
