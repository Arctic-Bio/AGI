# Artificial Brain: A Modular AGI Architecture

This repository demonstrates a modular approach to building an artificial intelligence system inspired by the human brain. We combine diverse AI and logic-driven components, orchestrated by an executive reasoning module, to emulate perception, memory, reasoning, and decision-making. Background processes continuously organize knowledge, form dynamic conceptions, and perform deductive reasoning, enriching a growing knowledge base.

---

## 🚀 Project Overview

* **Multi‑Segment Brain Simulation**: Each brain "segment" encapsulates a specific cognitive function (e.g., language understanding, vision, pattern recognition, symbolic reasoning).
* **Executive Controller**: A central agent that plans, sequences, and supervises tasks, coordinating sub‑modules via a simulated Executive Function (akin to the prefrontal cortex).
* **Background Cognitive Services**: Autonomous agents handling:

  * **Memory Management**: Encoding, retrieval, and consolidation of short‑ and long‑term memories.
  * **Knowledge Organization**: Indexing facts, concepts, and relationships.
  * **Concept Formation**: Clustering and abstraction to build higher‑order representations.
  * **Procedural Growth**: Deductive and inductive reasoning loops that update and expand the knowledge graph continuously.

## 🏗️ Architecture

```plaintext
┌──────────────────────────┐       ┌─────────────────────┐
│   Executive Controller   │<----->│ Planning & Reasoning│
└─────────────┬────────────┘       └─────────────────────┘
              │
  ┌───────────┼──────────┐
  │           │          │
┌─▼─┐       ┌─▼─┐      ┌─▼─┐       ┌─────────────────┐
│LLM│       │VLM│      │STT│       │ Knowledge & Mem │
│   │       │   │      │   │       │    Modules      │
└─┬─┘       └─┬─┘      └─┬─┘       └─────────────────┘
  │           │          │
  ▼           ▼          ▼
Perception  Vision     Speech

Background Services:
- Memory Aging & Retrieval
- Knowledge Graph Updater
- Concept Abstraction
- Reasoning Pipelines
```

## 🔧 Components

1. **Core LLMs**: Lightweight, quantized models (e.g., Mistral 7B, Llama 3 8B) for chain‑of‑thought reasoning and text generation.
2. **Vision Modules**: Small Vision-Language Models (e.g., SmolVLM, ViT) handling image understanding.
3. **Speech Processing**: ASR/TTS engines (e.g., Whisper.cpp, Coqui) for natural language input/output.
4. **Knowledge Base**: A graph database (e.g., Memgraph/PyKEEN) storing entities, relations, and episodic traces.
5. **Memory Manager**: Short‑term working memory buffers + compressed embeddings for efficient retrieval.
6. **Symbolic Planner**: PDDL‑based or graph‑search planner for high‑level task decomposition.
7. **Executive Agent**: LangChain‑style orchestration layer that sequences calls, monitors progress, and handles exceptions.
8. **Background Agents**:

   * **Indexer**: Continuously ingests new data, updates vector stores.
   * **Abstraction Engine**: Performs concept extraction and clustering on stored knowledge.
   * **Reasoner**: Runs periodic deductive inference to derive new facts and update the graph.

## 📦 Installation

```bash
git clone https://github.com/your-org/artificial-brain.git
cd artificial-brain
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

> **Note**: For quantized models, ensure you have `bitsandbytes` and appropriate GPU (or CPU) support.

## ⚙️ Usage

1. **Start the Executive Controller**:

   ```bash
   python executive_controller.py
   ```
2. **Launch Background Services** (in separate terminals or via a process manager):

   ```bash
   python services/indexer.py
   python services/abstraction.py
   python services/reasoner.py
   ```
3. **Interact via CLI or UI**:

   ```bash
   python interact.py --mode chat
   ```

## 🧪 Examples

* **Chat Interaction**: Ask the system to summarize a document, plan a trip, or solve a puzzle, and watch how modules collaborate.
* **Perception Demo**: Send an image to `/vision/process` endpoint and receive a semantic caption + related facts.
* **Memory Query**: Retrieve recent "episodic" memories or explore the knowledge graph graphically.

## 🔬 Extensibility

* Plug in new models: Add your own vision or language models by modifying `config/models.yml`.
* Implement custom services: Create new background scripts under `services/` for tasks like simulation, planning, or analytics.
* Swap DB backends: Replace the knowledge graph with Neo4j or Faiss-based vector stores.

## 🤝 Contributing

Contributions and suggestions are welcome! Please open issues or submit pull requests.

---

> Crafted to emulate distributed cognitive processes and dynamic learning, this artificial brain architecture aims to push the boundaries of local, modular AGI simulation.
