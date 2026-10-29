# Ditto

Your [Ditto](https://heyditto.ai) memory, inside your agent. This plugin connects
Cursor and Grok Bot to Ditto's hosted MCP server so the agent can recall what you
have already told Ditto (people, projects, preferences and past decisions) and
save new decisions and facts as you work.

- **Search and fetch memories.** Find memories by meaning, then pull the full text
  of the ones that matter.
- **Explore your knowledge graph.** Look up people and projects as subjects, search
  within a subject, and follow related memories.
- **Save and update memories.** Record durable decisions, facts and next steps, and
  correct an existing memory instead of duplicating it.
- **Hand off a chat.** Save a verified continuation note to Ditto before closing out
  a chat, so the next session can pick up where this one left off.

The plugin is free. Ditto itself has a free allowance; see
[heyditto.ai](https://heyditto.ai) for plans.

## What's included

| Component | Path | Purpose |
| --- | --- | --- |
| MCP server | `mcp.json` | Ditto's hosted server at `https://api.heyditto.ai/mcp` (Streamable HTTP, OAuth) |
| Skill | `skills/ditto-memory/` | How to recall Ditto context and capture durable facts with the user's permission |
| Skill | `skills/handoff/` | Save a verified continuation note to Ditto before closing out authorized chats |

No hooks, CLI helpers, scripts or local binaries are installed.

## Install

Install **Ditto** from the plugin marketplace in Cursor or Grok Bot.

To try it locally before it is listed, clone this repository and load the folder
as a local plugin in Cursor.

## Sign in

Ditto uses OAuth, so there is nothing to configure and no API key to paste. The
first time the agent calls a Ditto tool, your client opens a browser sign-in for
your Ditto account. Approve access and you're connected. You can revoke access
at any time from your Ditto account.

Don't have an account? Sign up free at [heyditto.ai](https://heyditto.ai).

## Tools

MCP clients discover Ditto's tools automatically, and the live server is the
source of truth. The core memory tools are:

| Tool | What it does |
| --- | --- |
| `search_memories` | Find memories by meaning; returns short previews with sources |
| `fetch_memories` | Get the full text of memories by ID |
| `save_memory` | Save a decision, fact or next step |
| `update_memory` | Correct a saved memory in place |
| `search_subjects` | Look up people and projects in your knowledge graph |
| `search_memories_in_subjects` | Search memories about one subject |
| `get_memory_network` | Follow related memories |
| `list_memories` | List what your agents saved |

## Try it

- "What do you remember about Project Cedar?"
- "Save that we chose Postgres for the billing service, and why."
- "Who have I talked to about the launch plan?"
- "/handoff: save where we are so I can pick this up tomorrow."

## Privacy and data

The plugin only talks to `https://api.heyditto.ai/mcp`. Memories enter the agent's
context only when it calls a Ditto tool; nothing is saved automatically, and the
skills tell the agent to skip secrets and credentials. Ditto never trains models
on your memories.

- Privacy policy: https://heyditto.ai/privacy
- Terms of service: https://heyditto.ai/terms
- Support: https://heyditto.ai/contact · support@heyditto.ai

## License

MIT. See [LICENSE](LICENSE).
