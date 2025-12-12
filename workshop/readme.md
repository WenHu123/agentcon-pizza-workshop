**start building here**
https://jolly-field-035345f1e.2.azurestaticapps.net/about.html

1. Setup Microsoft Foundry
https://jolly-field-035345f1e.2.azurestaticapps.net/1_microsoft-foundry.html

2. Create your agent
https://jolly-field-035345f1e.2.azurestaticapps.net/2_create-agent.html

3. Add instructions (or System Prompt)
https://jolly-field-035345f1e.2.azurestaticapps.net/3_add-instructions.html

4. Add knowledge using RAG
https://jolly-field-035345f1e.2.azurestaticapps.net/4_add-knowledge.html

Why Add Knowledge?
By default, the model only knows what it was trained on - it doesn’t have access to your organization’s private or domain-specific information.
To bridge this gap, we’ll use Retrieval-Augmented Generation (RAG).

RAG lets the agent fetch relevant information from your own data before generating a response.
This ensures your agent’s answers are accurate, up-to-date, and grounded in real information.
In Microsoft Foundry, we’ll use the File Search feature to implement this.
In this chapter, you’ll use a folder called ./documents that contains information about Contoso Pizza stores - such as locations, opening hours, and menus.

We’ll upload these files to Microsoft Foundry, create a vector store, and connect that store to the agent using a File Search tool.

5. Add estimation tool (Function Calling)
https://jolly-field-035345f1e.2.azurestaticapps.net/5_add-tool.html
What Are Tools (Function Calling)?
Tools let your agent call your code with structured inputs.
When a user asks for something that matches a tool’s purpose, the agent will select that tool, pass validated arguments, and use the tool’s result to craft a final answer.

Why this matters
Deterministic actions: offload precise work (math, lookup, API calls) to your code.
Safety & control: you define what the agent is allowed to do.
Better UX: the agent can provide concrete, actionable answers.
Adding the Pizza Size Calculator tool
We’ll add a tool that, given a group size and an appetite level, recommends how many and what size pizzas to order.
Tips & Best Practices
Schema first: if your SDK supports argument schemas, define clear types/enums/required fields.
Validate inputs: the tool should handle bad or missing data gracefully.
Single-purpose tools: small, focused tools are easier for the agent to choose and combine.
Explainability: name/describe tools so the agent knows when to use them.

6. Integrating MCP
https://jolly-field-035345f1e.2.azurestaticapps.net/6_add-mcp.html
What Is MCP and Why Use It?
MCP (Model Context Protocol) is an open standard for connecting AI agents to external tools, data sources, and services through interoperable MCP servers.
Instead of integrating with individual APIs, you connect once to an MCP server and automatically gain access to all the tools that server exposes.

Benefits of MCP
🧩 Interoperability: a universal way to expose tools from any service to any MCP-aware agent.
🔐 Security & governance: centrally manage access and tool permissions.
⚙️ Scalability: add or update server tools without changing your agent code.
🧠 Simplicity: keep integrations and business logic in the server; keep your agent focused on reasoning.
