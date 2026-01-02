# Contributing to AI Development Template

Thank you for your interest in contributing to this project! This document provides guidelines for contributing.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. Check if the issue already exists
2. Create a new issue with a clear title and description
3. Include relevant details:
   - Your environment (OS, editor, etc.)
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior

### Submitting Changes

1. **Fork the repository**
2. **Create a branch** for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**:
   - Follow existing code style
   - Update documentation if needed
   - Test your changes
4. **Commit your changes**:
   ```bash
   git commit -m "Description of changes"
   ```
5. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
6. **Create a Pull Request**

## Types of Contributions

### 🐛 Bug Fixes
- Fix broken configurations
- Correct documentation errors
- Resolve compatibility issues

### ✨ New Features
- Add support for new AI tools
- Create additional examples
- Enhance existing configurations

### 📚 Documentation
- Improve README or guides
- Add tutorials
- Clarify setup instructions

### 🔧 Configuration
- Update tool configurations
- Add new MCP servers
- Enhance VS Code settings

## Guidelines

### Code Style

- Use clear, descriptive names
- Follow existing formatting
- Add comments for complex logic
- Keep changes focused and minimal

### Documentation

- Update relevant docs with your changes
- Use clear, concise language
- Include examples where helpful
- Check for spelling and grammar

### Configuration Files

- Validate JSON files before committing
- Use consistent formatting
- Add comments (where supported)
- Test configurations work

### Commit Messages

Good commit messages:
- Start with a verb ("Add", "Fix", "Update")
- Be concise but descriptive
- Reference issues if applicable

Examples:
- ✅ "Add MCP server for Docker"
- ✅ "Fix typo in SETUP.md"
- ✅ "Update Copilot settings for better performance"
- ❌ "Fixed stuff"
- ❌ "Update"

## Testing

Before submitting:

1. **Validate JSON files**:
   ```bash
   cat package.json | jq .
   cat .mcp/config.json | jq .
   ```

2. **Check documentation**:
   - All links work
   - Markdown renders correctly
   - No spelling errors

3. **Test configurations**:
   - VS Code extensions load
   - MCP servers can be started
   - No syntax errors

## Pull Request Process

1. **Ensure your PR**:
   - Has a clear title and description
   - References any related issues
   - Includes necessary documentation updates
   - Passes all checks

2. **PR will be reviewed for**:
   - Code quality
   - Documentation completeness
   - Consistency with existing code
   - Value to the project

3. **After approval**:
   - Your PR will be merged
   - You'll be added to contributors

## Community

- Be respectful and constructive
- Help others in issues and discussions
- Share your experiences using the template
- Suggest improvements

## Questions?

If you have questions about contributing:
- Open a discussion
- Comment on relevant issues
- Review existing PRs for examples

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing! 🎉
