# Opik Evaluation Metrics

https://www.comet.com/docs/opik/evaluation/metrics/overview/?from=llm&utm_source=opik&utm_medium=github&utm_content=metrics_2_link&utm_campaign=opik
Opik provides a set of built-in evaluation metrics that you can mix and match to evaluate LLM behaviour. These metrics are broken down into two main categories:

* **Heuristic metrics** – deterministic checks that rely on rules, statistics, or classical NLP algorithms.
* **LLM as a Judge metrics** – delegate scoring to an LLM so you can capture semantic, task-specific, or conversation-level quality signals.

Heuristic metrics are ideal when you need reproducible checks such as exact matching, regex validation, or similarity scores against a reference.
LLM as a Judge metrics are useful when you want richer qualitative feedback (hallucination detection, helpfulness, summarisation quality, regulatory risk, etc.).

---

## **Built-in metrics**

### **Heuristic metrics**

| **Metric**         | **Description**                                                             | **Documentation**                                                                           |
| ------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| BERTScore          | Contextual embedding similarity score                                       | [BERTScore](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#bertscore)                   |
| ChrF               | Character n-gram F-score (chrF / chrF++)                                    | [ChrF](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#chrf)                             |
| Contains           | Checks whether the output contains a specific substring                     | [Contains](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#contains)                     |
| Corpus BLEU        | Computes corpus-level BLEU across multiple outputs                          | [CorpusBLEU](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#bleu)                 |
| Equals             | Checks if the output exactly matches an expected string                     | [Equals](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#equals)                         |
| GLEU               | Estimates grammatical fluency for candidate sentences                       | [GLEU](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#gleu)                             |
| IsJson             | Validates that the output can be parsed as JSON                             | [IsJson](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#isjson)                         |
| JSDivergence       | Jensen–Shannon similarity between token distributions                       | [JSDivergence](https://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#jsdivergence)             |
| JSDistance         | Raw Jensen–Shannon divergence                                               | [JSDistance](hhttps://www.comet.com/docs/opik/evaluation/metrics/heuristic_metrics#jsdistance)                 |
| KLDivergence       | Kullback–Leibler divergence with smoothing                                  | [KLDivergence](https://www.comet.com/docs/opik/evaluation/metrics/kldivergence)             |
| Language Adherence | Verifies output language code                                               | [Language Adherence](https://www.comet.com/docs/opik/evaluation/metrics/language-adherence) |
| Levenshtein        | Calculates the normalized Levenshtein distance between output and reference | [Levenshtein](https://www.comet.com/docs/opik/evaluation/metrics/levenshtein)               |
| Readability        | Reports Flesch Reading Ease and FK grade                                    | [Readability](https://www.comet.com/docs/opik/evaluation/metrics/readability)               |
| RegexMatch         | Checks if the output matches a specified regular expression pattern         | [RegexMatch](https://www.comet.com/docs/opik/evaluation/metrics/regexmatch)                 |
| ROUGE              | Calculates ROUGE variants (rouge1/2/L/Lsum/W)                               | [ROUGE](https://www.comet.com/docs/opik/evaluation/metrics/rouge)                           |
| Sentence BLEU      | Computes a BLEU score for a single output against one or more references    | [SentenceBLEU](https://www.comet.com/docs/opik/evaluation/metrics/sentencebleu)             |
| Sentiment          | Scores sentiment using VADER                                                | [Sentiment](https://www.comet.com/docs/opik/evaluation/metrics/sentiment)                   |
| Spearman Ranking   | Spearman’s rank correlation                                                 | [Spearman Ranking](https://www.comet.com/docs/opik/evaluation/metrics/spearman-ranking)     |
| Tone               | Flags tone issues such as shouting or negativity                            | [Tone](https://www.comet.com/docs/opik/evaluation/metrics/tone)                             |

---

### **Conversation heuristic metrics**

| **Metric**          | **Description**                                                                 | **Documentation**                                                                             |
| ------------------- | ------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| DegenerationC       | Detects repetition and degeneration patterns over a conversation                | [DegenerationC](https://www.comet.com/docs/opik/evaluation/metrics/degenerationc)             |
| Knowledge Retention | Checks whether the last assistant reply preserves user facts from earlier turns | [Knowledge Retention](https://www.comet.com/docs/opik/evaluation/metrics/knowledge-retention) |

---

### **LLM as a Judge metrics**

| **Metric**                      | **Description**                                                   | **Documentation**                                                                                         |
| ------------------------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| Agent Task Completion Judge     | Checks whether an agent fulfilled its assigned task               | [Agent Task Completion](https://www.comet.com/docs/opik/evaluation/metrics/agent-task-completion)         |
| Agent Tool Correctness Judge    | Evaluates whether an agent used tools correctly                   | [Agent Tool Correctness](https://www.comet.com/docs/opik/evaluation/metrics/agent-tool-correctness)       |
| Answer Relevance                | Checks whether the answer stays on-topic with the question        | [Answer Relevance](https://www.comet.com/docs/opik/evaluation/metrics/answer-relevance)                   |
| Compliance Risk Judge           | Identifies non-compliant or high-risk statements                  | [Compliance Risk](https://www.comet.com/docs/opik/evaluation/metrics/compliance-risk)                     |
| Context Precision               | Ensures the answer only uses relevant context                     | [Context Precision](https://www.comet.com/docs/opik/evaluation/metrics/context-precision)                 |
| Context Recall                  | Measures how well the answer recalls supporting context           | [Context Recall](https://www.comet.com/docs/opik/evaluation/metrics/context-recall)                       |
| Dialogue Helpfulness Judge      | Evaluates how helpful an assistant reply is in a dialogue         | [Dialogue Helpfulness](https://www.comet.com/docs/opik/evaluation/metrics/dialogue-helpfulness)           |
| G-Eval                          | Task-agnostic judge configurable with custom instructions         | [G-Eval](https://www.comet.com/docs/opik/evaluation/metrics/g-eval)                                       |
| Hallucination                   | Detects unsupported or hallucinated claims using an LLM judge     | [Hallucination](https://www.comet.com/docs/opik/evaluation/metrics/hallucination)                         |
| LLM Juries Judge                | Averages scores from multiple judge metrics for ensemble scoring  | [LLM Juries](https://www.comet.com/docs/opik/evaluation/metrics/llm-juries)                               |
| Moderation                      | Flags safety or policy violations in assistant responses          | [Moderation](https://www.comet.com/docs/opik/evaluation/metrics/moderation)                               |
| Prompt Uncertainty Judge        | Detects ambiguity in prompts that may confuse LLMs                | [Prompt Diagnostics](https://www.comet.com/docs/opik/evaluation/metrics/prompt-diagnostics)               |
| QA Relevance Judge              | Determines whether an answer directly addresses the user question | [QA Relevance](https://www.comet.com/docs/opik/evaluation/metrics/qa-relevance)                           |
| Structured Output Compliance    | Checks JSON or schema adherence for structured responses          | [Structured Output](https://www.comet.com/docs/opik/evaluation/metrics/structured-output)                 |
| Summarization Coherence Judge   | Rates the structure and coherence of a summary                    | [Summarization Coherence](https://www.comet.com/docs/opik/evaluation/metrics/summarization-coherence)     |
| Summarization Consistency Judge | Checks if a summary stays faithful to the source                  | [Summarization Consistency](https://www.comet.com/docs/opik/evaluation/metrics/summarization-consistency) |
| Trajectory Accuracy             | Scores how closely agent trajectories follow expected steps       | [Trajectory Accuracy](https://www.comet.com/docs/opik/evaluation/metrics/trajectory-accuracy)             |
| Usefulness                      | Rates how useful the answer is to the user                        | [Usefulness](https://www.comet.com/docs/opik/evaluation/metrics/usefulness)                               |

---

### **Conversation LLM as a Judge metrics**

| **Metric**                   | **Description**                                             | **Documentation**                                                                                       |
| ---------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Conversational Coherence     | Evaluates coherence across sliding windows of a dialogue    | [Conversational Coherence](https://www.comet.com/docs/opik/evaluation/metrics/conversational-coherence) |
| Session Completeness Quality | Checks whether user goals were satisfied during the session | [Session Completeness](https://www.comet.com/docs/opik/evaluation/metrics/session-completeness)         |
| User Frustration             | Estimates the likelihood a user was frustrated              | [User Frustration](https://www.comet.com/docs/opik/evaluation/metrics/user-frustration)                 |

---

## **Customizing LLM as a Judge metrics**

By default, Opik uses `GPT-5-nano` from OpenAI as the LLM to evaluate the output of other LLMs.
However, you can easily switch to another LLM provider by specifying a different `model` parameter.

### **Python Example**

```python
from opik.evaluation.metrics import Hallucination

metric = Hallucination(model="bedrock/anthropic.claude-3-sonnet-20240229-v1:0")
metric.score(
    input="What is the capital of France?",
    output="The capital of France is Paris. It is famous for its iconic Eiffel Tower and rich cultural heritage.",
)
```


