<div align="center">

<br/>

<img alt="claude-code-mcp-marketplace" src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=34&duration=2400&pause=900&color=A78BFA&center=true&vCenter=true&width=900&height=80&lines=claude-code-mcp-marketplace"/>

**The package manager for MCP servers.**
_Discover · install · update · audit — all from one CLI._

<br/>

```bash
npx ccmcp install slack
```

<br/>

<p>
<img src="https://img.shields.io/badge/MCP-D97757?style=for-the-badge&logo=anthropic&logoColor=white"/>
<img src="https://img.shields.io/badge/Marketplace-A78BFA?style=for-the-badge"/>
<img src="https://img.shields.io/badge/CLI-4D4D4D?style=for-the-badge&logo=gnubash&logoColor=white"/>
<img src="https://img.shields.io/badge/MIT-000000?style=for-the-badge"/>
</p>

<p>
<img src="https://img.shields.io/github/stars/kasimmj/claude-code-mcp-marketplace?style=social"/>
<img src="https://img.shields.io/github/forks/kasimmj/claude-code-mcp-marketplace?style=social"/>
</p>

</div>

---

## 🛒 The MCP problem

There are hundreds of MCP servers. They're scattered across:
- GitHub (search "mcp-server-*")
- npm (`@modelcontextprotocol/*`)
- PyPI (`mcp-*`)
- GoLang modules
- Random blog posts and tweets

Installing one means:
1. Find the repo
2. Read the install instructions (usually wrong)
3. Manually edit `settings.json`
4. Hope you got the JSON right
5. Restart Claude Code
6. Pray

**`ccmcp` (claude-code-mcp) fixes this.** One CLI. Curated registry. Verified servers.

---

## ⚡ Commands

```bash
# Search
ccmcp search slack
ccmcp search "database"

# Install
ccmcp install slack
ccmcp install slack --scope project   # vs --scope user

# List installed
ccmcp list

# Update
ccmcp update slack
ccmcp update --all

# Remove
ccmcp uninstall slack

# Audit installed servers (security + freshness check)
ccmcp audit
```

The CLI:
- ✅ Validates the server's manifest
- ✅ Checks for known CVEs in its dependencies
- ✅ Tests it boots successfully before saving
- ✅ Edits your settings.json with proper backup
- ✅ Restarts Claude Code if needed (optional)

---

## 📦 Registry

The marketplace tracks **300+ verified MCP servers** across categories:

| Category | Servers |
|----------|---------|
| 🗄️ **Databases** | Postgres, MySQL, SQLite, MongoDB, Redis, Snowflake, BigQuery |
| 💬 **Chat** | Slack, Discord, Telegram, Microsoft Teams, Matrix |
| 📅 **Productivity** | Google Calendar, Notion, Linear, Jira, Asana, Trello |
| 🌐 **APIs** | GitHub, GitLab, Stripe, Twilio, SendGrid, Vercel, Cloudflare |
| ☁️ **Cloud** | AWS, GCP, Azure, DigitalOcean, Hetzner, Render |
| 📊 **Analytics** | Mixpanel, Amplitude, PostHog, Google Analytics |
| 🤖 **AI / LLM** | Hugging Face, OpenAI, Anthropic (extra tooling), Replicate |
| 📁 **Files** | S3, R2, Google Drive, Dropbox, OneDrive |
| 🛒 **Commerce** | Shopify, Stripe, Square, WooCommerce |
| 🎮 **Gaming** | Steam, Discord Game SDK, Unity Cloud |
| 🔐 **Security** | 1Password, Vault, AWS Secrets Manager |
| 🛠️ **Dev Tools** | Sentry, Datadog, Honeycomb, Bugsnag |

Browse online: **[marketplace.ccmcp.dev](https://marketplace.ccmcp.dev)** _(coming soon)_

---

## 🛡️ Security

Every server in the registry has been **manually reviewed** for:

- ✅ Source available on GitHub
- ✅ No obfuscated code
- ✅ Permissions clearly documented
- ✅ Maintained (commits within last 6 months)
- ✅ No known critical CVEs in dependencies

We classify each server by trust tier:

| Tier | Meaning |
|------|---------|
| 🟢 **Official** | Maintained by the service vendor (Slack, GitHub, etc.) |
| 🔵 **Verified** | Maintained by trusted community contributor, code-reviewed |
| 🟡 **Community** | Community-maintained, less rigorous review |
| 🔴 **Experimental** | Use at own risk |

`ccmcp install` shows the tier before installing, and you can configure a minimum:

```bash
ccmcp config set min_trust_tier verified
```

---

## 📂 Server Manifest

Every registered server includes a `mcp.toml`:

```toml
name = "slack"
version = "2.1.0"
description = "Send messages, read channels, manage Slack workspaces."
author = "Slack, Inc."
license = "MIT"
trust_tier = "official"

[install]
type = "npm"                  # npm | pip | go | docker | binary
package = "@slack/mcp-server"
binary_name = "mcp-server-slack"

[runtime]
command = "mcp-server-slack"
env_required = ["SLACK_BOT_TOKEN"]
env_optional = ["SLACK_USER_TOKEN"]

[capabilities]
tools = ["send_message", "read_channel", "list_channels", "react_message"]
resources = ["channels", "users", "files"]

[permissions]
network = ["api.slack.com"]
filesystem = false
shell = false
```

This lets `ccmcp` show you exactly what permissions a server wants **before** you install.

---

## 🤝 Contributing a server

```bash
ccmcp submit ./my-mcp-server
```

This runs the manifest validator + a smoke test + opens a PR against the registry. Approved within 7 days if the manifest is complete.

---

## 🌟 Highlighted picks

### `postgres` 🟢
Query and modify your Postgres databases directly from Claude.

### `linear` 🟢
Browse, create, and update Linear issues without leaving Claude.

### `playwright` 🔵
Drive a browser from Claude. Great for web scraping + e2e testing.

### `aws-cdk` 🔵
Read your CDK stacks, propose changes, generate diffs.

### `huggingface` 🔵
Search models, datasets, run inference on Hugging Face directly.

---

## 📜 License

MIT.

---

<div align="center">

**Star ⭐ to follow the MCP marketplace.**

</div>
