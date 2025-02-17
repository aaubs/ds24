---
title: "Intro to Agentic Systems in AI"
weight: 5
disableToc: true
draft: false
---

## Literature

[Zhihua Duan, Jialin Wang (2024): Exploration of LLM Multi-Agent Application Implementation Based on LangGraph+CrewAI](https://arxiv.org/pdf/2411.18241)

## Resources

* [CrewAI documentation](https://docs.crewai.com/introduction)
    * Focus on [intro](https://docs.crewai.com/introduction), [agents](https://docs.crewai.com/concepts/agents), [tasks](https://docs.crewai.com/concepts/agents), [crews](https://docs.crewai.com/concepts/crews), [flows](https://docs.crewai.com/concepts/flows), and [tools](https://docs.crewai.com/concepts/tools)
    * Also, check out [CrewAIs framework examples](https://github.com/crewAIInc/crewAI-examples/). Specifically, the workshop will depart from the [Book writing crew](https://github.com/crewAIInc/crewAI-examples/tree/main/write_a_book_with_flows) example.    
* [Pydantic](https://docs.pydantic.dev/latest/)
* [Python packaging convention](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

## Building Multi-Agent Systems with CrewAI
This workshop explores the development of agentic systems - building AI applications where multiple specialized agents collaborate to accomplish complex tasks. Using CrewAI as our framework, we'll examine both theoretical concepts and practical implementation.

## Key Topics

### 1. Agentic Systems Fundamentals
- Role specialization and agent collaboration  
- Task delegation and coordination
- State management in multi-agent systems

### 2. CrewAI Framework
- Agents: Specialized roles with defined goals
- Crews: Orchestrating agent collaboration  
- Tasks: Structured work units
- Flow: Managing state and process control

### 3. Project Structure and Best Practices
- Organizing code with clear folder hierarchies
- Configuration management using YAML
- Data validation with Pydantic models  
- Testing and debugging agent interactions

### Real-world application
We'll examine a tender document generation system that demonstrates:
- Analysis and writing agent collaboration
- Structured data handling
- State management across multiple tasks
- Output validation and formatting
