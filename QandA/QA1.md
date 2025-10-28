# AI Systems: Key Questions, Answers & Best Practices

---

## Q&A

### Q: In the post-training phase, how do benchmarking eval results and the reward model work together?
**A:** Evaluation results and reward models serve different purposes. The reward model is part of the reinforcement learning process during training — it mimics human feedback and provides rewards to continuously improve the model. Evaluations, on the other hand, are offline tests conducted after the model is ready and training is complete. Think of evals as your final tests that measure performance, while the reward model is an active component during the training phase itself. They are two separate things, not inputs to each other.

---

### Q: Which no-code tools are most popular in the market today?
**A:** N8N (also written as N-A-T-E-N) is quite popular. It existed before the AI boom as a workflow automation tool (similar to Zapier) and adapted well to AI by allowing model calls and tool calls within orchestrations. However, N8N treats many components as black boxes, which isn't ideal for learning. OpenAI's new agent builder is very early stage. Flowise is another framework mentioned. The key is that for learning purposes, you want tools that help you understand the modules clearly rather than treating them as black boxes.

---

### Q: When you say iterative development, how do you structure those iterations? Are you iterating on the prompt, the data, the model, or the overall workflow?
**A:** Iterative development is about capabilities, not individual components. Think of it like the Aiden/Langchain example — you divide capabilities into smaller parts and build a data flywheel to understand behavior over time. Instead of building a completely autonomous system that makes decisions on your behalf, break down the problem into cognitive capabilities and slowly increase the agency of the system. It’s similar to feature prioritization in software systems, but here your agents make decisions, so you need to be more careful. Changes to the model, prompt, or data are just means to achieve a particular capability. Focus on the problem and how to break it down, not on the components themselves.

---

### Q: Is iterative development synonymous with an MVP-based approach?
**A:** Yes, very similar, but the MVP should depend on the cognitive capabilities of the LLM model. Once you've learned about RAG, autonomous agents, and multi-agent systems in Week 3, you'll build a better intuition for how to break down problems. This is exactly what you'll practice in your capstone project.

---

### Q: Can you explain evaluation-driven development and how it relates to iterative development?
**A:** Evaluation-driven development means: start simple and increase complexity only as your evals indicate you should. Don’t dump all your fancy RAG techniques or prompt engineering methods into version one. Build the simplest possible system first, then let your evals guide what needs improvement. Iterative solution design is a superset of this — it adds another layer by breaking solutions into capabilities. Think of your AI system as an intern learning over time — don’t grant it too much agency and power upfront. Evaluation is the driving force, but iteration based on capabilities is the framework.

---

### Q: Should we think about iteration at the capability level because the prompt, data, and model are all in service of that capability?
**A:** Exactly right. Many people today are too focused on implementation details — what prompt to use, which RAG technique to apply. The problem-first approach means if you have good intuition about what problem to solve with AI, you focus on building a system to solve that problem. Everything else — your prompt, model, data — should be tools you use to solve that problem, not the end goal itself.

---

### Q: Have you observed any exceptions to the iterative development rule?
**A:** The main exception is when you need to build something quickly — that’s when “vibes-driven development” kicks in (ship what looks good). However, if you want a robust product that teams can iterate on quickly, you need to follow iterative development. The scope and rigor depend on context: if you’re moving quickly with high error tolerance, you can reduce the metrics you care about. But if you’re legally liable for errors, you need to be more careful. Contextualize based on your risk appetite.

---

### Q: Is it fair to say we're in a discovery loop, trying to discover agent capabilities in our domain before giving it more agentic behavior?
**A:** Exactly. It’s a discovery phase, like evaluating an incredibly smart intern in your context. You’re understanding how well it’s doing and what gaps need to be filled — whether through prompt changes, adding new tools, or bringing in better models. The term “calibration” is frequently used by enterprise practitioners — you’re constantly calibrating a base model to your domain through different methods.

---

### Q: Regarding data hygiene in enterprises — do most traditional industries have data problems, and how does data connectivity happen during iterative development?
**A:** Data hygiene is one of the biggest problems in enterprises. Companies often aren’t data-ready — there’s conflicting information, improper processing, lack of rule-based access controls, etc. Everyone wants to build RAG solutions for enterprise search, but their data isn’t ready. Before starting, there needs to be basic data hygiene and a data readiness check. Even after starting, you’ll discover issues and can find fixes along the way. However, if they don’t even have a baseline data layer, you need to build that first before moving to the agentic part.

---

### Q: How many iterations typically does it take to solve a problem, and what's the time cycle?
**A:** With AI products, iteration never truly stops — it just reduces in frequency. Initially, you’re adding capabilities with many iterations until you reach feature complete. After that, the cadence reduces (perhaps to monthly reviews), but you continue monitoring because AI systems open up a huge surface area for natural user interactions. You need ongoing monitoring and improvements. For example, building a customer support agent for a mid-market company took about 8 months to reach production-ready reliability.

---

