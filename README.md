# Installation

To set up the MCP server, add the following configuration to your MCP client settings (e.g., in your MCP configuration file):

```json
{
  "mcpServers": {
    "add_tool": {
      "command": "wsl",
      "args": [
        "-d",
        "Ubuntu",
        "--cd",
        "/home/mishrasanjay/projects/mcpdemo/mcp-server-deepdive-functionality",
        "/home/mishrasanjay/.local/bin/uvx",
        "--from",
        "git+https://github.com/sanjaymishradm/mymcpservers.git",
        "mcp-server"
      ],
      "env": {
        "HOME": "/home/mishrasanjay",
        "LOGNAME": "mishrasanjay",
        "PATH": "/home/mishrasanjay/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
        "SHELL": "/bin/bash",
        "TERM": "xterm-256color",
        "USER": "mishrasanjay"
      }
    }
  }
}
```

This configuration runs the MCP server inside a WSL Ubuntu distribution, using `uvx` to install and execute the server from the specified Git repository.

## Running Directly on Windows

To run the MCP server natively on Windows (without WSL), use the following configuration in your MCP client settings:

```json
{
  "mcpServers": {
    "add_tool": {
      "command": "uvx",
      "args": [
        "--from",
        "git+https://github.com/sanjaymishradm/mymcpservers.git",
        "mcp-server"
      ]
    }
  }
}
```

This configuration assumes you have `uvx` installed and available in your Windows PATH. It will install and run the MCP server directly from the specified Git repository on Windows.