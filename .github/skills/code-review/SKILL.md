---
name: code-review
description: 'Perform structured code reviews with security, performance, and maintainability checks. Use when: reviewing pull requests, auditing code quality, checking best practices, finding bugs.'
argument-hint: 'File paths or PR number to review'
---

# Code Review Skill

Performs comprehensive code reviews following industry best practices.

## When to Use

- Reviewing pull requests before merge
- Conducting code quality audits
- Identifying security vulnerabilities
- Checking performance issues
- Verifying coding standards compliance

## Review Process

### Phase 1: Discovery (Understanding the Change)

1. **Identify scope**: Determine which files are modified
2. **Understand intent**: Read commit messages and PR description
3. **Map dependencies**: Identify affected modules and components

### Phase 2: Security Analysis

Review code for common security issues:

- **Input validation**: Check all user inputs are validated
- **Authentication/Authorization**: Verify proper access controls
- **SQL Injection**: Look for unsafe database queries
- **XSS vulnerabilities**: Check for unescaped output
- **Sensitive data exposure**: Ensure secrets aren't hardcoded
- **Dependency vulnerabilities**: Check for known CVEs

Reference: [Security Checklist](./references/security-checklist.md)

### Phase 3: Code Quality

Assess maintainability and readability:

- **Naming conventions**: Clear, descriptive names
- **Function complexity**: Functions should do one thing well
- **Code duplication**: DRY principle violations
- **Error handling**: Proper exception management
- **Documentation**: Comments where needed, not obvious code
- **Test coverage**: Adequate unit and integration tests

Reference: [Quality Standards](./references/quality-standards.md)

### Phase 4: Performance

Check for performance issues:

- **N+1 queries**: Database query optimization
- **Memory leaks**: Proper resource cleanup
- **Algorithmic complexity**: Efficient algorithms (O(n) vs O(n²))
- **Caching opportunities**: Identify cacheable operations
- **Lazy loading**: Defer expensive operations

### Phase 5: Generate Report

Create a structured review using the [review template](./assets/review-template.md):

1. **Summary**: High-level assessment
2. **Critical issues**: Must fix before merge
3. **Suggestions**: Nice-to-have improvements
4. **Positive highlights**: What was done well
5. **Risk assessment**: Low/Medium/High

## Output Format

```markdown
## Code Review Summary

**Overall Assessment**: ✅ Approve / ⚠️ Approve with changes / ❌ Request changes

**Files Reviewed**: X files, Y lines changed

### Critical Issues
- [ ] Issue 1 with file reference and line numbers
- [ ] Issue 2 with suggested fix

### Suggestions
- Suggestion 1
- Suggestion 2

### Positive Highlights
- What was done well

### Risk Level: [Low/Medium/High]
```

## Customization

Users can customize the review by:
- Adding language-specific rules to `references/`
- Modifying security checklist items
- Adjusting quality thresholds
- Creating custom review templates

## Example Usage

```
/code-review src/api/users.ts src/api/auth.ts
```

or

```
Review the changes in PR #123 using code-review standards
```
