# Skills

## Add skills to the agent

```bash
npx skills add https://github.com/pzyyll/ai-agents --skill daisyui [skills...]
# Specify agents to install to (use '*' for all agents)
npx skills add https://github.com/pzyyll/ai-agents --skill daisyui [skills...] --agent claude-code [agents...]
```

### Installed on agent:

- opencode
- codex
- gemini-cli
- github-copilot
- amp
- claude-code

## About `skills` command

```
Usage: skills <command> [options]

Commands:
  add <package>     Add a skill package
                    e.g. vercel-labs/agent-skills
                         https://github.com/vercel-labs/agent-skills
  remove [skills]   Remove installed skills
  list, ls          List installed skills
  find [query]      Search for skills interactively
  init [name]       Initialize a skill (creates <name>/SKILL.md or ./SKILL.md)
  check             Check for available skill updates
  update            Update all skills to latest versions

Add Options:
  -g, --global           Install skill globally (user-level) instead of project-level
  -a, --agent <agents>   Specify agents to install to (use '*' for all agents)
  -s, --skill <skills>   Specify skill names to install (use '*' for all skills)
  -l, --list             List available skills in the repository without installing
  -y, --yes              Skip confirmation prompts
  --all                  Shorthand for --skill '*' --agent '*' -y
  --full-depth           Search all subdirectories even when a root SKILL.md exists

Remove Options:
  -g, --global           Remove from global scope
  -a, --agent <agents>   Remove from specific agents (use '*' for all agents)
  -s, --skill <skills>   Specify skills to remove (use '*' for all skills)
  -y, --yes              Skip confirmation prompts
  --all                  Shorthand for --skill '*' --agent '*' -y

List Options:
  -g, --global           List global skills (default: project)
  -a, --agent <agents>   Filter by specific agents

Options:
  --help, -h        Show this help message
  --version, -v     Show version number

Examples:
  $ skills add vercel-labs/agent-skills
  $ skills add vercel-labs/agent-skills -g
  $ skills add vercel-labs/agent-skills --agent claude-code cursor
  $ skills add vercel-labs/agent-skills --skill pr-review commit
  $ skills remove                   # interactive remove
  $ skills remove web-design        # remove by name
  $ skills rm --global frontend-design
  $ skills list                     # list all installed skills
  $ skills ls -g                    # list global skills only
  $ skills ls -a claude-code        # filter by agent
  $ skills find                     # interactive search
  $ skills find typescript          # search by keyword
  $ skills init my-skill
  $ skills check
  $ skills update

Discover more skills at https://skills.sh/
```
