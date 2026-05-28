---
name: context-window-management
description: "Optimize context window usage. Disable unused tools, manage MCP connections, and preserve context for important work."
---

# Context Window Management

Your context window is precious. Manage it carefully to maintain performance and avoid degradation.

## The Problem

Too many tools, MCPs, or context can reduce your effective context window from 200k to 70k tokens. Performance degrades significantly when context is overloaded.

## The Rule

**Keep 20-30 MCPs configured, but only 5-10 enabled per project.**

## Strategies

### 1. Disable Unused MCPs

Before starting work, check what's enabled:

```
/mcp
/plugins
```

Disable anything not needed for the current project.

### 2. Project-Specific Configuration

Different projects need different tools:

- **Frontend project:** Enable TypeScript LSP, CSS tools
- **Backend project:** Enable database MCP, API tools
- **DevOps project:** Enable cloud provider MCPs

### 3. Progressive Loading

Don't load everything at once:

1. Start with core tools (git, file system)
2. Add project-specific tools as needed
3. Remove tools when done with specific tasks

### 4. Context Compaction

When context gets large:

- Use `/compact` to manually trigger compaction
- Focus on recent, relevant context
- Let old context fade naturally

## Tool Inventory

### Always Keep Enabled

- File system access
- Git operations
- Terminal/bash access
- Search capabilities

### Enable Per Project

- Language-specific LSPs
- Database connections
- Cloud provider tools
- Testing frameworks

### Enable Temporarily

- Debugging tools (when debugging)
- Performance profiling (when optimizing)
- Deployment tools (when deploying)

## Warning Signs

Watch for these signs of context overload:

- Responses becoming less coherent
- Forgetting earlier parts of conversation
- Making mistakes on simple tasks
- Taking longer to respond

## Best Practices

1. **Start clean** — Don't carry context from previous sessions
2. **Be selective** — Only enable what you need
3. **Monitor usage** — Check context percentage regularly
4. **Compact proactively** — Don't wait until performance degrades
5. **Use subagents** — Delegate tasks to preserve main context

## Example: Frontend Development Session

```
Before starting:
1. Disable: Database MCPs, Cloud MCPs, DevOps tools
2. Enable: TypeScript LSP, CSS tools, Browser MCP
3. Check: /mcp shows 8 tools enabled

During session:
- Need to check database? Temporarily enable DB MCP
- Done with database? Disable it again

After session:
- Tools automatically return to default state
```

## Anti-Patterns

❌ **Enabling everything "just in case"** — Context pollution
❌ **Never checking MCP status** — Assume nothing
❌ **Keeping debug tools on permanently** — Waste of context
❌ **Ignoring context warnings** — Performance will degrade
