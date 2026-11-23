# RemAgent Plugin for Google Antigravity

**Free and open source** local SQLite memory for Google Antigravity, powered by [RemAgent](https://github.com/Johnv412/remagent).

Website, privacy policy and terms: https://dreamengine.dev

This plugin is a lightweight "power cord": it contains no backend code of its own, connects to no hosted server of ours, and requires no plugin API key. It launches RemAgent's local MCP server directly on your machine via `uvx`.

---

## Install (One Line)

Requires [`uv`](https://docs.astral.sh/uv/) (`uvx`) on your machine (if you don't have it yet: `brew install uv` or `curl -LsSf https://astral.sh/uv/install.sh | sh`).

Install the plugin in Antigravity with one command:

```bash
agy plugin install https://github.com/Johnv412/remagent-plugin
```

No `pip install`, no virtual environment setup, and no API key prompt needed to start recalling and logging locally.

---

## Tools Provided

Once enabled, Antigravity gets three local MCP tools from `remagent-mcp`:

- **`remagent_recall`** — Recalls active consolidated entity facts and operational rules within a token budget.
- **`remagent_log`** — Appends an interaction turn to your local episodic memory buffer.
- **`remagent_dream`** — Runs a REM consolidation pass to prune noise, extract facts, and resolve contradictions.

---

## What It Stores and Where

- **What is stored:** Raw logged turns, consolidated entity–attribute facts, operational rules, and consolidation audit rows.
- **Where it is stored:** In a single local SQLite file inside Antigravity's per-plugin data folder: `${PLUGIN_DATA}/memory.db` (outside your git repositories, owned solely by you).
- **Network behavior:** `remagent_recall` and `remagent_log` stay 100% local on your machine. Only `remagent_dream` (when you explicitly trigger consolidation) calls your chosen LLM provider if you have exported one of `GEMINI_API_KEY`, `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, or `XAI_API_KEY`.

---

## License

This plugin is **free and open source** under the [MIT License](./LICENSE). The underlying [RemAgent](https://github.com/Johnv412/remagent) package is open source under the Apache-2.0 License.
