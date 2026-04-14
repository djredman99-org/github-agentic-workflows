# Plugin Manifest

This directory contains the VS Code plugin manifest that enables installation through the Copilot Chat UI.

## How it works

When you add this repository through:
**Copilot Chat Settings → Agent Customizations → Plugins → Add from Repository**

VS Code reads `plugin.json` to:
1. Display plugin information
2. Locate customization files (agents, skills, instructions, prompts)
3. Install them into your workspace

## Structure

```json
{
  "contributes": {
    "agents": [...],      // Custom agents (.agent.md)
    "skills": [...],      // Skills (SKILL.md)
    "instructions": [...], // Instructions (.instructions.md)
    "prompts": [...]      // Prompts (.prompt.md)
  }
}
```

All customization files are located in `.github/` directory as per standard conventions.
