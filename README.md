# Personal Knowledge System (PKS): From Raw Thought to a Structured Knowledge Graph

_A system for transforming unstructured thought into a structured, queryable idea graph_

**Offir Olivkovich**

![Python](https://img.shields.io/badge/Python-3.x-blue) 
![LLM](https://img.shields.io/badge/LLM-Agent%20+%20Prompting-purple)
![Embeddings](https://img.shields.io/badge/Semantic-Embeddings-orange)
![Graph](https://img.shields.io/badge/Graph-NetworkX-green) 
![Database](https://img.shields.io/badge/Database-SQLite-lightgrey)

---

> [!IMPORTANT]
> ### TL;DR
> - Built a system that converts **raw text into a structured knowledge graph**
> - Used **LLMs** to extract atomic ideas and structure unorganized input
> - Used **embeddings** to compute semantic similarity between ideas
> - Constructed a **graph of interconnected ideas** across sessions
> - Implemented an **LLM agent with tool use** to query and explore the system
>
> **End result:** a searchable, navigable system for interacting with ideas beyond linear notes

## Overview

This project implements a pipeline that transforms unstructured streams of thought into a structured, queryable knowledge graph.

Instead of storing ideas as linear text, the system represents them as **atomic units** that can be embedded, linked, and explored through semantic relationships.

> [!TIP]
> **Start here → [`notebooks/pks_prototype.ipynb`](notebooks/pks_prototype.ipynb)**  
> This notebook contains the full pipeline, from raw input → structured idea graph → exploration.
>
> Or jump to [Example Outputs](#example-outputs)

## Core Capabilities

### 1. Idea Extraction (LLM)
- Extract atomic ideas from unstructured text using structured prompts  
- Convert free-form input into consistent, structured idea units  

### 2. Semantic Similarity (Embeddings)
- Generate vector embeddings using SentenceTransformers  
- Compute similarity between ideas  
- Retrieve related concepts across domains  

### 3. Graph Construction (Relationships)
- Represent ideas as nodes and relationships as edges  
- Define connections using similarity and shared session context  
- Identify clusters of related ideas  

### 4. Structured Storage (SQLite)
- Store ideas, metadata, and relationships in a relational database  
- Enable structured querying and traversal of idea connections  

### 5. LLM Agent (Tool-Based Exploration)
- Use an LLM as an agent to query the database via tools  
- Select and chain operations through prompt-driven reasoning  
- Aggregate multi-step results into coherent responses 
  </br>

## Example Outputs

<details>
<summary><strong>Representative inputs and outputs from the notebook:</strong></summary>

### 1. Idea Extraction

**Input (raw thought):**

    I think there should be a designated app for events. like where you can browse events by category,
    see which ones your friends are interested in, and easily share events with friends. 
    The existing apps arent so good at this.

**LLM Output (Structured Ideas):**

    [
      {
        "text": "There should be a designated app for events where users can browse events by category",
        "summary": "Event app with category browsing",
        "main_domain": "technology",
        "sub_domains": ["social", "productivity"],
        "idea_type": "idea",
        "tags": ["events", "app", "browsing"]
      },
      {
        "text": "The app should allow users to see which events their friends are interested in",
        "summary": "Social visibility of events",
        "main_domain": "technology",
        "sub_domains": ["social"],
        "idea_type": "feature",
        "tags": ["social", "events"]
      }
    ]

---

### 2. LLM Agent Interaction

**Invocation:**

    agent_loop("explore connections between consciousness and physiology")

**Output:**

    The connections between consciousness and physiology are complex and multifaceted, 
    drawing interest from various fields such as neuroscience, psychology, and philosophy. 
    Here are several key areas of exploration:

    1. Neuroscience of Consciousness
       - Brain activity and conscious experience
       - Role of different brain regions in awareness

    2. Physiological States and Consciousness
       - Effects of sleep, stress, and bodily states on perception and cognition

    3. Mind-Body Interaction
       - How physiological signals influence subjective experience

    ...
> **Limitation:** The agent is not yet strictly grounded in database retrieval and may rely on general LLM knowledge. This is a proof of concept (POC). Future work will enforce structured tool usage and validation to ensure responses are derived only from retrieved results.
</details>

---

## System Vision

The following illustration represents how ideas can be structured as a graph, where semantic relationships and clustering enable exploration across domains and sessions.

  <p align="center">
  <img src="images/AI_visualization2.png" width="80%">
</br>
  <sub>
  AI-generated conceptual illustration of the system vision. Content is arbitrary and for demonstration purposes.
  </sub>
</p>

---

## Technologies

- Core: Python, SQLite  
- ML / NLP: OpenAI API, SentenceTransformers  
- Analysis: scikit-learn  
- Graph: NetworkX, PyVis

---

## Running the Project

### Setup

    pip install -r requirements.txt

Set API key:

    export OPENAI_API_KEY=your_api_key_here

(on Windows use: `setx OPENAI_API_KEY your_api_key_here`)

### Run

- open `notebooks/pks_prototype.ipynb`  
- run cells in order  

The system will create and populate the database automatically.

---

## Future Work

The current implementation establishes a foundation for structuring and exploring ideas. Several extensions can further improve the system:

- LLM-based interpretation of clustering outputs  
- Interactive interface for exploration  
- Incremental graph updates  
- Improved similarity metrics  
- Enhanced idea classification  
- Scaling beyond notebook workflows  

---

> [!NOTE]
> This project started from a personal curiosity about how ideas could be structured and explored beyond linear notes. Building it was an opportunity to experiment with combining LLMs, embeddings, and graph-based representations into a single system.

---

## Contact

- GitHub: https://github.com/oyoai
- LinkedIn: https://linkedin.com/in/offir-olivkovich-ai
