# Claude Code Configuration

Personal configuration repository for Claude Code settings, commands, agents, and integrations.

## What's in This Repo?

This repository contains my Claude Code customizations to maintain consistency across machines and preserve configurations:

- **Memory Files** (`CLAUDE.md`) - Personal preferences and communication style
- **Slash Commands** (`.claude/commands/`) - Reusable prompt templates
- **Agents** (`.claude/agents/`) - Specialized AI assistants for specific tasks
- **Hooks** (`settings.json`) - Automated workflows and validations
- **MCP Server Configurations** - Integrations with external tools and services

## Repository Structure

```
.
├── README.md
├── {user}/                       # User-level configs (~/.claude/)
│   ├── CLAUDE.md               # Personal memory/preferences
│   ├── commands/               # Personal slash commands
│   │   ├── review.md
│   │   └── optimize.md
│   ├── agents/                 # Personal agents
│   │   ├── code-reviewer.md
│   │   └── debugger.md
│   └── settings.json           # User-level settings & hooks
├── project-templates/          # Templates for project-specific configs
│   └── example/
│       ├── CLAUDE.md           # Project memory template
│       └── .claude/
│           ├── commands/       # Project slash commands
│           └── settings.json   # Project-level settings
└── mcp/                        # MCP server configurations
    └── mcp-servers.json        # Backup of MCP configurations
```

## Setup on a New Machine

### 1. Install Claude Code
Follow the [official installation guide](https://code.claude.com/docs/en/overview).

### 2. Clone This Repository
```bash
git clone git@github.com:antonsamper/claude-code-config.git
cd claude-code-config
```

### 3. Restore User-Level Configurations
```bash
# Copy user memory
cp {user}/CLAUDE.md ~/.claude/

# Copy user commands
mkdir -p ~/.claude/commands
cp -r {user}/commands/* ~/.claude/commands/

# Copy user agents
mkdir -p ~/.claude/agents
cp -r {user}/agents/* ~/.claude/agents/

# Copy user settings (hooks, etc.)
cp {user}/settings.json ~/.claude/settings.json
```

### 4. Restore MCP Servers (if applicable)
```bash
# Review and add MCP servers from mcp/mcp-servers.json
# Add each server using: claude mcp add ...
```

## What Each Component Does

### Memory (CLAUDE.md)
Persistent knowledge Claude always sees:
- Communication preferences (conciseness, tone)
- Coding standards and conventions
- Personal workflow preferences

### Slash Commands
Quick prompts invoked with `/command-name`:
- `/review` - Code review checklist
- `/optimize` - Performance analysis
- Custom workflows you use frequently

### Agents (Subagents)
Specialized AI assistants with dedicated context:
- `code-reviewer` - Security and quality focused reviews
- `debugger` - Root cause analysis and fixes
- `data-scientist` - SQL queries and data analysis

### Hooks
Automated actions triggered by events:
- Validation before tool use
- Formatting after file edits
- Notifications and logging

### MCP Servers
Integrations with external tools:
- GitHub (pull requests, issues)
- Databases (PostgreSQL, etc.)
- Monitoring tools (Sentry)
- Communication (Slack)

## Backup Workflow

Regularly backup your configurations:

```bash
# From your home directory
cd ~/path/to/claude-code-config

# Update user configs
cp ~/.claude/CLAUDE.md {user}/
cp -r ~/.claude/commands/* {user}/commands/
cp -r ~/.claude/agents/* {user}/agents/
cp ~/.claude/settings.json {user}/

# Export MCP server list
claude mcp list > mcp/mcp-servers.txt

# Commit and push
git add .
git commit -m "Update configurations"
git push
```

## Tips

- **Keep sensitive data out**: Use `.gitignore` for API keys and secrets
- **CLAUDE.local.md**: For machine-specific preferences (not in repo)
- **Test before committing**: Ensure configs work before pushing
- **Document custom commands**: Add comments in slash command files

## Resources

- [Claude Code Documentation](https://code.claude.com/docs)
- [MCP Protocol](https://modelcontextprotocol.io/)
- [Memory Management](https://code.claude.com/docs/en/memory)
- [Hooks Guide](https://code.claude.com/docs/en/hooks-guide)
- [Agents Documentation](https://code.claude.com/docs/en/sub-agents)

---

**Note**: This repo stores personal Claude Code configurations. Review and customize to match your own preferences and workflow.
