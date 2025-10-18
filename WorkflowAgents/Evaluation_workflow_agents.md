# Evaluating Workflow Agents & Challenges

Once you've built your workflow agent use-case, the next big question is: How do you know it's working as intended? That’s where evaluation comes into play. You can assess these systems at two levels: at the task level—determining whether the final output meets your expectations—and at the intermediate output level, where you check whether each step in the process is on target.

Evaluation metrics can be broadly divided into two types: operational metrics and performance metrics.

---

## **Operational Metrics**

These metrics focus on the “nuts and bolts” of your workflow. They answer questions like:

**Time Taken:**
How long does it take on average to complete a task? For example, in a customer support routing workflow, you might measure the average time from when a query is received until it’s correctly assigned to the appropriate team.

**Cost Efficiency:**
What’s the projected cost of running the workflow—based on input and output tokens, compute time, and other resources? This is crucial when scaling up or operating under tight budget constraints.

By monitoring these operational aspects, you ensure that your workflow is not only effective but also efficient and scalable.

---

## **Performance Metrics**

Performance metrics dive into the quality of the outputs, both at the final stage and at intermediate steps. For proper evaluation, consider the following elements:

* **Input Prompts:** Both system and user prompts that set the stage for the workflow.
* **Output Results:** The final response produced by your workflow.
* **Intermediate Results:** The outputs from each step along the chain.
* **Ideal Results:** A benchmark or gold-standard output for each component.

You can then apply a combination of evaluation techniques:

---

### **Exact Match Metrics**

For tasks with a well-defined set of answers, such as in a customer support routing workflow where the output must match one category from a predefined list, exact match metrics are ideal. If the system’s classification perfectly aligns with the ground truth, it scores highly.

---

### **Traditional NLP (Natural Language Processing) Metrics**

For more free-form responses, traditional language metrics like BLEU can be useful. For example, when summarizing a medical report, you might measure how closely the generated summary aligns with a human-curated version. BLEU is a metric originally designed for machine translation; it compares a generated text to one or more reference texts by checking how many words or short phrases (known as "n-grams") match. The more matches there are, the higher the BLEU score, suggesting that the output is closer to what a human might produce. However, while BLEU provides a quick measure of quality, it may not fully capture the nuance or context-specific accuracy required for some tasks.

Another approach is to generate embeddings ([a short video explaining embeddings](https://www.youtube.com/watch?v=9xjmvUS-UGU))—numerical representations of text—for both the ideal results and the output. These embeddings capture the semantic meaning of the text, allowing you to compare them for similarity. In simple terms, if the embeddings of two texts are very close to each other in a mathematical space, it indicates that they convey similar meanings.

---

### **LLM Judges as Evaluators**

In enterprise settings, traditional metrics like BLEU or simple embedding similarity might not suffice, given the complexity and richness of the generated data. Word similarity alone often fails to capture context, style, and domain-specific nuances. In such cases, you can employ an LLM as an evaluator.

This LLM can be prompted with specific criteria, for example, checking whether the response includes an order number, adheres to the company’s communication style, or meets any other niche requirements. The LLM then scores the output based on these tailored evaluation questions, providing a more nuanced and context-aware assessment of the response quality.

Aishwarya has extensively discussed LLM judges and best practices for deploying them. You can check out her popular video from the 2024 MLOps World Summit for a deep dive into LLM judges in the next lesson — [Watch Here](https://www.youtube.com/watch?v=OB99E7Y1cMA).

---

## **Real-World Examples**

### **Customer Support Routing Workflow**

* **Operationally:** Measure how quickly and cost-effectively each query is routed.
* **Final Response Level:** Verify that the output exactly matches the pre-defined correct category using exact match metrics.
* **Intermediate Level:** Evaluate whether each subtask—such as parsing the query or extracting key features—is performed accurately, using traditional NLP metrics when the outputs are structured.
* **LLM Judges:** For free-form responses, use an LLM judge to assess the quality based on qualitative criteria like clarity, coherence, factual accuracy (or possibility of hallucinations), and adherence to guidelines.

---

### **Insurance Claims Processing Workflow**

* **Operationally:** Track the average time taken to process each claim—from submission to final decision—and calculate the cost per claim based on compute or token usage.
* **Final Response Level:** Check if the final decision (e.g., approve, reject, or flag for review) exactly matches the pre-defined correct category.
* **Intermediate Level:** Break down the process into individual subtasks, such as extracting key details (policy number, incident description, amount claimed) from claim documents, and compare these against a gold-standard using metrics like BLEU or ROUGE.
* **LLM Judges:** Use an LLM judge to ensure that the generated explanation adheres to legal standards and internal review policies, evaluating factors like the accuracy of cited policy details, logical consistency, and the completeness of the response.

---

Keep in mind that these metrics can be applied to a wide range of AI use cases, not just workflow agents. We'll also rely on them when evaluating our more complex applications.

---

## **Workflow Agents Common Challenges**

Workflow agents are excellent for building simple, determinate enterprise use cases and for testing the waters. However, they come with several challenges:

### **Hallucinations**

When a question falls outside the model's core expertise, it may hallucinate an answer. There are two types: one where the correct answer exists in the prompt but the model still fabricates a response, and another where the input context is insufficient, leading to inaccurate or invented outputs.

### **Prompt Hacking**

This occurs when malicious users manipulate input prompts to bypass safeguards or trigger unintended behaviors. Because generative AI systems operate based on the instructions given in the prompt, even slight alterations can lead to harmful or unpredictable outputs. This vulnerability requires robust input guardrails and ongoing monitoring to detect and mitigate such attacks.

### **Prompt Drift**

As generative AI models are continuously updated and optimized, the ideal prompt for a given task can change over time. This means that what worked yesterday might not yield the same results today, leading to inconsistent performance. Addressing prompt drift demands automated prompt optimization techniques and regular evaluation to ensure that the system remains effective and aligned with enterprise requirements.

We'll explore **Issue 1** — hallucinations — in greater detail in our upcoming lectures on enterprise systems and RAG (Retrieval-Augmented Generation).

Points 2 and 3, prompt hacking and prompt drift, are inherent challenges in generative AI systems (not just workflow agents) and we’ll talk a bit about them in our upcoming lectures on enterprise systems.

---



