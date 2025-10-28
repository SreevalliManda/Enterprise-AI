## Model Memory & Agents

**Q:** Could you explain the statement "An ML model has no inherent memory, it is naturally stateless" - so what is memory in an agent?  
**A:** When we say an ML model has no inherent memory, it means the model doesn't actually remember past conversations. When you chat with ChatGPT and it seems to understand context, that's because the model provider (not the model itself) stores your conversation history in a database and injects your past conversations into each new query sent to the model.  
In agents, memory works the same way - you retrieve relevant past conversations or information and artificially add it to the context when calling the model. One core way to do this is using **Retrieval Augmented Generation (RAG)**.  
There are different types of memory abstractions (episodic memory, procedural memory), but fundamentally, it's always artificial injection via context, not the model actually "remembering."

The key distinction: The model API call itself is stateless. Products like ChatGPT have extensive engineering behind the scenes to manage conversations, attach files, and provide memory across different conversations. In your assignments, you'll be using the model APIs directly, not the full ChatGPT application.

---

## Document Uploads & Context

**Q:** When you upload documents or PDFs to ChatGPT, is that content also sent multiple times to retain context? Wouldn't it be more efficient to use a temporary document store with a pointer?  
**A:** For small files that fit within the context window, ChatGPT simply dumps the entire file into the context. However, for large enterprise use cases, it wouldn't make sense to feed everything into context. That's what **RAG** is for — you only retrieve and feed relevant information.  
Even for conversation memory, when you have thousands of turns, model providers use compression and retrieval techniques for optimization.  

---

**Q:** Does ChatGPT remember everything I say across all my conversations, including in projects?  
**A:** There are two distinct things:  
- The model (stateless API)  
- The product (ChatGPT) which manages long conversations, memory, and attachments.  
ChatGPT stores your conversations and sends relevant history with each query, but the model itself doesn’t “remember.”  

---

**Q:** When uploading 20 files to ChatGPT Projects or Claude projects, how do those apps handle processing those files? Also, how does Claude.md work when I update it?  
**A:**  
- **Multiple files:** Uses RAG — retrieves key parts from your files and sends only relevant info to the model.  
- **Claude.md:** This is context engineering — the system pastes your Claude.md content and system prompts before your query and sends that combined context to the model.  

---

## Tokens, Context, and RAG

**Q:** With token limits on models, is it possible to pass large conversation histories as context?  
**A:** This is where **RAG** and memory optimization come in — retrieval helps you stay within token limits.  

**Q:** ChatGPT apps don’t seem to do RAG — how is the increased context length managed?  
**A:**  
1. **Increased context windows** (GPT-4o has 400K+ tokens).  
2. **Context optimization** — compressing and prioritizing relevant content.  

---

## Model Temperature

**Q:** How do developers choose the right temperature (T)?  
**A:**  
- For agentic/enterprise apps → keep temperature **0** for consistency.  
- For creative tasks (marketing, storytelling, art) → higher temperatures make sense.  
Temperature affects randomness, not hallucination.  

---

## Fine-Tuning, RLHF, and Training

**Q:** Is RLHF a form of supervised learning that follows fine-tuning?  
**A:** Yes, RLHF uses human preference supervision. It often follows fine-tuning but not always. Fine-tuning optimizes exact labels; RLHF aligns behavior to human preferences.  

**Q:** Does fine-tuning always follow RLHF?  
**A:** Not necessarily. Enterprises may fine-tune on specific data while retaining RLHF knowledge.  

**Note:**  
- Fine-tuning = label optimization.  
- RLHF = preference optimization.  

---

## Evals (Evaluations)

**Q:** What kinds of evals are covered?  
**A:** Domain-specific, semantic, and code-based evals. Examples:  
- Helpfulness  
- Accuracy  
- Routing correctness  
- Precision/recall where relevant  

---

## RAG vs Fine-Tuning

**Q:** When should we decide to use RAG versus fine-tuning?  
**A:**  
- RAG → when model lacks external data access  
- Fine-tuning → when model lacks domain or style knowledge  

**Q:** Is RAG always about vector databases?  
**A:** No. RAG simply means *retrieve and augment*. Retrieval can use:  
- Vector databases  
- Keyword search  
- Hybrid search  

---

## Temperature & Hallucination

**Q:** Does temperature 0 mean no hallucination?  
**A:** No. Temperature affects creativity, not factuality. Hallucination happens when the model lacks relevant knowledge.  

---

## Prompting vs Fine-Tuning

**Q:** Can strong prompting replace fine-tuning?  
**A:** Yes — often.  
If you haven’t fully optimized prompts, don’t fine-tune yet.  
Fine-tuning should be last resort (niche domain, style-heavy use case).  
Fine-tuning is expensive, irreversible, and requires clean data.  

---

## Fine-Tuning Costs & Scenarios

**Q:** Does fine-tuning have costs?  
**A:** Yes. Inference becomes more expensive. Fine-tuned models aren’t transferable to new model versions.  

**Q:** When does fine-tuning make sense?  
**A:**  
- Indigenous/new languages  
- New programming languages  
- Domain-specific stylistic needs  

---

## Inference

**Q:** What is inference?  
**A:**  
- **Training:** Updates model weights  
- **Inference:** Uses frozen model to generate outputs  
All usage of GPT-4o, Gemini, etc., is inference.  

---

## Model Comparisons

**Q:** Are GPT-4o and Gemini different enough to switch?  
**A:** Not significantly.  
- Enterprises choose based on contracts, not performance.  
- Personal users may prefer style or tone differences.  
Performance across similar price tiers is nearly identical.  

**Q:** What about Claude vs GPT coding agents?  
**A:** Preference-based. Claude is more hands-on, GPT slower but detailed. Both comparable in ability.  

---

## Repeated Themes & Best Practices

### On Model Memory & Context
- Models are stateless; memory is engineered externally.  
- Memory = retrieved + injected context, not stored inherently.  

### On Evaluations
- Every new component → needs an eval.  
- Evals are expensive and domain-specific.  

### On Fine-Tuning
- Exhaust prompt engineering first.  
- Fine-tuning only after data flywheel maturity.  

### On Model Selection
- Similar price → similar performance.  
- Style/preferences differ slightly.  
- Enterprises pick based on existing contracts.  

### On Data & Annotation
- SMEs are valuable but costly.  
- Hybrid approach: AI generates → SMEs verify.  
- Synthetic data helps anticipate queries.  
- Iterative improvement is key.  
- Expect distribution shifts.  

---


