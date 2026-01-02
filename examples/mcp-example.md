# MCP Servers Example

This document shows how AI assistants can use MCP servers to enhance their capabilities.

## Available MCP Servers

This template includes configuration for three MCP servers:

### 1. Filesystem Server
Provides AI assistants with file system access.

**Capabilities:**
- Read files and directories
- Search for files
- Get file metadata
- List directory contents

**Example Usage:**
```
Ask your AI: "What files are in the src directory?"
Ask your AI: "Show me the contents of config.json"
Ask your AI: "Find all JavaScript files that import React"
```

### 2. Git Server
Provides AI assistants with Git repository access.

**Capabilities:**
- View commit history
- Check repository status
- See file diffs
- Analyze branches

**Example Usage:**
```
Ask your AI: "What changes were made in the last commit?"
Ask your AI: "Show me the git history for this file"
Ask your AI: "What files have uncommitted changes?"
```

### 3. GitHub Server
Provides AI assistants with GitHub API access.

**Capabilities:**
- View issues and pull requests
- Search repositories
- Check Actions workflows
- Read discussions

**Example Usage:**
```
Ask your AI: "Show me open issues labeled 'bug'"
Ask your AI: "What's the status of PR #42?"
Ask your AI: "List recent workflow runs"
```

## Configuration

MCP servers are configured in `.mcp/config.json`. Each server specifies:
- `command`: How to run the server
- `args`: Arguments to pass
- `env`: Environment variables needed
- `description`: What the server does

## Custom MCP Servers

You can add your own MCP servers to enhance capabilities:

```json
{
  "mcpServers": {
    "custom-api": {
      "command": "node",
      "args": ["./mcp-servers/custom-api.js"],
      "env": {
        "API_KEY": "${CUSTOM_API_KEY}"
      },
      "description": "Your custom MCP server"
    }
  }
}
```

## Benefits of MCP

1. **Standardized Interface**: AI assistants can use any MCP server
2. **Extensible**: Add new capabilities by adding servers
3. **Secure**: Control what tools AI has access to
4. **Contextual**: AI gets real-time access to your development environment

## Learn More

- [MCP Specification](https://modelcontextprotocol.io/)
- [MCP SDK Documentation](https://github.com/modelcontextprotocol/sdk)
- [Available MCP Servers](https://github.com/modelcontextprotocol/servers)