### Q: Can you elaborate on continual pre-training versus fine-tuning?
**A:** Continual pre-training takes a pre-trained model and improves language capabilities and nuanced understanding (not task capabilities). You’d use continual pre-training to teach a model a new language or domain-specific language nuances. Fine-tuning is for specific tasks — like teaching a model that knows English to perform summarization or question answering.  
- **Pre-training:** Language structure  
- **Fine-tuning:** Task performance

---

### Q: Based on the funnel diagram, Gen AI is a subset of ML. Could you explain how ML serves as a superset?
**A:** Machine learning refers to any algorithms that take input data, learn from it, and produce outputs. This includes classification, regression, and other problem types. Generative AI is a subset because it does the same thing but specifically for generation tasks. So ML is the broader category, and Gen AI is a smaller subset focused on generation.

---

### Q: You mentioned there are other generative AI models, not just LLMs. What are those?
**A:** Other generative AI models include video generation models, image generation models, and audio generation models. LLMs are only language models that generate text. Generative AI can work with other modalities like audio, video, and images as well.

---

### Q: Are the four AI use case paradigms mutually exclusive, or can a single use case span multiple paradigms?
**A:** They’re not mutually exclusive — a single use case can span multiple paradigms. Never look at these as four different choices — take the bigger problem and plug in these paradigms as required.

---

### Q: Are there defined levels or degrees of hallucination in AI models?
**A:** Yes — intrinsic vs. extrinsic hallucinations:  
- **Intrinsic:** Twisting real facts (e.g., wrong date)  
- **Extrinsic:** Creating new facts (completely made-up).  
Intrinsic ones are easier to fix via better fact lookup (RAG), while extrinsic ones need more constrained prompts.

---

### Q: What strategies can reduce the performance gap between offline evaluation and online deployment?
**A:**  
1. Accept that a gap will always exist.  
2. Treat evals themselves as iterative.  
3. Keep the risk profile low by increasing capabilities gradually.  
4. Build proper human handoff systems.  
Focus on **system-level reliability**, not just model accuracy.

---

### Q: How do we determine when a system is ready for production?
**A:** You can only estimate production readiness — never be 100% sure. Use SME input to model real-world queries, test incrementally, and keep human handoff in place. The process is iterative and risk-managed.

---

### Q: Should all capabilities be built before moving to production, or should we build iteratively in production?
**A:** Build **iteratively in production**. Start with human-overridable capabilities and gradually increase autonomy as performance stabilizes.

---

### Q: When iterating, should I train the model or look for new models if the system isn't giving 100% results?
**A:** You should **almost never train your own model** in enterprise apps.  
- 80% of issues are solved by better **context engineering**.  
- Only switch models or fine-tune after exhausting context-related fixes.

---

### Q: When should we stop the iterative model selection process?
**A:** When your **evaluation metrics** meet your **business requirements**. Keep iterating as long as gaps remain between expected and actual outcomes.

---

### Q: What should we do if the system starts degrading after 3 months in production?
**A:** Maintain **continuous monitoring** and **iterative evaluation**. Regular weekly or bi-weekly evals help detect issues early. If new patterns emerge, update test cases and retrain context understanding.

---

### Q: Wouldn't you use RAG for product-specific information and to avoid the cost of fine-tuning?
**A:** Yes — that’s covered in detail in later material. You’re on the right track.

---

### Q: Regarding human review — what's the right way to determine when a response needs human review?
**A:** It’s domain-specific. Base it on:  
- Existing escalation rules  
- Data confidence levels  
- Organizational policies  
Sensitive or uncertain responses should always be escalated. Define what’s acceptable vs. not acceptable for your context.

### 1. Problem-First, Not Tool-First
- Don’t be “tool-obsessed.” Focus on concepts.  
- Tools are means, not goals.  
- Understanding one tool helps you master others.

---

### 2. Iterative Development is Continuous
- Iteration never stops — just slows down.  
- Start simple, grow with eval feedback.  
- Break problems into cognitive capabilities.  
- Treat AI systems as interns learning over time.

---

### 3. Evaluation is Critical
- Evals drive iteration.  
- Treat evals as iterative too.  
- Always have evals before declaring production-ready.

---

### 4. Context Engineering Over Model Training
- 80% of issues are solved via context, not new models.  
- Start mid-tier, upgrade only when needed.  
- Rarely train models from scratch.

---

### 5. Human-in-the-Loop Design
- Begin with human-overridable capabilities.  
- Build strong handoff systems.  
- Gradually increase autonomy.

---

### 6. Data Readiness is Foundational
- Enterprises often lack clean data.  
- Conduct readiness checks first.  
- Build data layers before agentic systems.  
- Use metadata search and prioritization for imperfect data.

---

### 7. Managing Expectations
- Building reliable AI systems takes time (e.g., 8 months).  
- Expect performance gaps between offline & online.  
- SMEs are essential for domain-specific insight.

---

### 8. Risk Management
- Increase capabilities gradually.  
- Define acceptable vs. unacceptable risks.  
- Larger organizations require more rigor; startups can experiment more.

---
