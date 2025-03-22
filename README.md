# Sequential Tools MCP Server

A Model Context Protocol (MCP) server for Sequential Thinking and Sequential Story as mnemonic techniques for problem-solving.

## Overview

This project offers two complementary MCP tools for structuring complex problems:

1. **Sequential Story** - A narrative-based approach to sequential thinking. Instead of tracking abstract thoughts, it structures problems as story elements with characters, settings, and plot developments to make them more memorable and engaging.

2. **Sequential Thinking** - A flexible analytical tool for breaking down complex problems through a chain of thoughts that can be revised, branched, and built upon as understanding deepens.

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

### Common Features
- Formatted, color-coded display of elements
- Full MCP protocol support for integration with AI systems
- Support for branching and revision

## Installation

```bash
# Clone the repository
git clone https://github.com/dhkts1/sequentialStory
cd sequentialStory

# Install just the base dependencies using uv
uv venv
source .venv/bin/activate
uv sync

# Install with development dependencies
uv sync --group dev

# Or install in development mode
uv pip install -e .
```

## Usage

### Running the server

```bash
# Run directly using the sequential_tools.py script
python sequential_tools.py
```

### Installing with MCP

```bash
# Install in the Claude desktop app
mcp install -e . -n "Sequential Tools" sequential_tools.py:server

# For development with the MCP Inspector
mcp dev sequential_tools.py:server
```

### Installing with Smithery

To register and install with Smithery:

1. Visit [Smithery.ai](https://smithery.ai) and create an account
2. Add your server to the Smithery registry
3. Use the stdin/stdout transport option (not WebSockets)
4. Deploy your server following Smithery's instructions

```bash
# Local testing for Smithery compatibility
python sequential_tools.py
```

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

The Sequential Thinking implementation is inspired by the JavaScript implementation from the Model Context Protocol repositories:
https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking
