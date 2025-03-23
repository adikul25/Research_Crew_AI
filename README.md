# Research_Crew_AI

This repository contains a notebook-based framework for automating historical research tasks using LLM-powered agents. The system allows you to create researcher agents that can find, analyze, and summarize important historical events on any topic.

## Overview

This framework uses agent-based architecture to:
1. Create specialized researcher agents with specific goals and tools
2. Define research tasks with clear expected outputs
3. Execute these tasks to generate historical analysis

## Getting Started

### Prerequisites

```
pip install langchain openai beautifulsoup4 requests
```

### Basic Usage

```python
from research_agents import Agent, Task, writer
import your_llm_client  # Import your preferred LLM client

# Initialize your LLM
llm = your_llm_client.initialize()

# Create a researcher to investigate a historical topic
topic = "ancient Egypt"
researcher = create_researcher(topic, llm)

# Create a research task
research_task = create_history_task(topic, researcher)

# Execute the task
writer.execute_task(research_task)
```

## Core Components

### Agent Creator Function

This function creates a researcher agent with:
- A defined role and goal specific to your topic
- A detailed backstory that guides its research approach
- Research tools including web search and web scraping
- Verbose output for transparency
- Your chosen LLM as its reasoning engine

### Task Creator Function

This function creates a research task that:
- Clearly defines what to research about the topic
- Specifies the expected output format (bullet points with specific details)
- Assigns the task to your researcher agent
- Enables asynchronous execution for efficiency

### Task Execution

The writer object handles executing the task using the assigned agent, collecting the results, and formatting them according to the expected output.

## Customization

You can customize:
- Research topics
- Agent roles and capabilities
- Task descriptions and output formats
- LLM providers

## Example Output

```
Research: Ancient Rome

Important Historical Events:
• 509 BCE - Founding of the Roman Republic: Marked the transition from monarchy to republican government, establishing the Senate and principle of shared power. Significantly influenced future democratic systems and concepts of citizenship.

• 27 BCE - Establishment of the Roman Empire: Augustus became first Emperor, ending the Republic and beginning the Pax Romana era. Led to unprecedented stability, territorial expansion, and cultural development throughout the Mediterranean.

• 313 CE - Edict of Milan: Emperor Constantine legalized Christianity, transforming Rome's religious landscape. Ultimately led to Christianity becoming Rome's official religion, profoundly shaping European culture and history for centuries to follow.
```

## Advanced Usage

See the example notebooks for advanced configurations including:
- Multi-agent research teams
- Custom research tool integration
- Output templating
- Citation tracking
