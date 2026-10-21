---
tags:
  - ai
  - mcp
  - agentic-ai
---

# Model Context Protocol (MCP)

> **MCP** is an open protocol that gives AI applications a standard way to connect with external data sources, tools, and services.

## Why MCP?

An AI model is useful at reasoning and generating text, but it does not automatically have access to your files, databases, APIs, or apps. Traditionally, every AI application needed a separate integration for every service.

MCP standardizes this connection:

```text
AI application / host  <-->  MCP client  <-->  MCP server  <-->  tool or data source
```

It is often compared to a **universal connector for AI tools and context**.

## Core parts

| Part | Role |
|---|---|
| **Host** | The AI application that the user interacts with, such as an editor or desktop app. |
| **Client** | A component inside the host that communicates with one MCP server. |
| **Server** | A program that exposes capabilities to the client in the MCP format. |
| **Tool** | An action the model can request, e.g. search a database, create an issue, or run a query. |
| **Resource** | Readable context, such as a file, document, schema, or API result. |
| **Prompt** | A reusable prompt template offered by a server. |

## How it works

1. The host connects to an MCP server.
2. The server advertises its available tools, resources, and prompts.
3. The user asks for a task.
4. The AI decides whether a capability is useful.
5. The host requests permission when needed and invokes the capability.
6. The server returns structured results for the AI to use in its response.

## Example

**Task:** “Summarize this project's open GitHub issues.”

An MCP-enabled AI application could:

1. Use a GitHub MCP server to list issues.
2. Read the issue titles, labels, and descriptions.
3. Group them by priority or theme.
4. Produce a summary without the user manually copying data into the chat.

## Typical uses

- Search and read local files or knowledge bases
- Query databases and analytics systems
- Work with GitHub, issue trackers, chat, calendars, and cloud storage
- Call internal company APIs
- Automate repeatable workflows
- Provide domain-specific context to AI assistants

## Tools vs. resources

| | Tools | Resources |
|---|---|---|
| **Purpose** | Perform an action | Supply information/context |
| **Examples** | Send a message, execute a query, create a ticket | A Markdown file, database schema, API documentation |
| **Risk** | May change external state | Usually read-only, but still may contain sensitive data |

## Security considerations

MCP increases an AI application's access, so use it carefully.

- Connect only to servers you trust.
- Grant the minimum required permissions.
- Review tool calls that can modify or delete data.
- Keep secrets (API keys, tokens, passwords) out of prompts and logs.
- Treat data returned by tools as untrusted; it may contain misleading instructions.
- Separate read-only tools from write/destructive tools where possible.

## Benefits

- **Interoperability:** one protocol instead of many custom integrations.
- **Reusability:** the same MCP server can work with multiple compatible AI apps.
- **Better context:** AI can use current, task-relevant information.
- **Extensibility:** teams can expose internal tools in a consistent format.
- **User control:** applications can show and confirm the actions a model wants to take.

## Key idea

> MCP does not make the model smarter by itself. It gives the model a controlled, standardized way to access the right context and take useful actions.

## Quick revision

- **MCP = Model Context Protocol**
- It connects AI applications to external tools and data.
- A server exposes **tools**, **resources**, and **prompts**.
- The host/client uses these capabilities on the model's behalf.
- Security and permission control are essential.

## Related notes

- [[Ai]]
- [[Agents]]
- [[APIs]]
