# 🛡️ CyberGuard AI — Personal SOC Assistant

A personal AI assistant built for cybersecurity analyst workflows. Powered by Claude (Anthropic), hosted on GitHub Pages. No backend, no rate limits, no subscription — just your API key and your browser.

## Features

- **5 specialist modes** — General analyst, Vulnerability management, Threat hunting (KQL), Risk assessment, GRC
- **KQL generation** for both Microsoft Sentinel and Microsoft Defender XDR
- **CVE triage** with CVSS scoring and patch prioritization
- **Risk assessments** aligned to NIST CSF 2.0, ISO 27001:2022, and CIS Controls v8
- **GRC support** — policy writing, control mapping, audit prep
- **Streaming responses** — answers appear word by word, no waiting
- **One-click copy** on all KQL/code blocks
- **MITRE ATT&CK** technique references baked into every hunt response
- **Severity badges** — CRITICAL / HIGH / MEDIUM / LOW auto-highlighted

## Setup

1. Clone or fork this repo
2. Enable GitHub Pages: **Settings → Pages → Branch: main**
3. Get an [Anthropic API key](https://console.anthropic.com)
4. Open your GitHub Pages URL, paste your API key in the sidebar, click Save
5. Start hunting

## Adding your ChatGPT knowledge base

Once you receive your ChatGPT export:

1. Run `scripts/parse_chatgpt.py` on your `conversations.json`
2. The output `knowledge_base.txt` contains your past KQL queries and analyst work
3. Paste relevant sections into the system prompt inside `index.html` under your chosen mode

## Runbooks

Drop markdown files into `/runbooks/` — these become reference material you can paste into conversations:

- `vuln_triage.md` — your CVE triage process
- `threat_hunt_checklist.md` — hunt hypotheses and data sources  
- `risk_assessment_template.md` — your risk scoring criteria
- `governance_controls.md` — control framework mappings

## Cost

claude-sonnet-4-6 costs roughly $0.003 per 1K input tokens and $0.015 per 1K output tokens. A typical analyst session (10–15 exchanges) costs under $0.10.

## Stack

- Pure HTML/CSS/JS — no framework, no build step, no dependencies
- Anthropic Messages API with streaming
- GitHub Pages for hosting (free)
- localStorage for API key persistence

---

Built by [Subash Ghimire](https://github.com/SubashGhimire)
