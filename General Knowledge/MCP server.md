
An MCP Server is a way connect text based AI agents that accept tokens and return tokens to external data sources.

Creating an LLM is a lot of work, and has great payoff. It acts as a primitive "thinking" model that you can outsource thinking to, that has extensive general purpose knowledge but no domain specific knowledge.

Adding domain specific knowledge by comparison is a very easy thing to do- just attaching the extra information as "context" to a prompt enables the LLM to understand patterns.

What are the sources of data at wisetech?
1) wisetech academy
2) sharepoint
3) ediprod

Each data source has an MCP server with a common interface, the protocol was developed by anthropic.


When you make a request, the MCP server grabs relevant context and forwards the request + context to LLM.