# MCP Server Demo

This document provides step-by-step instructions to create and run the MCP server demo project.

## Prerequisites
- Python 3.13 or later installed on your system.
- `uv` CLI tool installed. You can install it using:
  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

## Steps to Create and Run the Project

### 1. Initialize the Project
1. Open a terminal and navigate to your desired workspace directory.
2. Run the following command to initialize a new MCP server project:
   ```bash
   uv init mcp-server-demo
   ```
3. Navigate into the project directory:
   ```bash
   cd mcp-server-demo
   ```

### 2. Add Dependencies
1. Add the `mcp[cli]` dependency to the project:
   ```bash
   uv add "mcp[cli]"
   ```

### 3. Modify the `main.py` File
1. Open the `main.py` file in your preferred text editor.
2. Ensure the `FastMCP` object is globally accessible with a standard name (e.g., `mcp`).
   Example content for `main.py`:
   ```python
   from mcp.server.fastmcp import FastMCP

   # Ensure the FastMCP object is globally accessible with a standard name
   mcp = FastMCP("Demo")

   def main():
       print("Hello from mcp-server-demo!")

   if __name__ == "__main__":
       main()
   ```

### 4. Run the MCP Server
1. Start the MCP server in development mode:
   ```bash
   uv run mcp dev main.py
   ```
2. The server will start and be accessible at `http://127.0.0.1:6274`.

### 5. Interact with the Server
1. Use a browser, `curl`, or Postman to send requests to the server.
2. Example:
   ```bash
   curl http://127.0.0.1:6274
   ```

## Notes
- Ensure that the `uv` CLI tool is in your system's PATH.
- If you encounter issues, verify that the `FastMCP` object is correctly defined and globally accessible in `main.py`.

Enjoy working with your MCP server demo!