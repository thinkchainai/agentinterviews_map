# Agent Interviews MCP

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue.svg)](https://modelcontextprotocol.io)

> Access your Agent Interviews data directly from Claude and Cursor using Model Context Protocol (MCP)

## Overview

The Agent Interviews MCP server provides a standardized way for AI assistants to access your interview data, reports, and transcripts using the [Model Context Protocol (MCP)](https://modelcontextprotocol.io). This integration allows Claude, Cursor, and other MCP-compatible AI assistants to seamlessly interact with your Agent Interviews account.

## Features

- ✅ **Secure API Access**: Connect to your Agent Interviews account using your API key
- ✅ **Prefixed Tools**: All tools use the `agentinterviews_` prefix to avoid collisions with other MCPs
- ✅ **Comprehensive Functionality**: Access interviews, transcripts, reports, projects, and more
- ✅ **Intuitive Queries**: Ask natural language questions and let the AI determine the right tools to use

## Documentation

For comprehensive setup guides and usage instructions, visit our official documentation:

- [Model Context Protocol Overview](https://docs.agentinterviews.com/MCP/overview/)
- [Setting Up MCP in Cursor](https://docs.agentinterviews.com/MCP/setup-cursor/)
- [Setting Up MCP in Claude Desktop](https://docs.agentinterviews.com/MCP/setup-claude/)

## Quick Start

### Prerequisites

- An Agent Interviews account with API access
- Your Agent Interviews API key
- MCP-compatible client (Claude Desktop, Cursor, etc.)

### Cursor Setup

```json
{
  "mcpServers": {
    "AgentInterviews": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote@latest",
        "https://api.agentinterviews.com/mcp",
        "--header",
        "Authorization:${API_KEY}"
      ],
      "env": {
        "API_KEY": "Api-Key YOUR_API_KEY_HERE"
      }
    }
  }
}
```

### Claude Desktop Setup

Edit your Claude Desktop config file (accessible via Claude menu → Settings → Developer → Edit Config):

```json
{
  "mcpServers": {
    "agentinterviews": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote@latest",
        "https://api.agentinterviews.com/mcp",
        "--header",
        "Authorization:${API_KEY}"
      ],
      "env": {
        "API_KEY": "Api-Key YOUR_API_KEY_HERE"
      }
    }
  }
}
```

## Example Usage

Once configured, you can ask questions like:

- "Show me the status of my recent interviews"
- "Get the transcript from my last interview with candidate John Smith"
- "What projects do I have available?"
- "Show me details about the 'Senior Developer' interviewer"

## Available Tools

Our MCP server exposes tools with the `agentinterviews_` prefix. Some key tools include:

- `agentinterviews_list_projects`: List all your projects
- `agentinterviews_get_interview`: Get details about a specific interview
- `agentinterviews_list_interviewers`: List all your interviewers
- `agentinterviews_get_transcript`: Get a transcript from an interview

## Security

The Agent Interviews MCP server requires your API key for authentication. This key is used to securely access your account data. Never share your API key or include it in public repositories.

## Support

If you encounter any issues or have questions:

- Check our [documentation](https://docs.agentinterviews.com/MCP/overview/)
- Contact [support@agentinterviews.com](mailto:support@agentinterviews.com)
- Open an issue in this repository

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Related Projects

- [Model Context Protocol](https://github.com/modelcontextprotocol/modelcontextprotocol)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)
