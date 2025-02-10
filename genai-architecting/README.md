# LangPortal AI-Powered Language Learning System

## Overview
LangPortal is an AI-driven language learning platform designed to help students improve their language skills through interactive study activities. The system prioritizes privacy and cost-efficiency by leveraging a locally hosted AI model on an AI PC.

## Functional Requirements
- The company aims to own its infrastructure to address concerns regarding user data privacy and the rising costs of managed GenAI services.
- The AI PC budget is set between 60,000 INR and 1,00,000 INR.
- The platform will serve 50-100 active students within the state of Maharashtra.

## Assumptions
- Open-source LLMs, such as DeepSeek and IBM Granite, will be capable of running efficiently within the allocated hardware budget.
- A single office server with internet access will provide sufficient bandwidth to support 100 students.

## Hardware & System Architecture
### Hardware:
- **AI PC Specifications:**
  - Processor: 12th Gen Intel Core i5
  - RAM: 32GB/64GB
  - Storage: 1TB SSD
  - GPU: NVIDIA RTX 3060 12GB/NVIDIA RTX 4060TI 16GB (Which will allow larger models)
- **Networking:**
  - High-speed fiber connection for stable access

## System Architecture
### Components:
1. **LangPortal** - The core interface where students and teachers interact.
2. **SQLite3 Database** - Stores a core vocabulary of 2,000 words.
3. **Study Activities:**
   - Sentence Constructor
   - Writing Learning App
   - Text Adventure Immersion Game
   - Children's Storybook Reading
   - Pronunciation Tutor
4. **Sentence Constructor Module:**
   - **Retrieval-Augmented Generation (RAG):**
     - Utilizes a **Vector DB** and **Internet sources** for retrieval.
     - Implements caching for performance optimization.
   - **Guard Rails:**
     - Input validation before processing user queries.
     - Output validation to ensure quality and appropriateness.
   - **Local LLM (DeepSeek/Can Change as Budgets increase):**
     - Uses DeepSeek-r1-14b-qwen-distilled-q4_K_M (9.0GB) for cost efficiency:
        - Fits within our VRAM limit.
        - Q4 quantization offers good balance of quality and efficiency
        - Qwen architecture is known for good performance
     - Output caching to improve response times.

## Data Strategy
- The platform avoids copyright issues by purchasing and storing licensed learning materials in a local database.

## Guardrails Implementation

To ensure safe and responsible AI-generated content, LangPortal incorporates the following guardrails:

### Input Guardrails:
- Filtering of inappropriate or offensive language before processing user inputs.
- Restricting inputs that could lead to biased, harmful, or misleading responses.
- Ensuring that study materials align with educational standards and guidelines.

### Output Guardrails:
- Monitoring AI-generated content to prevent misinformation or inappropriate outputs.
- Applying post-processing filters to refine sentence structures and remove errors.
- Using a caching system to verify and store reliable responses for reuse, reducing unnecessary AI processing costs.

## Considerations
- Ensuring the local LLM can handle student interactions effectively within the hardware constraints.
- Scaling the infrastructure as student numbers grow while maintaining cost efficiency.
- Implementing robust caching mechanisms to optimize response times.

## Conclusion
LangPortal is a locally hosted AI-powered language learning solution designed to balance privacy, cost, and performance. By leveraging an open-source LLM and carefully structured study activities, the platform provides an engaging and effective learning experience for students in Maharashtra.

