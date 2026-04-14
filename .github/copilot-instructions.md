# Agent Plugin Development Guidelines

This repository contains reusable Copilot agent customizations packaged as an installable plugin.

## Purpose

Provide high-quality, production-ready agent customizations that teams can adopt for:
- Code review automation
- Documentation generation
- Code refactoring assistance
- Language-specific best practices

## Code Standards

### Documentation Quality
- Every customization file must have a clear, keyword-rich `description`
- Include concrete "use when" examples in descriptions
- Show expected inputs and outputs
- Link to supporting references rather than duplicating content

### File Organization
- Skills go in `.github/skills/<name>/SKILL.md`
- Always create supporting files in subdirectories: `references/`, `scripts/`, `assets/`
- Custom agents in `.github/agents/*.agent.md`
- Instructions in `.github/instructions/*.instructions.md`
- Prompts in `.github/prompts/*.prompt.md`

### Naming Conventions
- Use kebab-case for all file and folder names
- Match folder name exactly with YAML `name:` field in skills
- Descriptive names that indicate purpose: `code-review`, `doc-writer`, `python-standards`

### YAML Frontmatter
- Always quote description fields containing colons
- Use 2-space indentation (no tabs)
- Include all required fields for the file type
- Validate YAML syntax before committing

## Testing Customizations

Before publishing:
1. Test each customization in a real project
2. Verify descriptions trigger correct loading
3. Check that applyTo patterns work as expected
4. Ensure all file references resolve correctly
5. Validate tool restrictions on custom agents

## Publishing

This plugin is distributed via:
- npm package: Users run `npm install` to get customizations
- Direct clone: Users copy `.github/` directory
- GitHub template: Users create repo from template

## Version Control

- Follow semantic versioning (MAJOR.MINOR.PATCH)
- Update CHANGELOG.md for all releases
- Tag releases in git
- Keep package.json version in sync

## Dependencies

This plugin should:
- Have minimal external dependencies
- Work across different project types
- Not require specific frameworks or tools
- Provide graceful fallbacks when tools unavailable

## Quality Standards

All customizations must:
- ✅ Have clear, discoverable descriptions
- ✅ Include usage examples
- ✅ Follow established patterns
- ✅ Be well-documented
- ✅ Handle edge cases gracefully
- ✅ Not assume specific project structure

## Contributing

When adding new customizations:
1. Check existing patterns first
2. Avoid duplication - extend existing rather than creating new
3. Use established file organization
4. Test thoroughly
5. Document clearly
6. Consider the end user experience
