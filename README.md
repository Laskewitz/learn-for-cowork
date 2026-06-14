# 📚 Learn for Copilot Cowork

A [Cowork](https://learn.microsoft.com/en-us/microsoft-365/copilot/cowork/cowork-manage-plugins) plugin that connects to the [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp) and includes a research skill for deep-diving into Microsoft documentation.

## 🧠 About the Microsoft Learn MCP Server

The [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp) gives AI agents access to Microsoft's official documentation. It's a remote MCP server using Streamable HTTP — no authentication required, free to use.

**What it can do:**

- 🔍 Search through Microsoft Learn documentation
- 📄 Fetch complete articles
- 💻 Find code samples

The server is powered by the same knowledge service behind [Ask Learn](https://learn.microsoft.com) and Copilot for Azure. Content refreshes incrementally after updates, with a full refresh once daily.

## 🎯 Included Skills

### 📊 Learn Deck

Creates a PowerPoint presentation on a Microsoft technology topic:

1. **Topic Selection** — Asks what you'd like a deck about and for whom
2. **Research** — Performs multiple searches across Learn documentation
3. **Structure** — Organizes findings into a logical slide flow
4. **Create** — Generates a polished PowerPoint with speaker notes and source links

### 📝 Learn One-Pager

Creates a concise Word one-pager on a Microsoft technology topic:

1. **Topic Selection** — Asks what you'd like a one-pager about and the audience
2. **Research** — Performs multiple searches for comprehensive coverage
3. **Structure** — Distills findings into a scannable one-page format
4. **Create** — Generates a professional Word document with clear formatting

> 💡 Both skills are designed to do **multiple calls** to the Learn MCP Server, ensuring thorough research rather than surface-level results.

## 📦 What's included

```
learn-for-cowork.zip
├── manifest.json
├── color.png (192×192)
├── outline.png (32×32)
└── skills/
    ├── learn-deck/
    │   └── SKILL.md
    └── learn-onepager/
        └── SKILL.md
```

## 📥 Download

Grab the latest `learn-for-cowork.zip` from the [Releases](https://github.com/Laskewitz/learn-for-cowork/releases/latest) page.

## ⚙️ Plugin details

| Field | Value |
|-------|-------|
| MCP Server URL | `https://learn.microsoft.com/api/mcp` |
| Authentication | None |
| Transport | Streamable HTTP |

## 🏗️ Packaging

```powershell
Compress-Archive -Path manifest.json, color.png, outline.png, skills -DestinationPath learn-for-cowork.zip -Force
```

Or with a npm script:

```bash
npm run package
```

## 🚀 Sideloading

1. Go to **Microsoft 365 Admin Center** > **Agents** > **All agents**
2. Click the **...** (more options) menu
3. Select **+ Add agent**
4. Upload the `.zip` package
5. The plugin will appear in Cowork's **Sources & Skills** panel ✨

