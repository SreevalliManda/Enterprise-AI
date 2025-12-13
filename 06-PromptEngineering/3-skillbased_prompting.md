# Skill Based Prompting : 

### Level 1: In-Context Learning

In-Context Learning involves teaching large LLMs or generative AI models through prompts rather than traditional training methods. The idea is to provide the model with instructions, examples, and context directly in the prompt to guide its output.

- **Zero-Shot:** Ask the LLM to answer without providing examples. For instance, "Explain the concept of blockchain in simple terms."
- **Few-Shot:** Include a few examples in your prompt to reliably guide the model. For example, when translating sentences, show two examples before asking for a translation.
- **Role-Based Prompts:** Define a role to set the context. For example, "You are a financial analyst. Explain the impact of interest rate changes on stock markets."
- **Keep It Simple:** Use clear, straightforward language to avoid confusion.
- **Comprehensive Explanation:** Share all relevant details so the model has enough context, reducing ambiguity in its responses.
- **Avoid Bias:** Craft prompts that steer clear of encouraging sycophantic or overly agreeable answers.
- **Natural Tone:** Instruct the model to respond in a conversational and accessible tone.

Everyone should learn basic in-context learning principles. Also remember that, in most applications, a prompt consists of two key components: the system prompt and the user prompt.

- **System Prompt:** The system prompt consists of hidden instructions provided to the model before it sees any user input. These instructions establish the overall context, tone, and rules that guide the AI’s behavior throughout the conversation.  
  *Example:* In a banking support system, the system prompt might state, "Answer banking questions only, be friendly." This ensures that regardless of the user's query, the model adheres to a specific behavior—staying within the banking domain, maintaining a friendly tone, and avoiding off-topic responses. The system prompt is typically injected into the context via API calls or configuration settings and is not visible to the end user.

- **User Prompt:** The user prompt is the visible query or message that the user types, which the AI then responds to. When integrating with API wrappers, the user prompt is combined with the system prompt to form the full context that the AI uses to generate its response. This separation allows developers to tailor the hidden instructions independently of the user’s direct input, ensuring consistent and controlled behavior.

### Level 2: Advanced Prompting Methods

From 2022 to 2024, over 100 advanced prompting research papers were published. These can broadly be grouped into three major categories: Thought Generation and Reflection, Decomposition, and Ensembling. They are designed to improve the quality and consistency of AI responses, though they also introduce additional considerations regarding effort, performance, cost, and latency. Below, we tag a few popular ones for each category. You don't need to master every advanced prompting technique, instead, focus on understanding the high-level overview. Most of these skill based techniques can now be optimized more efficiently (we'll learn more in the next lesson).

#### Thought Generation and Reflection

- **Chain-of-Thought (CoT) Prompting:** Encourages the model to “think aloud” by generating a series of intermediate reasoning steps. Improves performance on math word problems and logical reasoning.  
  [Paper: Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903) by Jason Wei et al.

- **Tree-of-Thought (ToT) Prompting:** Allows the model to explore multiple reasoning paths in a tree-like structure. Enables backtracking and evaluation of strategies for complex problems.  
  [Paper: Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://arxiv.org/abs/2305.10601) by Shunyu Yao et al.

- **ReAct Pattern (Reasoning+Acting):** Interleaves reasoning steps with action steps, allowing reflection and task execution.  
  [Paper: ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629) by Shunyu Yao et al.

- **Active Prompting with Chain-of-Thought:** Selects the most informative examples for prompting to ensure task-relevant reasoning.  
  [Paper: Active Prompting with Chain-of-Thought for Large Language Models](https://arxiv.org/abs/2302.11382) by Diao et al.

#### Decomposition

- **Least-to-Most Prompting:** Solve simpler sub-problems first, then progressively tackle more complex ones.  
  [Paper: Least-to-Most Prompting Enables Complex Reasoning in Large Language Models](https://arxiv.org/abs/2205.10625) by Denny Zhou et al.

- **Decomposed (DecomP) Prompting:** Break complex tasks into distinct sub-tasks and solve them independently.  
  [Reference: Decomposed Prompting: A Modular Approach for Solving Complex Tasks](https://arxiv.org/abs/2301.10342)

- **Plan-and-Solve Prompting:** Plan a sequence of steps first, then execute each step sequentially.  
  [Paper: Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought Reasoning](https://arxiv.org/abs/2305.15346) by Lei Wang et al.

- **Recursive Task Decomposition:** Break down a task recursively until all sub-tasks are manageable.  
  [Paper: Recursion of Thought: A Divide and Conquer Approach to Multi-Context Reasoning with Language Models](https://arxiv.org/abs/2302.03620) by Soochan Lee and Gunehee Kim.

#### Ensembling

- **Self-Consistency for Chain-of-Thought (CoT):** Generate multiple reasoning paths and select the final answer by majority voting.  
  [Paper: Self-Consistency Improves Chain of Thought Reasoning in Language Models](https://arxiv.org/abs/2203.11171) by Xuezhi Wang et al.

- **Active Prompting and Ensemble of Prompts:** Combine multiple diverse prompts or use meta-prompts to aggregate reasoning.  
  [Related Work: Active Prompting with Chain-of-Thought](https://arxiv.org/abs/2302.11382) by Diao et al.

---

