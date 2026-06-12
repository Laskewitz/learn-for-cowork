# learn-mcp-cowork

A [Cowork](https://learn.microsoft.com/en-us/microsoft-365/copilot/cowork/cowork-manage-plugins) plugin that connects to the [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp).

## What's included

- **manifest.json** — M365 Unified App Manifest (v1.28) declaring the Learn MCP connector
- **color.png** — 192×192 full-color app icon (placeholder)
- **outline.png** — 32×32 outline icon (placeholder)

## Plugin details

| Field | Value |
|-------|-------|
| MCP Server URL | `https://learn.microsoft.com/api/mcp` |
| Authentication | None |
| Transport | Streamable HTTP |

## Packaging

```powershell
Compress-Archive -Path manifest.json, color.png, outline.png -DestinationPath learn-mcp-cowork.zip
```

## Sideloading

1. Go to **M365 Admin Center** > **Manage Apps** > **Upload custom app**
2. Upload the `.zip` package
3. The plugin will appear in Cowork's **Sources & Skills** panel
