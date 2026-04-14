# GitHub Copilot Agent Plugin

A production-ready collection of GitHub Copilot agent customizations for code review, documentation generation, refactoring, and development best practices.

## What is an Agent Plugin?

An Agent Plugin is a packaged collection of GitHub Copilot customizations that extend Copilot's capabilities with specialized skills, custom agents, and workflow automations. Install this plugin to add powerful code review, documentation, and refactoring capabilities to your project.

## 🚀 Features

### 🔍 Code Review Skill
Comprehensive automated code reviews covering:
- Security vulnerability scanning
- Code quality assessment
- Performance analysis
- Best practices validation
- Detailed review reports

**Usage**: `/code-review <files>` or "Review this PR with code-review standards"

### 📝 Documentation Writer Agent
Specialized agent for creating and maintaining documentation:
- README generation
- API documentation from code
- Architecture overviews
- Contributing guides
- User documentation

**Usage**: `@doc-writer Generate documentation for this project`

### 🔧 Refactor Prompt
Single-command code refactoring:
- Extract methods and variables
- Simplify conditionals
- Remove code duplication
- Improve readability
- Modernize code patterns

**Usage**: `/refactor <file>` or "Refactor this code for better readability"

### 🐍 Python Standards
Automatic Python best practices enforcement:
- PEP 8 compliance
- Type hints
- Modern Python features
- Testing patterns
- Documentation standards

**Applies to**: All `.py` files automatically

## 📦 Installation

### Option 1: Clone into Project
```bash
git clone https://github.com/djredman99-org/github-agentic-workflows .copilot-plugin
cp -r .copilot-plugin/.github/* .github/
```

### Option 2: npm Package (Recommended)
```bash
npm install @djredman99-org/github-copilot-agent-plugin
cp -r node_modules/@djredman99-org/github-copilot-agent-plugin/.github/* .github/
```

### Option 3: GitHub Template
1. Click "Use this template" on GitHub
2. Create your repository
3. The customizations are already included

## 📖 What's Included

### Skills (`.github/skills/`)
- **code-review**: Automated code review with security, quality, and performance checks
  - Supporting files: security checklist, quality standards, review template

### Custom Agents (`.github/agents/`)
- **doc-writer**: Documentation generation with read-only access and structured output

### Instructions (`.github/instructions/`)
- **python-standards**: Automatic Python best practices for all `.py` files

### Prompts (`.github/prompts/`)
- **refactor**: Single-task code refactoring with guided improvements

### Workspace Instructions (`.github/copilot-instructions.md`)
- Plugin development standards and guidelines

## 🎯 How to Use

### Using Skills
Type `/` in Copilot chat to see available skills, then:
```
/code-review src/api/users.ts
```

### Using Custom Agents
Mention the agent with `@`:
```
@doc-writer Create API documentation for the auth module
```

### Using Prompts
Type `/` and select the prompt:
```
/refactor src/utils/helpers.js - focus on extracting functions
```

### Automatic Instructions
Python standards apply automatically when working with `.py` files - no action needed!

## 🛠️ Customization

All customizations are editable. Modify files in `.github/` to adapt to your needs:

- **Add new skills**: Create `.github/skills/<name>/SKILL.md`
- **Create custom agents**: Add `.github/agents/<name>.agent.md`
- **Add file-specific rules**: Create `.github/instructions/<name>.instructions.md`
- **Add quick tasks**: Create `.github/prompts/<name>.prompt.md`

See [.github/copilot-instructions.md](.github/copilot-instructions.md) for development guidelines.

## 📁 Plugin Structure

```
.github/
├── copilot-instructions.md           # Workspace-level guidelines
├── agents/
│   └── doc-writer.agent.md          # Documentation generator agent
├── skills/
│   └── code-review/
│       ├── SKILL.md                 # Main skill definition
│       ├── references/              # Supporting documentation
│       │   ├── security-checklist.md
│       │   └── quality-standards.md
│       └── assets/
│           └── review-template.md   # Review report template
├── instructions/
│   └── python-standards.instructions.md  # Python best practices
└── prompts/
    └── refactor.prompt.md           # Refactoring prompt
```

## 🧪 Testing the Plugin

After installation, verify the plugin works:

1. **Test skill loading**: Type `/code` in Copilot chat - you should see `/code-review`
2. **Test agent**: Type `@doc` - you should see `@doc-writer`
3. **Test prompt**: Type `/ref` - you should see `/refactor`
4. **Test instructions**: Open a `.py` file - Python standards apply automatically

## 📝 Contributing

Contributions welcome! When adding customizations:

1. Follow the structure in [.github/copilot-instructions.md](.github/copilot-instructions.md)
2. Test thoroughly before submitting
3. Include clear descriptions with keywords
4. Add supporting documentation in subdirectories
5. Update this README with new features

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details

## 🔗 Links

- [VS Code Agent Customization Docs](https://code.visualstudio.com/docs/copilot/customization)
- [Creating Agent Skills](https://code.visualstudio.com/docs/copilot/customization/agent-skills)
- [Custom Instructions Guide](https://code.visualstudio.com/docs/copilot/customization/custom-instructions)

## ⚡ Quick Start Example

```bash
# Install the plugin
npm install @djredman99-org/github-copilot-agent-plugin
cp -r node_modules/@djredman99-org/github-copilot-agent-plugin/.github/* .github/

# Open VS Code
code .

# Try it out in Copilot Chat:
# - "/code-review src/" - Review your code
# - "@doc-writer Generate README" - Create documentation
# - "/refactor app.py" - Refactor code
```

## 🆘 Support

Issues? Questions? 
- [Open an issue](https://github.com/djredman99-org/github-agentic-workflows/issues)
- Check [VS Code Copilot docs](https://code.visualstudio.com/docs/copilot)

---

**Made with ❤️ for the GitHub Copilot community**
