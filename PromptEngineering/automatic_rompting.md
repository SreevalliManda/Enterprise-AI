# Automatic Prompt Optimization: A Deep Dive

By the end of 2023—and even more so in 2024—we’ve seen a steep drop in basic prompting methods (level 1 and level 2). The reason is straightforward: why spend time mastering every trick of prompt optimization when you can automate the process? This shift has made way for two advanced approaches:

### Level 3: Meta Prompting/Prompting Engines
Imagine bypassing the need for manual optimization by embedding those techniques directly into a model. Meta prompts are built to steer the model toward generating effective prompts using proven best practices. For example, you can check out resources like [Anthropic's prompt generator](https://www.anthropic.com/) and [OpenAI's advanced usage documentation](https://platform.openai.com/docs/guides) . These models are sometimes even fine-tuned specifically to generate prompts. You can experiment with them on your own, and we’ll also do a live demo in class.

### Level 4: Algorithmic Optimization
Tools like DSPy take this a step further by decoupling the program’s flow from the individual parameters of each step. It introduces optimizers that fine-tune both prompts and weights based on specific metrics, allowing models like GPT-3.5, GPT-4, T5-base, or Llama2–13b to perform tasks with greater reliability and quality.

Note that tools like DSPy work with both closed-source and open-source language models via their API. This means you can effectively “wrap” a closed-source LLM in DSPy’s framework to build complex applications, even without direct access to the model’s inner workings.

Another option is Langgraph's function called `create_prompt_optimizer` that refines prompt quality through iterative optimization strategies. For more details, check out their [prompt optimization reference](https://docs.langgraph.com/docs/prompt-optimization) and explore this [blog post on different prompt optimization methods](https://www.langgraph.com/blog/prompt-optimization-methods).

---

