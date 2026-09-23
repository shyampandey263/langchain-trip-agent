See also: [langchain-rag-qa](https://github.com/shyampandey263/langchain-rag-qa) — a retrieval-augmented agent with memory.
# LangChain Trip Cost Agent

A small AI agent built with LangChain 1.x. It has two independent tools: one looks up a
petrol price, the other calculates a trip's fuel cost. The model decides which tool to call.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shyampandey263/langchain-trip-agent/blob/main/langchain-trip-agent.ipynb)

See also: [langchain-rag-qa](https://github.com/shyampandey263/langchain-rag-qa) — a retrieval-augmented agent with memory.

## How it works
The user asks a question. The agent decides which tool fits: a price lookup, a cost
calculation, or both if needed. Each tool is self-contained, so the model never has to
chain one tool's output into another's input.

## How to run
1. Click the "Open In Colab" badge above.
2. Runtime, then Change runtime type, then T4 GPU.
3. Run the cells top to bottom. It installs Ollama, downloads llama3.1, and runs the agent.

## What I learned
Tool design matters. My first version chained two tools (price lookup, then calculation),
and the model called both at once with a placeholder instead of a real number. Making each
tool self-contained fixed it. This came up again on the RAG project, where reading the
trace, not just the final answer, was the only way to catch the issue.

## Tech
Python, LangChain 1.x, Ollama (llama3.1), Google Colab
