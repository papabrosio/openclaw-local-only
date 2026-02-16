# Local OpenClaw Setup Guide

## Quick Start

This repository provides a local-only version of the Clawdbot skills configured to run entirely on your machine without requiring VPS or cloud infrastructure.

### Clone This Repository

```bash
# Clone the repository
git clone https://github.com/papabrosio/openclaw-local-only.git
cd openclaw-local-only

# Option 1: Install all skills from this repo
./install.sh --all

# Option 2: Interactive selection
./install.sh

# Option 3: Install to custom location
./install.sh --dest ~/.openclaw-skills
```

## Getting the Full Skill Library

The original repository with all skills is available here:
- **Original Repo**: https://github.com/Dicklesworthstone/agent_flywheel_clawdbot_skills_and_integrations

To get all the skills from the original:

```bash
# Clone the original repository
git clone https://github.com/Dicklesworthstone/agent_flywheel_clawdbot_skills_and_integrations.git

# Copy skills folder to your location
cp -r agent_flywheel_clawdbot_skills_and_integrations/skills ~/.openclaw-skills/
```

## Configuring Clawdbot

After installing skills, enable them in your Clawdbot configuration (`~/.clawdbot/clawdbot.json` or `~/clawd/config/clawdbot.json`):

```json
{
  "skills": {
    "entries": {
      "ntm": { "enabled": true },
      "github": { "enabled": true },
      "ssh": { "enabled": true },
      "cursor": { "enabled": true },
      "ghostty": { "enabled": true },
      "wezterm": { "enabled": true },
      "claude-chrome": { "enabled": true }
    }
  }
}
```

## Local-Only Tools You Can Use

### Terminal & Development
- **ntm** (Named Tmux Manager) - Orchestrate multiple agents in tmux panes
- **github** - GitHub CLI for repository management
- **ssh** - SSH tunneling and configuration
- **cursor** - Cursor AI editor integration
- **ghostty** - Ghostty terminal emulator
- **wezterm** - WezTerm terminal multiplexer

### Local Agentic Stack
- **agent-mail** - MCP coordination between local agents
- **bv** (Beads Viewer) - Local task graph visualization
- **cass** (Coding Agent Session Search) - Search local agent history
- **cm** (CASS Memory) - Local procedural memory for agents
- **slb** (Simultaneous Launch Button) - Two-person rule for local commands

### Utilities
- **claude-chrome** - Local browser automation
- **giil** - Local image handling
- **csctf** - Convert chat transcripts to files

## What NOT to Use (Removed VPS/Cloud)

The following skills from the original have been excluded as they require cloud infrastructure:
- **gcloud** (Google Cloud Platform)
- **wrangler** (Cloudflare Workers)
- **vercel** (Vercel deployments)
- **supabase** (Supabase database)

If you need these, use the original repository.

## Troubleshooting

### Command Not Found

If skills aren't found, ensure they're in the right directory:

```bash
# Check where skills are installed
find ~ -name "skills" -type d 2>/dev/null

# Re-run installer with explicit path
./install.sh --dest ~/.openclaw-skills
```

### Permission Issues

```bash
# Make installer executable
chmod +x install.sh

# Ensure skills directory is readable
chmod -R +rx ~/.openclaw-skills
```

### Testing Skills

```bash
# List installed skills
./install.sh --list

# Check Clawdbot can see skills
clawdbot agent --message "list available skills"
```

## Development Workflow

With local-only setup, you can:

1. **Run multiple agents locally**:
   ```bash
   ntm start 3
   ```

2. **Coordinate with agent-mail**:
   ```bash
   clawdbot agent --message "check mailbox for reservations"
   ```

3. **Search agent history**:
   ```bash
   cass search "authentication"
   ```

4. **Manage session memory**:
   ```bash
   cm recall patterns
   ```

## Getting Started

1. Install Clawdbot if you haven't already
2. Clone this repository
3. Run the installer: `./install.sh --all`
4. Configure your `clawdbot.json`
5. Restart Clawdbot
6. Start using the local-only skills!

## Next Steps

- Explore the README.md for detailed skill documentation
- Check out the original project: https://github.com/Dicklesworthstone/agent_flywheel_clawdbot_skills_and_integrations
- Join the Clawdbot community: https://github.com/steipete/clawdbot

## Support

For issues with:
- **This repository**: File an issue
- **Original skills**: See the original repo
- **Clawdbot**: See the Clawdbot repository
