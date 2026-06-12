# 📚 learn-for-cowork

A [Cowork](https://learn.microsoft.com/en-us/microsoft-365/copilot/cowork/cowork-manage-plugins) plugin that connects to the [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp).

## 🧠 About the Microsoft Learn MCP Server

The [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp) gives AI agents access to Microsoft's official documentation. It's a remote MCP server using Streamable HTTP — no authentication required, free to use.

**What it can do:**

- 🔍 Search through Microsoft Learn documentation
- 📄 Fetch complete articles
- 💻 Find code samples

The server is powered by the same knowledge service behind [Ask Learn](https://learn.microsoft.com) and Copilot for Azure. Content refreshes incrementally after updates, with a full refresh once daily.

## 📦 What's included

- **manifest.json** — M365 Unified App Manifest (v1.28) declaring the Learn MCP connector
- **color.png** — 192×192 full-color app icon
- **outline.png** — 32×32 outline icon

## ⚙️ Plugin details

| Field | Value |
|-------|-------|
| MCP Server URL | `https://learn.microsoft.com/api/mcp` |
| Authentication | None |
| Transport | Streamable HTTP |

## 🏗️ Packaging

```powershell
Compress-Archive -Path manifest.json, color.png, outline.png -DestinationPath learn-for-cowork.zip -Force
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

