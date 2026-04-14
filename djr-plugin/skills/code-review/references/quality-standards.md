# Code Quality Standards

## Naming Conventions

### Variables
- Use descriptive names that reveal intent
- Boolean variables should be questions: `isActive`, `hasPermission`
- Avoid single-letter names except in loops
- Constants in UPPER_SNAKE_CASE

### Functions
- Verb-based names: `getUserById`, `calculateTotal`
- One clear purpose per function
- Max parameters: 3-4 (use objects for more)
- Max lines: 50 (refactor if larger)

### Classes
- Noun-based names representing entities
- Single responsibility principle
- Clear inheritance hierarchy

## Function Complexity

### Cyclomatic Complexity
- Target: < 10 per function
- Max acceptable: 15
- Refactor if > 15

### Nesting Depth
- Max nesting: 3 levels
- Use early returns to reduce nesting
- Extract complex conditions to named variables

## Code Duplication (DRY)

- No copy-paste code (extract to function/module)
- Similar logic should be abstracted
- Configuration over duplication
- Use inheritance/composition appropriately

## Error Handling

### Required
- Try-catch blocks around risky operations
- Specific exceptions over generic ones
- Always clean up resources (finally blocks)
- Log errors with context

### Avoid
- Empty catch blocks
- Catching and ignoring errors
- Generic error messages
- Swallowing exceptions

## Comments & Documentation

### When to Comment
- Complex algorithms needing explanation
- Non-obvious business logic
- Workarounds for external issues
- Public API documentation

### Avoid
- Commenting obvious code
- Commented-out code (use version control)
- TODO comments without tickets
- Misleading or outdated comments

## Testing

### Coverage Requirements
- Minimum: 70% code coverage
- Critical paths: 100% coverage
- Unit tests for business logic
- Integration tests for workflows
- Edge cases explicitly tested

### Test Quality
- One assertion per test (generally)
- Clear test names describing scenario
- Arrange-Act-Assert pattern
- No test interdependencies

## File Organization

### File Size
- Max 300-400 lines per file
- Split large files by concern
- One class/module per file (generally)

### Folder Structure
- Group by feature, not type
- Clear separation of concerns
- Flat structure where possible
- Consistent naming across project

## Performance Considerations

### Database
- Index frequently queried columns
- Avoid N+1 queries
- Use pagination for large datasets
- Cache expensive queries

### Algorithms
- Choose appropriate data structures
- Consider time/space complexity
- Profile before optimizing
- Avoid premature optimization

### Memory
- Release resources when done
- Avoid large objects in loops
- Use streams for large files
- Watch for memory leaks

## Code Smells to Watch For

- **Long methods**: Break into smaller functions
- **Large classes**: Split responsibilities
- **Long parameter lists**: Use objects
- **Duplicate code**: Extract and reuse
- **Dead code**: Remove unused code
- **Magic numbers**: Use named constants
- **Feature envy**: Move method to appropriate class
- **God objects**: Split into focused classes
