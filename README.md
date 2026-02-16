# OpenClaw Local-Only Setup

## Overview

This is a modified version of the [Agent Flywheel Clawdbot Skills & Integrations](https://github.com/Dicklesworthstone/agent_flywheel_clawdbot_skills_and_integrations) repository, specifically tailored for **local-only execution** without requiring any VPS or cloud infrastructure.

## Key Differences from Original

- **No VPS Requirements**: All tools run locally on your machine
- **Local-First Design**: Removed cloud deployment references
- **Simplified Setup**: Stripped down to essentials for local development
- **No Cloud CLIs Required**: Focus on local development tools (git, ssh, cursors, terminal multiplexers)

## What's Included

Clawdbot skills for agentic coding workflows with tools for:

- **Local Agentic Tools**: ntm, agent-mail, bv, cass, cm, slb
- **Workflow Methodologies**: Planning, beads, agent-swarm workflows
- **Local Development**: github, ssh, cursor, ghostty, wezterm
- **Browser Automation**: Claude in Chrome
- **Media Tools**: Image handling, file conversions

## Quick Setup

### One-Line Install

```bash
curl -fsSL "https://raw.githubusercontent.com/papabrosio/openclaw-local-only/main/install.sh?v=$(date +%s)" | bash -s -- --all
```

### Manual Install

```bash
# Clone the repository
git clone https://github.com/papabrosio/openclaw-local-only.git ~/.openclaw-skills
cd ~/.openclaw-skills

# Run the installer
./install.sh --all
```

## Prerequisites

### Required
- `bash` or `sh`
- `git`
- `curl` or similar download tool

### Optional (for specific skills)
- **Terminal Multiplexers**: ghostty, wezterm
- **Browser**: Chrome/Chromium (for claude-chrome skill)
- **Dev Tools**: GitHub CLI (gh), Cursor editor

## Local Skills Available

### Agentic Coding Stack
- `ntm` - Named Tmux Manager
- `agent-mail` - MCP Agent Mail coordination
- `bv` - Beads Viewer task triage
- `cass` - Coding Agent Session Search
- `cm` - CASS Memory System
- `slb` - Simultaneous Launch Button (two-person rule)

### Workflow Methodologies
- `planning-workflow` - Planning methodology
- `beads-workflow` - Task structure conversion
- `agent-swarm-workflow` - Multi-agent coordination
- `agent-fungibility` - Agent philosophy
- `ui-ux-polish` - Iterative UI improvement
- `de-slopify` - Remove AI writing artifacts

### Development Tools
- `github` - GitHub CLI integration
- `ssh` - SSH patterns and tunneling
- `cursor` - Cursor AI editor control
- `ghostty` - Ghostty terminal emulator
- `wezterm` - WezTerm terminal multiplexer

### Utilities
- `claude-chrome` - Browser automation
- `giil` - Image handling
- `csctf` - Chat transcripts to files

## Installation Options

```bash
# Interactive selection menu
curl ... | bash

# Install all skills
curl ... | bash -s -- --all

# Install to custom directory
curl ... | bash -s -- --dest ~/my-skills

# List available skills
curl ... | bash -s -- --list

# Uninstall all skills
curl ... | bash -s -- --uninstall
```

## Configuration

After installation, enable skills in your `clawdbot.json`:

```json
{
  "skills": {
    "entries": {
      "ntm": { "enabled": true },
      "github": { "enabled": true },
      "ssh": { "enabled": true },
      "cursor": { "enabled": true }
    }
  }
}
```

## Usage Examples

```bash
# Via CLI
clawdbot agent --message "Start a tmux session for the API project"
clawdbot agent --message "Create a PR from this branch"
clawdbot agent --message "SSH to the server and check logs"

# Via WhatsApp/Telegram/iMessage
"Start a 3-agent session for the API refactor"
"Deploy to production"
"Check GitHub Actions status"
```

## Skill Anatomy

Each skill is a markdown file with YAML frontmatter:

```yaml
---
name: my-tool
description: Brief description of what the tool does
---

# My Tool Skill

Explanation and common commands...
```

## Contributing

### Adding a New Skill

1. Create `skills/skill-name/SKILL.md`
2. Include YAML frontmatter with `name` and `description`
3. Document commands and workflows
4. Update this README
5. Submit a PR

## Local-Only Design Philosophy

This fork prioritizes:
- **Privacy**: All data stays on your machine
- **Offline**: Works without internet connectivity
- **Simplicity**: Minimal dependencies
- **Control**: Full control over your environment

## Troubleshooting

### Skills Not Found

Ensure skills are installed to the correct directory:
- Default: `~/.clawdbot/skills`
- Alternative: `~/.openclaw/skills`
- Custom: Specify with `--dest`

### Permission Errors

Make sure the installer is executable:
```bash
chmod +x install.sh
```

## Related Projects

- **Original**: [Agent Flywheel Clawdbot Skills](https://github.com/Dicklesworthstone/agent_flywheel_clawdbot_skills_and_integrations)
- **Clawdbot**: [Clawdbot by Peter Steinberger](https://github.com/steipete/clawdbot)
- **ACFS**: [Agentic Coding Flywheel Setup](https://github.com/Dicklesworthstone/agentic_coding_flywheel_setup)

## License

MIT License - See LICENSE file for details.

## Credits

Based on the excellent work of [Dicklesworthstone's Agent Flywheel Project](https://github.com/Dicklesworthstone/agent_flywheel_clawdbot_skills_and_integrations), modified for local-only execution.
