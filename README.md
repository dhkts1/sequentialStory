[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/dhkts1-sequentialstory-badge.png)](https://mseep.ai/app/dhkts1-sequentialstory)

# Sequential Story MCP Server

A Model Context Protocol (MCP) server for Sequential Thinking and Sequential Story as mnemonic techniques for problem-solving.

## Overview

This project offers two complementary MCP tools for structuring complex problems:

1. **Sequential Story** - A narrative-based approach to sequential thinking. Instead of tracking abstract thoughts, it structures problems as story elements with characters, settings, and plot developments to make them more memorable and engaging.

2. **Sequential Thinking** - A pure Python port of the JavaScript implementation, eliminating Node.js dependencies

Both approaches leverage the power of sequencing and structure to enhance memory retention and problem understanding.

## Features

### Sequential Story
- Build problem solutions as narrative sequences
- Revise and branch story elements as needed
- Track characters, settings, tones, and plot points
- Formatted, color-coded display of story elements

### Sequential Thinking
- Structure problems as a sequence of thoughts
- Revise or branch thinking paths as needed
- Generate and verify solution hypotheses
- Track thinking process completion
- Pure Python implementation (no Node.js required)

### Common Features
- Formatted, color-coded display of elements
- Full MCP protocol support for integration with AI systems
- Support for branching and revision

## Installation

### During Development

When working with the package locally before publishing:

```bash
# Clone the repository
git clone https://github.com/dhkts1/sequentialStory
cd sequentialStory

# Install dependencies using uv
uv venv
source .venv/bin/activate
uv sync

# Install with development dependencies
uv sync --group dev

```



### Installing with MCP

```bash
# Install in the Claude desktop app
mcp install -e . src/cli.py -n "Sequential Story"

# Install with only the Sequential Thinking tool
mcp install -e . src/cli.py -n "Sequential Thinking" --env-var "TOOLS='[\"thinking\"]'"

# Install with only the Sequential Story tool explicitly
mcp install -e . src/cli.py -n "Sequential Story" --env-var "TOOLS='[\"story\"]'"

# Install with both tools
mcp install -e . src/cli.py -n "Sequential Tools" --env-var "TOOLS='[\"thinking\",\"story\"]'"
```

For development:

```bash
# For development with the MCP Inspector
mcp dev src/__main__.py:main
```

You can also configure Claude desktop to use the tool with `uvx` by adding this to your Claude mcpServers.json:

```json
"mcpServers": {
  "Sequential Story": {
    "command": "uvx",
    "args": [
      "sequential-story"
    ]
  }
}
```

The environment variable `TOOLS` controls which tools are enabled. By default, only the Sequential Story tool is enabled, but the Sequential Thinking tool can be added as needed.

This is useful when you want to focus on a specific problem-solving approach or when integrating with other MCP tools. You can also update the environment variables directly in the Claude desktop app after installation.

### Example story element

```json
{
  "element": "Our protagonist, a data scientist named Alex, encounters a mysterious pattern in the customer behavior data.",
  "elementNumber": 1,
  "totalElements": 5,
  "nextElementNeeded": true,
  "character": "Alex (data scientist)",
  "setting": "Data analysis lab",
  "tone": "Mysterious",
  "plotPoint": "Discovery of pattern"
}
```

### Example thought element

```json
{
  "thought": "The problem requires analyzing multiple data sources to identify correlations between customer behavior and sales patterns.",
  "thoughtNumber": 1,
  "totalThoughts": 5,
  "nextThoughtNeeded": true
}
```

## Development

```bash
# Install pre-commit hooks
uv run pre-commit install

# Run all pre-commit checks
poe pre
```
## Credits

This project builds on the concepts of sequential thinking and structured problem-solving, adapting these approaches to both analytical and narrative frameworks for enhanced memory and problem-solving.

The Sequential Thinking implementation is a pure Python port inspired by the JavaScript implementation from the Model Context Protocol repositories:
https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking