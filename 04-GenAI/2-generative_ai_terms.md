# 🧠 Generative AI Terms You Should Know!

![Generative AI Terms Header](genai_terms_images/genai_terms_header.png)

Absolutely — here is a **clear, simple, accurate explanation of every term** shown in the “Generative AI Terms You Should Know!” graphic.
There are **36 terms**, grouped for easy understanding.

---
### **1. Generative AI**

AI that *creates* new data—text, images, audio, code—based on patterns it learned.
Examples: ChatGPT, Midjourney, Claude.

---

### **2. Discriminative AI**

AI that *classifies* existing data into categories.
Example: Spam vs. Not Spam, Dog vs. Cat classification.

---

### **3. AGI (Artificial General Intelligence)**

A hypothetical AI that can understand, learn, and reason across *any* domain like a human.
**Does not exist yet.**

---

### **4. ASI (Artificial Superintelligence)**

AI that surpasses human capabilities in *every* possible domain.
A science-fiction concept, not real today.

---

### **5. ANI (Artificial Narrow Intelligence)**

AI designed for one specific task.
Example: Google Maps navigation, recommendation systems.

---

### **6. Foundation LLM**

A large general-purpose model trained on massive datasets.
It can be adapted to many tasks with prompting or fine-tuning.
Examples: GPT-4, Llama, Claude, Gemini.

---

### **7. Self-Supervision**

Training method where AI learns from unlabelled data by predicting hidden or masked parts.
Example: Predicting the next word in a sentence.

---

### **8. Domain Adaptation**

Using a model trained in one domain and adapting it to a *related* domain.
Example: A medical LLM adapted to work for insurance claims.

---

---

# 📏 **2. Model Input & Learning Concepts**

### **9. Context Length**

The maximum number of tokens (words / characters) an LLM can process at once.
Longer context → LLM remembers more in a conversation.

---

### **10. Zero-Shot Learning**

AI performs a task with *no examples*, relying only on the instructions given.

---

### **11. Few-Shot Learning**

AI performs a task after seeing *a few examples* in the prompt.

---

### **12. Transformer**

The neural network architecture powering most modern LLMs.
Key innovation: **self-attention**.

---

### **13. Attention**

Mechanism allowing the model to focus on the *most relevant* parts of input text.
Example: Tracking which word relates to which in a long sentence.

---

### **14. Weights**

Numerical parameters within the model that determine its behavior.
These are what models “learn” during training.

---

### **15. MM-LLM (Multimodal LLM)**

A model that can understand and create content across modalities:
🖼️ images
📄 text
🎧 audio
🎥 video

---

### **16. Diffusion Models**

Models that generate images by starting from noise and refining it.
Used by: Stable Diffusion, DALL·E, Midjourney.

---

---

# 📚 **3. Data Concepts**

### **17. RAG (Retrieval-Augmented Generation)**

Technique where LLM retrieves external knowledge before generating answers.
Improves accuracy and reduces hallucinations.

---

### **18. Tokenization**

Breaking text into smaller units (tokens) for processing.
Example: “ChatGPT is great” → [“Chat”, “G”, “PT”, “is”, “great”]

---

### **19. Knowledge Base (KB)**

A structured set of documents or data that RAG systems query.

---

### **20. Structured Data**

Data in a fixed format with defined relationships.
Example: Excel sheets, databases.

---

### **21. Unstructured Data**

Data without a predefined format.
Example: PDFs, emails, images.

---

### **22. Vector DB (Vector Database)**

Database for storing embeddings (numerical representations).
Used for semantic search, RAG.

---

### **23. Embeddings**

Numerical representation of text or images, capturing meaning and relationships.
Example: “king - man + woman = queen”

---

### **24. Vector Search**

Finding the most semantically similar chunks using embeddings.

---

---

# 🧾 **4. Prompting & Interaction Concepts**

### **25. Prompting**

Giving instructions to LLMs to produce an output.

---

### **26. User Prompt**

The actual input text a user provides.

---

### **27. System Prompt**

Instructions that define how the AI should behave.
Example: “You are a helpful assistant.”

---

### **28. Meta Prompting**

Prompting a model to *generate* the best prompt for your task.

---

### **29. In-Context Learning**

LLM learns a pattern from examples *inside* the prompt—no training required.

---

### **30. Chaining**

Linking multiple prompts or model calls to solve multi-step tasks.
Example: Retrieve → Extract → Summarize.

---

---

# 🔧 **5. Model Training & Optimization**

### **31. Fine-Tuning**

Training a model further on task-specific data to improve accuracy.

---

### **32. PEFT (Parameter-Efficient Fine-Tuning)**

Fine-tuning only a *small subset* of model parameters so it’s cheaper and faster.

---

### **33. Distillation**

Creating a smaller model that mimics a larger model's behavior.
Example: Distilled versions of BERT.

---

### **34. Quantization**

Reducing precision of model weights (e.g., 16-bit → 8-bit) to save memory and speed up inference.

---

### **35. GGUF**

A fast binary file format optimized for running LLMs locally.
Used by tools like llama.cpp and GGML.

---

---

# ⚠️ **6. Safety & Architecture Concepts**

### **36. Reinforcement Learning**

Learning through rewards and penalties over repeated trials.

---

### **37. RLHF (Reinforcement Learning with Human Feedback)**

Human ratings guide model behavior during training.
Used heavily by OpenAI.

---

### **38. Adversarial Attacks**

Attempts to trick an AI into making mistakes with carefully crafted inputs.

---

### **39. MoE (Mixture of Experts)**

Architecture where multiple expert networks collaborate, improving performance and efficiency.

---

### **40. Hallucination**

When an LLM produces incorrect or fabricated information but sounds confident.

---

![Generative AI Terms Definitions](genai_terms_images/genai_terms_definitions.png)

Here is a **complete, clear explanation of every term** shown in the *Agentic AI Terms You Should Know!* graphic.
This glossary will help you understand the full landscape of **agent-based AI systems**, **tools**, **memory**, **reasoning**, and **design patterns**.

---

# 🚀 **Agentic AI Terms — Full Explanations**

---

# 🧠 **1. Core Model & Reasoning Concepts**

### **1. LLM**

A Large Language Model that generates or understands text, images, or other data.

---

### **2. Reasoning**

The process where AI analyzes context, evaluates options, selects tools, and performs multi-step actions to reach a conclusion.

---

### **3. LRM (Large Reasoning Model)**

A new class of models optimized for **multi-step logical reasoning**, planning, and action-taking — beyond just text generation.

Examples: OpenAI o1, o3; DeepSeek-R1.

---

### **4. Continual Pretraining**

Training an AI model further on new *unlabeled* data to improve general knowledge and performance.

---

### **5. Supervised Fine-Tuning (SFT)**

Training on *labeled* datasets to improve model accuracy for specific tasks.

---

### **6. Distillation**

A technique where a smaller model learns to mimic a larger model’s outputs.

---

### **7. MoE (Mixture of Experts)**

Architecture where the model routes work to specialized “experts,” making it efficient and scalable.

---

### **8. HITL (Human-in-the-Loop)**

Human oversight is incorporated into the AI workflow to improve safety, correctness, or decision quality.

---

---

# 🔁 **2. Training, Alignment & Safety**

### **9. Reinforcement Learning**

Models learn through rewards and penalties based on their actions.

---

### **10. RLHF**

Reinforcement Learning from Human Feedback.
Human evaluation guides the model toward better behavior.

---

### **11. Alignment**

Ensuring AI behaves according to human values, ethics, and safety guidelines.

---

### **12. Post-Training**

A general term referring to alignment and fine-tuning performed *after* base model training.

---

### **13. Agentic AI**

AI that can make decisions, choose tools, plan sequences of actions, and interact with external systems independently.

---

### **14. Workflows**

Defined sequences of steps or tools AI follows to solve tasks.

---

### **15. Agents**

AI systems managing their own processes, tool usage, and decision-making.

---

### **16. Multi-Agents**

Multiple AI agents collaborating, dividing tasks based on skills or roles.

---

---

# 🧩 **3. Design Concepts & Memory Systems**

### **17. Design Patterns**

Proven strategies and architectures for designing effective agent systems.

---

### **18. Agent Memory**

The ability of an AI agent to store and reuse past information for better performance.

---

### **19. Short-Term Memory**

Temporary memory within one session or task.

---

### **20. Long-Term Memory**

Persistent storage across sessions for retaining knowledge.

---

### **21. Procedural Memory**

Memory of *how* to perform tasks — similar to skills (e.g., "how to format a summary").

---

### **22. Cognitive Architecture**

The entire flow and structure that defines how an AI system processes instructions, data, decisions, and actions.

---

### **23. RAG (Retrieval-Augmented Generation)**

Enhancing LLM outputs with retrieved external knowledge.

---

### **24. Agentic RAG**

A smarter RAG system where the agent decides *when* and *what* to retrieve.

---

---

# 🔧 **4. Tools, Calling, and Interoperability**

### **25. Tools**

External functions the AI can call, such as calculators, APIs, or search engines.

---

### **26. Function Calling**

LLMs triggering external functions programmatically based on their reasoning.

---

### **27. MCP (Model Context Protocol)**

A framework for connecting AI systems to business tools and external environments.
Developed by **Anthropic**.

---

---

# 📤 **5. Output & Reasoning Structures**

### **28. Structured Outputs**

Responses must follow a predefined format (JSON, tables, fields).

---

### **29. CoT (Chain of Thought)**

AI breaks down its reasoning step-by-step to improve accuracy.

---

### **30. Test-Time Scaling**

Techniques that dynamically adjust an AI model’s depth of reasoning *during inference*.

Example: Allowing the model to think longer for harder problems.

---

### **31. ReAct**

Combines reasoning (thoughts) with actions (tool calls) in a loop before deciding the final answer.

---

### **32. Reflection**

AI reviews its own output, detects mistakes, and improves results.

---

---

# 🛠️ **6. Agent Behaviors & Architecture**

### **33. Self-Healing**

Agents detect and correct their own errors without human help.

---

### **34. LLM Judge**

A separate model used to evaluate outputs of another model to ensure quality.

---

### **35. Hybrid Models**

Models that combine test-time scaling with dynamic deep reasoning.

---

### **36. Chaining**

Breaking a task into multiple sequential steps, handled by different actions or tools.

---

### **37. Routing**

Directing tasks to different models, prompts, or tools depending on complexity.

---

### **38. Orchestrator**

A controller that manages multiple agents and tools to determine roles and execution order.

---

### **39. Vertical Agents**

Agents specialized in specific industries:
banking, healthcare, HR, retail, compliance, etc.

---

### **40. Overthinking**

A situation in Large Reasoning Models where too many reasoning steps cause token overuse or unneeded depth.
Mechanisms help **stop reasoning when enough information is available**.

---
