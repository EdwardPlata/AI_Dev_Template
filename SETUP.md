# Setup Guide for AI Development Template

This guide will help you set up all the AI-enabled development tools included in this template.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [GitHub Copilot Setup](#github-copilot-setup)
3. [SpecKit Setup](#speckit-setup)
4. [MCP Servers Setup](#mcp-servers-setup)
5. [Claude Code Setup](#claude-code-setup)
6. [Verification](#verification)

## Prerequisites

Before you begin, ensure you have:

- [ ] Git installed
- [ ] Node.js (v16 or higher) and npm installed
- [ ] A code editor (VS Code is recommended)
- [ ] A GitHub account
- [ ] Internet connection

## GitHub Copilot Setup

### Step 1: Get Access

1. Visit [GitHub Copilot](https://github.com/features/copilot)
2. Sign up for a subscription or verify you have access through your organization
3. Individual plans start at $10/month, or free for verified students and open-source maintainers

### Step 2: Install VS Code Extension

1. Open VS Code
2. Go to Extensions (Ctrl+Shift+X or Cmd+Shift+X)
3. Search for "GitHub Copilot"
4. Install both:
   - GitHub Copilot
   - GitHub Copilot Chat

### Step 3: Sign In

1. After installation, you'll be prompted to sign in
2. Click "Sign in to GitHub"
3. Authorize the extension in your browser
4. Return to VS Code

### Step 4: Verify

1. Create a new file (e.g., `test.js`)
2. Start typing a comment like `// function to calculate factorial`
3. You should see Copilot suggestions appear

## SpecKit Setup

### Step 1: Create Account

1. Visit [SpecKit](https://speckit.dev/) (or your organization's SpecKit instance)
2. Create an account or sign in with your organization credentials

### Step 2: Get API Key

1. Navigate to Settings > API Keys
2. Generate a new API key
3. Copy the key (you won't be able to see it again)

### Step 3: Configure

1. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```

2. Add your SpecKit API key:
   ```bash
   SPECKIT_API_KEY=your_actual_api_key_here
   ```

### Step 4: Initialize Directories

```bash
mkdir -p specs/api specs/features specs/architecture docs
```

### Step 5: Verify

Check that `.speckit.json` exists and contains your project configuration.

## MCP Servers Setup

### Step 1: Install Dependencies

MCP servers are run through npx, so no installation is required. However, you can pre-cache them:

```bash
npx -y @modelcontextprotocol/server-filesystem --help
npx -y @modelcontextprotocol/server-git --help
npx -y @modelcontextprotocol/server-github --help
```

### Step 2: Configure GitHub Token (Optional)

For the GitHub MCP server:

1. Go to [GitHub Settings > Developer Settings > Personal Access Tokens](https://github.com/settings/tokens)
2. Generate a new token (classic) with `repo` scope
3. Add to your `.env` file:
   ```bash
   GITHUB_TOKEN=your_github_token_here
   ```

### Step 3: Verify Configuration

Check `.mcp/config.json` to ensure servers are configured correctly.

### Step 4: Test MCP Servers

```bash
npm run mcp:status
```

## Claude Code Setup

### Step 1: Get Anthropic API Access

1. Visit [Anthropic Console](https://console.anthropic.com/)
2. Sign up or sign in
3. Navigate to API Keys section
4. Create a new API key

### Step 2: Configure API Key

Add your API key to `.env`:

```bash
ANTHROPIC_API_KEY=your_anthropic_api_key_here
```

### Step 3: Install Claude Extensions

For VS Code:
1. Search for Claude extensions in the marketplace
2. Popular options include:
   - Claude Dev (if available)
   - Continue (supports Claude)
   - Cody (supports Claude)

### Step 4: Configure Extension

1. Open extension settings
2. Select "Claude" as your AI provider
3. Enter your API key (or it will be read from environment)
4. Choose your preferred model (e.g., claude-3-5-sonnet-20241022)

## Verification

### Check All Tools

1. **GitHub Copilot:**
   - Open a code file
   - Start typing and verify suggestions appear
   - Try Copilot Chat (Ctrl+Shift+I or Cmd+Shift+I)

2. **SpecKit:**
   - Verify `.speckit.json` exists
   - Check that spec directories are created

3. **MCP Servers:**
   - Verify `.mcp/config.json` exists
   - Check that your Claude/AI assistant can access MCP tools

4. **Claude Code:**
   - Open your Claude-enabled extension
   - Try a simple query like "Explain this codebase"
   - Verify it can read files and provide context-aware responses

### Test Workflow

Create a simple test file to verify all tools work together:

1. Create `test-ai-tools.js`
2. Use Copilot to generate a function
3. Use Claude to explain the function
4. Use MCP to search for similar patterns in your codebase
5. Document the function using SpecKit conventions

## Troubleshooting

### GitHub Copilot Issues

**Problem:** No suggestions appearing
- **Solution:** Check Copilot status in VS Code status bar
- Verify subscription is active
- Try reloading VS Code

**Problem:** Suggestions are poor quality
- **Solution:** Provide more context in comments
- Write clearer function/variable names
- Add type annotations

### MCP Server Issues

**Problem:** Cannot connect to MCP servers
- **Solution:** Verify Node.js is installed: `node --version`
- Check `.mcp/config.json` syntax
- Try running servers manually to see error messages

### Claude API Issues

**Problem:** API authentication errors
- **Solution:** Verify API key is correct
- Check API key has not expired
- Ensure you have API credits remaining

### SpecKit Issues

**Problem:** Cannot access SpecKit
- **Solution:** Verify API key is valid
- Check network connection
- Ensure organization access is granted

## Next Steps

1. Read the main [README.md](README.md) for usage examples
2. Explore each tool's documentation
3. Customize configurations for your project
4. Start coding with AI assistance!

## Support

- **GitHub Copilot:** [Documentation](https://docs.github.com/en/copilot)
- **SpecKit:** [Documentation](https://speckit.dev/docs)
- **MCP:** [Specification](https://modelcontextprotocol.io/)
- **Claude:** [Documentation](https://docs.anthropic.com/)

For issues with this template:
- Open an issue on GitHub
- Check existing issues for solutions
- Contribute improvements via Pull Request
