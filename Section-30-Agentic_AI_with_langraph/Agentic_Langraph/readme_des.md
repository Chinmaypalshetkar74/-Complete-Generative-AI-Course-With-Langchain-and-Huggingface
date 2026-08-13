🤖 LangGraph & Agentic AI: Complete Bootcamp Guide
Based on Krish Naik's Gen AI Bootcamp (Udemy - Section 30)
Welcome to the comprehensive guide for building production-ready AI agents using LangGraph. This repository documents the journey from basic chatbots to complex multi-agent systems, incorporating LangSmith for monitoring and LangGraph Studio for debugging.

📚 Course Overview
This bootcamp is divided into structured modules, guiding you from the fundamentals of agent architecture to advanced implementation with Model Context Protocol (MCP) and Human-in-the-Loop workflows.

🎯 Key Learning Outcomes
Core Concepts: Understand the difference between stateless LLM calls and stateful LangGraph workflows.
Agent Architectures: Build ReAct Agents with memory and chain-of-thought reasoning.
Observability: Monitor agents, trace execution, and debug performance using LangSmith.
Advanced Patterns: Implement Human-in-the-Loop approvals and Multi-Agent collaboration.
Tooling: Set up development environments using uv (Python package manager) and LangGraph Studio.
Modern Integration: Connect external tools and data sources using MCP.

🚀 Quick Start Guide
1. Environment Setup with uv
We use uv for fast, dependency-safe environments.

bash

Copy
# Install uv (if not installed)
curl -LsSf https://astral.sh/uv/install.sh | sh

# Clone the repository
git clone <repo-url>
cd langgraph-bootcamp

# Create and activate environment
uv venv --python 3.11
uv sync

# Install LangGraph dependencies
uv add langgraph langgraph-cli[inmem] langgraph-api langsmith
2. Run the Development Server
Use LangGraph Studio to visualize and debug your agents.

bash

Copy
# Start the local LangGraph server
langgraph dev

# Open Studio in your browser
# Navigate to http://localhost:5766
3. Run Specific Modules
Each module contains a main.py and specific instructions.

bash

Copy
# Example: Run the Basic Chatbot
cd 01_basics && python main.py

# Example: Run the ReAct Agent
cd 02_agent_architecture && python main.py
📖 Module Breakdown
1. 🌱 Basics: Building the First Chatbot
Concept: Introduction to StateGraph, nodes, and edges.
Implementation: Create a simple sequential workflow where an LLM processes input and generates a response.
Key Files: basic_chatbot.py, state_schema.py
2. 🧠 AI Agent Theory & ReAct Architecture
Concept: How agents think (Reasoning + Action).
Implementation: Build a ReAct Agent that can:
Plan steps (Reason)
Call tools (Act)
Observe results (Observe)
Key Files: react_agent.py, tools.py
3. 🧩 Memory Implementation
Concept: Maintaining context across conversations.
Implementation:
Buffer Memory: Store raw chat history.
Summary Memory: Summarize long conversations to save tokens.
State Management: Update the graph state dynamically.
Key Files: memory_node.py, state_with_memory.py
4. 🤝 Human-in-the-Loop
Concept: Introducing human approval steps for critical actions.
Implementation:
Create a node that pauses execution.
Use Conditional Edges to route based on user input (Approve/Reject).
Implement Interrupts for real-time feedback.
Key Files: human_approval.py, interrupt_workflow.py
5. 🔍 Monitoring & Debugging
Concept: Observability is crucial for production agents.
Implementation:
LangSmith: Project setup, tracing runs, and evaluating performance.
LangGraph Studio: Visualizing the graph, inspecting state, and replaying traces.
Key Files: monitoring_config.py, langsmith_tracing.py
6. 🕸️ Multi-Agent Systems
Concept: Collaborative agents working together.
Implementation:
Graph of Graphs: Sub-graphs for specific roles (e.g., Researcher, Writer, Editor).
Routing: Dynamic routing between agents based on query type.
Key Files: multi_agent_router.py, sub_graphs/
7. 🔌 MCP (Model Context Protocol)
Concept: Standardizing how LLMs connect to external data and tools.
Implementation:
Connect to local files, databases, or APIs via MCP.
Implement dynamic tool registration.
Key Files: mcp_integration.py, mcp_tools/
🛠️ Tech Stack & Tools
Tool	Purpose
LangGraph	Framework for building stateful, multi-agent applications
LangSmith	Observability, tracing, and evaluation platform
LangGraph Studio	Local GUI for debugging and testing graphs
uv	Ultra-fast Python package manager and resolver
Pydantic	Data validation and state schema definition
OpenAI / Anthropic	LLM Providers (configurable)
📊 LangSmith Tracing & Studio Usage
Visualizing the Agent
Start the Server: langgraph dev
Open Studio: Navigate to localhost:5766
Inspect State: Click on nodes to see the state dump at that step.
Debug: Replay traces to see exactly where the agent failed.
Key Metrics to Track
Token Usage: Monitor cost per run.
Latency: Time taken for each node.
Error Rates: Frequency of crashes or failed tool calls.
Human Intervention: How often the "Human-in-the-Loop" is triggered.
🤝 Contributing & Learning Path
This bootcamp is designed to be followed sequentially. Each module builds on the previous one.

Start with 00_environment_setup to ensure your uv environment is clean.
Follow the README in each folder for specific code instructions.
Experiment: Modify the code to add new tools or change the agent's personality.
Deploy: Once confident, deploy your graph to a cloud provider (e.g., AWS, Azure, or LangGraph Cloud).
📝 License
This project is for educational purposes based on Krish Naik's Udemy course. Feel free to fork and learn!

💡 Pro Tips
Always use uv: It prevents dependency hell and ensures reproducible environments.
Check LangSmith: If an agent behaves unexpectedly, the trace will usually show the exact step where the reasoning failed.
Human-in-the-Loop: Don't skip this section; it's critical for building trust in AI systems.
Happy Coding! 🚀