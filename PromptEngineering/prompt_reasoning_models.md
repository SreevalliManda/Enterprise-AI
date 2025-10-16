# Prompting For Reasoning Models

## Lesson 5

Reasoning models are trained in a way that enable users to no longer need elaborate, meticulously crafted prompts, they generate their own chains of thought to break down problems more effectively.

Some examples include OpenAI's [o1](https://openai.com/research), [o3](https://openai.com/research) and [Deepseek-R1](https://deepseek.ai/). These systems are designed to autonomously develop internal reasoning processes, essentially handling much of the cognitive heavy lifting that traditional prompt engineering requires. Instead of relying on humans to define every nuance of a prompt, these models learn to interpret, deconstruct, and address complex tasks by generating their own step-by-step solutions.

This evolution not only streamlines the process but also democratizes access to advanced AI capabilities, reducing the barrier to entry for leveraging sophisticated models in real-world applications.

Reasoning models are built to do more than just spit out a final answer, they’re designed to break down problems by generating a chain of thought, effectively mimicking human internal reasoning. Here’s how they do it:

### Internal Decomposition of Problems
Rather than being fed a fully detailed prompt, these models are trained on data that includes intermediate reasoning steps. When faced with a complex query, they begin by decomposing the problem into smaller, manageable parts. This isn’t just a list of bullet points—it’s a dynamic, internally generated narrative that leads to the final answer.

### Step-by-Step Processing
Consider how you might solve a challenging math problem: you first break it down into simpler equations, work through each step, and then synthesize your findings into the final solution. Reasoning models work similarly. They generate a “chain of thought” where each step logically follows from the previous one. This sequence helps them navigate through ambiguity and reach a more accurate conclusion.

### Examples in Practice
- **Mathematical Problem Solving:** When asked a multi-step math question, a reasoning model might first outline the formula or theorem needed, then identify the relevant variables, compute intermediate results, and finally combine these elements to produce the answer.  
- **Complex Decision Making:** For a scenario-based question, the model might generate a series of “if-then” logical steps—evaluating pros and cons at each stage—before arriving at a decision. This mirrors how a human expert might weigh different factors before making a call.  
- **Natural Language Understanding:** When handling ambiguous language queries, the model can internally debate different interpretations. It sifts through multiple possibilities in its chain of thought and ultimately selects the most coherent answer.

From the previous lessons and section, it’s clear that you don’t need to master prompt engineering in extreme detail to work effectively with generative models. However, learning some basics can go a long way in understanding how these models function and what to expect from them. Here’s a straightforward guide, drawn from OpenAI’s best practices, to help you decide when to use reasoning models versus non-reasoning models and some prompting tips drawn from OpenAI's best practices for reasoning models.

### Reasoning Models vs. Regular Models (e.g., o1/GPT-5 Thinking vs. GPT-4o)
#### Different Strengths for Different Tasks
**Reasoning Models (“The Planners”):**  
These models are built to think long-term and dive deep into complex challenges. They excel at:  
- **Strategic Planning:** Breaking down multi-step problems and managing ambiguity.  
- **High Accuracy:** Ideal for fields where precision matters—math, science, engineering, finance, legal, etc.  
- **Visual Reasoning:** Some, like [o1](https://openai.com/research), even handle tricky visuals such as ambiguous charts or low-quality images.  

**Regular Models (“The Workhorses”):**  
Designed for speed and cost-efficiency, these models (like GPT-4o) are perfect when you need:  
- **Rapid Responses:** Fast, cost-effective answers.  
- **Efficient Task Execution:** Great for clearly defined, straightforward tasks.

### How to Choose the Right Model
Ask yourself: What’s most important for your use case?  

- **Speed and Cost:** If quick, budget-friendly responses are your top priority, go with regular models.  
- **Executing Well-Defined Tasks:** For tasks with clear, explicit requirements, regular models handle them like a champ.  
- **Accuracy and Reliability:** When precision is non-negotiable, reasoning models are your trusted decision makers.  
- **Complex Problem-Solving:** For multi-step problems and ambiguous challenges, reasoning models work through the complexity with ease.  

Often, the best approach is a hybrid one: use reasoning models for strategic planning and regular models for execution.

### When to Use Reasoning Models
Based on real-world feedback and internal tests, here are some scenarios where reasoning models truly shine:  

- **Navigating Ambiguous Tasks:** They’re great at interpreting limited or scattered information and will ask clarifying questions rather than making wild guesses.  
- **Finding a Needle in a Haystack:** When dealing with large amounts of unstructured data, they can sift through and extract only the most relevant information.  
- **Uncovering Relationships in Large Datasets:** Whether it’s dense legal contracts, financial statements, or insurance claims, reasoning models can draw parallels and make informed decisions from complex documents.

### Tips for Prompting Reasoning Models
To get the best results, keep these best practices in mind:  

- **Keep It Simple and Direct:** Brief, clear instructions work best.  
- **Skip the “Chain-of-Thought” Prompts:** These models handle internal reasoning on their own—no need to instruct them to “think step by step.”  
- **Use Clear Delimiters:** Organize your input with markdown, XML tags, or section titles to keep things structured.  
- **Start with Zero-Shot:** Most reasoning models perform well without examples. Add a few only if absolutely necessary.  
- **Set Specific Guidelines:** Outline any constraints (e.g., “propose a solution with a budget under $500”) to keep the output on track.  
- **Define Your End Goal:** Clearly state what success looks like, so the model iterates until it meets your criteria.  
- **Formatting Note:** As of version o1-2024-12-17, reasoning models avoid markdown formatting by default. To re-enable it, include “Formatting re-enabled” at the start of your developer message.

### Advanced Use Cases
- **Multi-Step Agentic Planning:** Use reasoning models as planners to generate detailed, multi-step solutions. Then, hand off specific tasks to regular models (“the doers”) based on whether intelligence or speed is more critical.  
- **Visual Reasoning:** Currently, [o1](https://openai.com/research) is the only reasoning model with vision capabilities. It can tackle challenging visuals—interpreting ambiguous charts, tables, or low-quality images by transferring context effectively across a dataset.  
- **Code Review and Debugging:** These models can review and refine large volumes of code, performing background analyses to improve overall code quality.

---

