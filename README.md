<p align="center">
  <a href="https://buildcord.dev/"><img src="assets/logo.png" alt="Buildcord" width="96" height="96"></a>
</p>

<h1 align="center">Buildcord MCP server</h1>

<p align="center">
  Build and change Discord bots from ChatGPT, Claude, Cursor or any AI app that supports remote MCP servers.
</p>

<p align="center">
  <a href="https://cursor.com/en/install-mcp?name=buildcord&config=eyJ1cmwiOiJodHRwczovL2FwaS5idWlsZGNvcmQuZGV2L21jcCJ9"><img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Add to Cursor" height="32"></a>
  <a href="https://insiders.vscode.dev/redirect/mcp/install?name=buildcord&config=%7B%22name%22%3A%22buildcord%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//api.buildcord.dev/mcp%22%7D"><img src="https://img.shields.io/badge/VS_Code-Install_server-0098FF?logo=visualstudiocode&logoColor=white" alt="Install in VS Code" height="32"></a>
</p>

[Buildcord](https://buildcord.dev/) is a visual builder for Discord bots. You make a bot out of flows: slash commands, replies to things that happen in a server, schedules, buttons and forms, each made of steps like sending a message, giving a role or saving data.

This MCP server lets an AI app do the building for you. Describe what the bot should do, and the app creates the flows, embeds, modals and data in your bot's draft. You check the result in the builder and deploy when you're happy.

```text
https://api.buildcord.dev/mcp
```

It's a remote server with OAuth sign-in, so there's nothing to install and no API key to copy. The first time an app connects, you sign in to Buildcord and choose what it can access.

## Connect

### Claude

In Claude, open **Settings** > **Connectors**, select **Add custom connector** and paste the address above. Then select **Connect** and sign in.

### Claude Code

```sh
claude mcp add --transport http buildcord https://api.buildcord.dev/mcp
```

Then run `/mcp` in Claude Code and sign in.

Or install the plugin, which adds the server and skills that teach Claude how to build with it:

```text
/plugin marketplace add buildcord-dev/mcp
/plugin install buildcord@buildcord
```

### ChatGPT

Open **Settings** > **Apps** > **Advanced settings** and turn on **Developer mode**. Select **Create app**, paste the address above and choose **OAuth**.

### Cursor

Use the **Add to Cursor** button above, or add this to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "buildcord": { "url": "https://api.buildcord.dev/mcp" }
  }
}
```

### VS Code

Use the **Install in VS Code** button above, or add this to `.vscode/mcp.json`:

```json
{
  "servers": {
    "buildcord": { "type": "http", "url": "https://api.buildcord.dev/mcp" }
  }
}
```

### Codex

```sh
codex mcp add buildcord --url https://api.buildcord.dev/mcp
```

### Windsurf

Add this to `~/.codeium/windsurf/mcp_config.json`:

```json
{
  "mcpServers": {
    "buildcord": { "serverUrl": "https://api.buildcord.dev/mcp" }
  }
}
```

### Gemini CLI

```sh
gemini mcp add --transport http buildcord https://api.buildcord.dev/mcp
```

### Devin, Manus and other apps

Add a remote MCP server with the address `https://api.buildcord.dev/mcp` and OAuth sign-in. In Devin, that's **Settings** > **MCP Marketplace** > **Add your own**. In Manus, it's **Connectors** > **Add MCP by URL**.

## What you can ask for

- "Make my bot a /poll command that posts a question with up to four buttons and counts the votes."
- "Welcome new members with an embed that greets them by name."
- "Add a /ticket command that opens a private thread for the person who ran it."
- "Show me my bot's flows and what's wrong with them, then fix them."

## Tools

| Tool | What it does |
| --- | --- |
| `whoami` | Your Buildcord account |
| `list_bots` | Lists your bots |
| `create_bot` | Creates a bot |
| `get_bot` | A bot's outline: flows, designs, data and problems |
| `update_bot` | Changes a bot's name, description, presence and intents |
| `read_step_catalogue` | How flows work, and every step's settings and outputs |
| `create_flow` | Creates a flow with its steps |
| `read_flow` | Reads a flow |
| `edit_flow` | Adds, changes and wires steps in a flow |
| `update_flow` | Changes a flow's settings |
| `save_embed` | Creates or edits an embed |
| `save_components` | Creates or edits buttons and select menus |
| `save_modal` | Creates or edits a modal |
| `save_variable` | Creates or edits a variable |
| `save_collection` | Creates or edits a collection and its rows |
| `read_item` | Reads an embed, component set, modal, variable or collection |
| `delete_item` | Deletes a flow or design, after you confirm |
| `show_bot` | Shows a bot or a flow as a diagram, in apps that support it |
| `get_builder_link` | A link to open something in the Buildcord builder |

## What it can't do

- See or set your bot's token or other secrets. Those stay in the builder.
- Deploy. Changes land in the bot's draft; you deploy with the **Deploy** button in the builder.
- Act on Discord itself, such as your servers, members or messages.

## Links

- [Buildcord](https://buildcord.dev/), the Discord bot builder
- [Connect an AI app](https://docs.buildcord.dev/ai-apps), the full guide
- [Documentation](https://docs.buildcord.dev/)
- [Templates](https://buildcord.dev/templates/), ready-made bots to start from
- [MCP Registry entry](https://registry.modelcontextprotocol.io/v0.1/servers?search=dev.buildcord/buildcord)
- [Privacy](https://buildcord.dev/privacy/) and [terms](https://buildcord.dev/terms/)

Questions or problems: [support@buildcord.dev](mailto:support@buildcord.dev).

This repository holds the server's listing for MCP registries. The server itself runs at `api.buildcord.dev`.
