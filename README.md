# mcp-scaffolder

An MCP (Model Context Protocol) server that scaffolds new project directories from built-in templates for **Python**, **Node.js**, and **Go**. Built with [FastMCP](https://github.com/jlowin/fastmcp), it exposes tools that MCP-compatible clients (e.g. Claude Desktop) can call to generate ready-to-use project skeletons.

## Features

- Scaffolds project structures with a single tool call
- Supports Python, Node.js, and Go templates out of the box
- Generates source files, `README.md`, `.gitignore`, and language-specific subdirectories
- Configurable output directory via the `PROJECTS_DIR` environment variable
- Runs over stdio for easy integration with MCP clients

## Tools

| Tool | Description |
|------|-------------|
| `scaffold_project(name, language)` | Creates a new project directory with template files. `language` must be one of `python`, `node`, `go`. |
| `list_templates()` | Lists all available templates and the files/directories they generate. |

## Templates

- **Python** – `main.py`, `requirements.txt`, `README.md`, `.gitignore`, `tests/`
- **Node.js** – `index.js`, `package.json`, `README.md`, `.gitignore`
- **Go** – `main.go`, `go.mod`, `README.md`, `.gitignore`, `cmd/`, `internal/`

## Installation

```bash
git clone https://github.com/Rikita22/mcp-scaffolder.git
cd mcp-scaffolder

python -m venv .venv
.venv\Scripts\activate      # On Windows
# source .venv/bin/activate # On macOS/Linux

pip install mcp
