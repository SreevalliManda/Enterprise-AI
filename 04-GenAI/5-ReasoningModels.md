# Introduction: What Are LRMs?

Large Reasoning Models (LRMs) represent the next step in the evolution of AI, moving beyond simple text generation into structured reasoning and decision-making. While Large Language Models (LLMs) are designed to predict text based on statistical patterns, LRMs aim to simulate a true reasoning process. This enables them to tackle complex problem-solving, perform multi-step logical inference, and make decisions with greater consistency. Essentially, LRMs overcome LLM limitations by incorporating mechanisms to analyze, verify, and refine their outputs, closely aligning with human-like thought processes.

It started with OpenAI coming out as the first reasoning model that could “think,” and now we have many more, with the recent innovation being DeepSeek.

---

## What Issues Do LRMs Solve in LLMs, and at What Cost?

Like we discussed, as AI builders, our decisions are guided by four dimensions: cost, performance, effort, and latency.

Let’s review how LRMs address common LLM challenges:

### Solving Logical Consistency Issues:
LLMs can sometimes be inconsistent—correctly solving a math problem in one instance but failing when the problem is slightly reworded. LRMs counter this by engaging in self-verification and breaking problems down into multiple steps rather than relying solely on pattern matching. The tradeoff is that these extra internal reasoning steps demand more computational power, making LRMs more expensive.

### Reducing Hallucinations:
Another challenge with LLMs is their tendency to generate factually incorrect information with undue confidence—often referred to as “hallucination.” LRMs mitigate this by incorporating structured knowledge retrieval and cross-checking outputs before presenting them. This rigorous internal review leads to more reliable responses, though it also means longer generation times (increased latency) with improvements in performance.

### Improving Long-Horizon Decision Making:
LLMs struggle with tasks that require sustained, multi-step reasoning, such as strategic planning or complex troubleshooting. LRMs improve on this by maintaining logical consistency across several steps and using memory and planning frameworks to track progress over longer interactions. The cost here is higher training and inference expenses compared to conventional LLMs.

Basically, while LRMs are more resource-intensive and slower than LLMs, they excel in scenarios where improved performance and reasoning are crucial. For a builder using LRMs as an API tool, the additional effort is minimal—there are no new pain points compared to using LLMs, only better capabilities.

---

## Architectural Differences: How LRMs Are Built Differently

Let’s examine the architectural differences using the three stages we discussed in class: pretraining, supervised fine-tuning (SFT), and reinforcement learning (RL).

### Pretraining: A Shift Toward Reasoning Data
While LLMs are pretrained on vast, internet-scale corpora optimized for language fluency, LRMs integrate structured reasoning datasets from the start. These datasets include materials such as math proofs, formal logic exercises, and detailed chain-of-thought explanations. This allows LRMs to learn not only language patterns but also causal and counterfactual reasoning—forming a solid foundation for multi-step problem-solving.

### Supervised Fine-Tuning: Teaching Explicit Reasoning Steps
In traditional fine-tuning, LLMs learn from instruction-following datasets—tasks like summarization or Q&A—to align with user queries. LRMs, however, are fine-tuned on multi-step reasoning datasets that explicitly train the model to justify its answers step by step. They learn to cross-validate their outputs by questioning their own reasoning, ensuring that each answer is logically sound.

### Reinforcement Learning: Optimizing for Logical Correctness
LLMs typically use Reinforcement Learning from Human Feedback (RLHF) to adjust responses based on human preference rankings, with a focus on fluency and coherence. LRMs extend this concept by employing reinforcement learning strategies that reward logical correctness and structured reasoning. With internal verification loops, LRMs refine their responses continuously—prioritizing accuracy over mere surface-level appeal. This self-evaluation mechanism, which we touched on in class, marks a major departure from traditional models and is central to the robustness of LRMs.

---

## How LRMs Differ from LLMs: The Input-Output Framework

### Input Differences:
LLMs often require explicit prompting for reasoning; users might need to instruct them to “think step by step” or use “chain-of-thought reasoning.” LRMs, however, naturally engage in multi-step logical thinking, breaking down and analyzing input information systematically without extra cues.

### Output Differences:
When generating responses, LLMs predict the next most likely word based on learned patterns. This approach can result in plausible-sounding answers that sometimes contradict themselves or hallucinate facts. In contrast, LRMs produce structured reasoning steps, carefully evaluating and refining their answers before finalizing them. This leads to more reliable, coherent outputs—especially for tasks that require sustained logical analysis.

---

## DeepSeek’s Approach: Innovations in LRM Training

DeepSeek has introduced several novel techniques to push the boundaries of LRMs, exemplified by their models DeepSeek-R1-Zero and DeepSeek-R1.

### DeepSeek-R1-Zero:
This model takes a bold step by bypassing the initial supervised fine-tuning phase altogether. Instead, it employs reinforcement learning directly on the base model. This approach allows the model to explore chain-of-thought reasoning independently, developing self-verification and reflection abilities without relying on pre-labeled data. DeepSeek-R1-Zero demonstrates that robust reasoning capabilities can be achieved purely through RL.

### DeepSeek-R1:
Building on this, DeepSeek-R1 utilizes a multi-stage training pipeline that interleaves reinforcement learning and supervised fine-tuning. The process starts with a small amount of high-quality “cold start” data to stabilize the model and ensure coherent output. Then, two rounds of RL focus on discovering and refining complex reasoning patterns, followed by two rounds of supervised fine-tuning to reinforce the model’s language skills and its ability to justify each reasoning step. This layered approach results in a model that not only reasons effectively but also communicates its logic clearly and consistently.

If you remember, we discussed how model innovations are becoming a new science "aha" moments, where low cost and high performance innovations are key to utility and enterprise use. DeepSeek-R1 touches on both these areas, which is likely a major factor in its rising popularity.

> DeepSeek-R1 balances **low cost and high performance**, driving its popularity.

---

## Recommended Resources
- [The Illustrated DeepSeek-R1](https://newsletter.languagemodels.co/p/the-illustrated-deepseek-r1) 
- [Understanding Reasoning LLMs](https://sebastianraschka.com/blog/2025/understanding-reasoning-llms.html)

---

