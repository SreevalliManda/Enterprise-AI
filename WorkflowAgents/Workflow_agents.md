# Workflow Agents in the Enterprise (Popular Architectures & Examples)

We learned quite a bit about prompting LLMs in the last lesson. By orchestrating LLMs in defined workflows, we can build end-to-end use cases—what many call workflow agents (or, in some circles, “agentic” systems). But let’s not get bogged down in the terminology.

There are several popular design patterns for building workflow agents. Below are a few examples. Keep in mind, these aren’t the only options—you can always invent your own. The key idea is that in workflows, you’re the one doing the planning. AI models are here to understand and generate knowledge; planning is up to you.

---

## Workflow: Prompt Chaining

Prompt chaining breaks a task into a sequence of steps, where each LLM call processes the output from the previous one. You can also add programmatic checks (the “gate” in the diagram) at any stage to ensure the process stays on track.

**When to Use It:**
Ideal for tasks that can be neatly divided into fixed subtasks. This approach trades off latency for higher accuracy, as each LLM call becomes a simpler, more manageable task.

### Enterprise Use-Cases:

**Healthcare**

* Treatment Plan Development: review patient history, identify key risk factors, and craft treatment strategies.
* Medical Report Summarization: sequentially summarize clinical notes, lab reports, and imaging findings into concise summaries.

**Supply Chain**

* Order Processing: verify order details, check inventory, confirm shipping schedules.
* Supplier Evaluation: assess performance metrics and quality to rank suppliers.

**Manufacturing**

* Process Improvement: analyze production data, identify bottlenecks, and suggest improvements.

**Marketing**

* Campaign Strategy Development: conduct market research, segment audiences, and design cohesive messaging.
* Content Generation: generate headlines, supporting copy, and CTAs sequentially for consistency.

---

## Workflow: Routing

Routing involves classifying an input and directing it to a specialized follow-up task. This design separates concerns by allowing you to build specialized prompts tailored for different input categories. Without routing, optimizing for one type of input might hurt performance on others.

**When to Use It:**
Best for complex tasks involving distinct categories. Routing enhances performance when inputs can be accurately classified.

### Enterprise Use-Cases:

**Healthcare**

* Triage Systems: classify patient symptoms and route to relevant departments (cardiology, neurology, etc.).
* Insurance Claims Processing: direct claims to appropriate review teams by procedure type.

**Finance**

* Customer Support: classify and route client queries to specialized departments for accuracy and speed.

---

## Workflow: Parallelization

LLMs can sometimes work on tasks simultaneously, with their outputs aggregated programmatically.

**Forms:**

* **Sectioning:** Split a task into independent subtasks.
* **Voting:** Run the same task multiple times to gather diverse outputs.

**When to Use It:**
Effective for speeding up tasks or gathering multiple perspectives for reliability.

### Enterprise Use-Case:

**Marketing:**

* Campaign Performance Monitoring: analyze click-through rates, engagement, and conversions in parallel to optimize strategy dynamically.

---

## Workflow: Orchestrator-Workers

In this pattern, a central LLM (the orchestrator) dynamically breaks down tasks, delegates them to worker LLMs, and synthesizes the results.

**When to Use It:**
For complex, unpredictable tasks like code refactoring or content generation where subtasks vary based on input. The orchestrator determines and manages task flow dynamically.

---

When designing your workflows, always ask yourself:
**“What’s the best performance I can achieve with this system?”**
The answer depends on your data, the task, and how you balance speed, cost, and accuracy. These workflow patterns are simple yet powerful tools to get you started—and with creativity, you can tailor them to any enterprise need.

Think about use cases in your industry that could benefit from these workflows—or invent new ones!

---

**Images & Terms courtesy of:**
👉 [Anthropic: Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents)

---


