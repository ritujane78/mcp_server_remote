# MCP Server (Remote – SSE)

## Overview

This project implements an **MCP Server using SSE (Server-Sent Events)** transport.

It allows remote MCP clients to connect over HTTP and receive responses via SSE.

## Transport

- **SSE (Server-Sent Events)**

This mode is suitable for:
- Remote deployments
- HTTP-based MCP clients
- Distributed systems

## Client Configuration Example

When connecting from an MCP client, configure the server URL as follows:

```properties
spring.ai.mcp.client.sse.connections.janeproduction.url=http://<server-ip>:8090
```

Replace `<server-ip>` with the IP address or hostname of the machine where this server is running.

## Verifying Server Functions

All functions (tools) exposed by this MCP server can be **verified and tested using the MCP Inspector**.

### MCP Inspector

The MCP Inspector allows you to:
- List all exposed MCP tools
- Inspect request and response schemas
- Invoke tools interactively
- Debug MCP behavior

#### Prerequisites

- **Node.js must be installed**

#### Run MCP Inspector

```bash
npx @modelcontextprotocol/inspector
```

>  Screenshots demonstrating tool verification using MCP Inspector are available.

## Notes

- SSE-based MCP servers are ideal for remote and cloud deployments.
- Spring AI currently does **not** support *streamable HTTP*, so SSE is used instead.
