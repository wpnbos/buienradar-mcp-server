# Buienradar MCP Server

## Overview

This is an MCP server that fetches precipitation data for a given latitude and longitude using Buienradar. It exposes a single MCP tool, `get_precipitation_for`, which provides precipitation forecasts for the next two hours.

## Configuration

First, make sure you have `uv` (and Python) installed.

To integrate this server with `Claude for Desktop`, update your configuration file at:

MacOS/Linux
```
~/Library/Application Support/Claude/claude_desktop_config.json
```

Windows
```
code $env:AppData\Claude\claude_desktop_config.json
```

Example configuration:

```json
{
    "mcpServers": {
        "precipitation": {
            "command": "uv",
            "args": [
                "--directory",
                "/ABSOLUTE/PATH/TO/PARENT/FOLDER/buienradar-mcp-server",
                "run",
                "server.py"
            ]
        }
    }
}
```

Replace `/ABSOLUTE/PATH/TO/PARENT/FOLDER/buienradar-mcp-server` with the actual path where your server is located.

Restart Claude for Desktop for the tool to become available.

You might have to provide the full path for `uv` instead of just `uv`.
To find the full path for your `uv` executable, on MacOS/Linux execute `which uv`.

## Usage

If all went well, you should be able to ask Claude about any upcoming precipitation.

```
> Will there be any rain soon in Amsterdam?

> No rain predicted in Amsterdam for the next 2 hours.
```
