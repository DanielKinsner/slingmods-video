# MCP + Tooling Setup (per machine)

What the pipeline needs installed on a machine before Claude can edit there.
Office PC: done 2026-07-30. Home PC / MacBook: not yet.

## Prerequisites
- **Node.js 18+** (office has v24) — needed by both the Premiere MCP and HyperFrames
- **Python 3.10–3.13** (office has 3.13.5) — needed by the Resolve MCP
- **FFmpeg** on PATH — frame sampling, analysis, HyperFrames rendering
- **git** + GitHub credentials (GitHub Desktop login is enough)
- Adobe Premiere Pro 2020+ and/or DaVinci Resolve **Studio** (free edition can't do external scripting)

## 1. Premiere Pro MCP — hetpatel-11/Adobe_Premiere_Pro_MCP
```
git clone https://github.com/hetpatel-11/Adobe_Premiere_Pro_MCP.git
cd Adobe_Premiere_Pro_MCP
npm run setup:win        # macOS: npm run setup:mac
```
Then register with Claude Code (adjust paths to where you cloned):
```
claude mcp add --scope user premiere-pro -e "PREMIERE_TEMP_DIR=<TEMP>\premiere-mcp-bridge" -- node "<clone-path>\dist\index.js"
```
(Windows TEMP is `%TEMP%\premiere-mcp-bridge`; the installer prints the exact values at the end.)

**One-time in Premiere:** open any project → Window → Extensions → MCP Bridge (CEP) → set the temp
directory the installer printed → Save Configuration → **Start Bridge** (needed after every Premiere launch).

## 2. DaVinci Resolve MCP — samuelgursky/davinci-resolve-mcp
```
npx -y davinci-resolve-mcp setup --clients claude-code
```
**Known gotcha (hit on office PC):** its venv may install MCP SDK 2.x, which breaks the server
(`No module named 'mcp.server.fastmcp'`). Fix:
```
<install-dir>\venv\Scripts\python.exe -m pip install "mcp[cli]<2"
```
(install dir: `%LOCALAPPDATA%\davinci-resolve-mcp`). Also: the installer writes a *project-scoped*
.mcp.json in its own folder — register user-scope instead with `claude mcp add --scope user davinci-resolve ...`
using the command/args/env from that .mcp.json.

**One-time in Resolve:** Preferences → General → External scripting using → **Local**. Resolve must be
running with a project open for the tools to work.

## 3. HyperFrames skills
```
npx -y skills add heygen-com/hyperframes --full-depth
```

## 4. SlingMods skills (this repo)
Copy each folder in `skills/` to `~/.claude/skills/`.

## 5. Verify
```
claude mcp list      # premiere-pro and davinci-resolve should both show Connected
```
(Resolve shows connected only when Resolve is running. Restart the Claude session after adding MCPs.)

## Office-PC-specific things that DON'T transfer
- Drive layout: `M:` (Dan's projects), `E:\claude\` (Claude workspace), `M:\_template`. Home machines
  need their own equivalents — decide drive roles there before the first project, per WORKFLOW-RULES.md.
- Keep `yt-dlp` current (`pip install -U yt-dlp`) if doing channel research — stale versions fail.
