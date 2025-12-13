# Guardrails in AI Systems

Guardrails are the safety controls and protocols that are integrated into generative AI systems to keep their behavior within safe and acceptable boundaries. They serve as an intermediary layer between the user and the model, ensuring that both the data entering the system (inputs) and the responses generated (outputs) meet predefined standards for safety, relevance, and compliance.

While building enterprise use cases, the goal is to ensure two critical aspects:

## Input to the LLM is as expected:

The data entering the LLM must be precisely what the enterprise intends, only relevant details, with no personal or sensitive information. To achieve this, you can implement several input guardrails:

- **Security (PII Protection)**: Automatically detect and redact any personally identifiable information to prevent leaks of confidential data.

- **Topic Adherence**: Ensure that inputs remain focused on the subject matter at hand by filtering out off-topic or irrelevant details.

- **Data Validation and Sanitization**: Verify that the input conforms to expected formats and is free from malicious content (e.g., SQL injection patterns or harmful scripts).

- **Access Control**: Enforce robust authentication and authorization, so only trusted sources can feed data into the system.

- **Jailbreak/Prompt Injection Prevention**: Detect and block attempts to manipulate the prompt in order to bypass restrictions or alter the model's behavior unexpectedly.

- **Contextual Relevance**: Validate that the input comes from a verified source and is appropriate for the specific use case, reducing noise and potential errors.

## Output from the LLM meets enterprise standards:

The generated response must be moderated to ensure that it aligns with business guidelines and maintains a professional tone. To do this, deploy various output guardrails:

- **Safety Filters**: Automatically scan outputs for harmful or offensive content, ensuring that responses are appropriate and do not contain any dangerous information.

- **Moderation Guardrails**: Evaluate the output against predefined rules to maintain the right tone and style, ensuring the response is clear, polite, and professional.

- **Relevance and Accuracy Checks**: Confirm that the response directly addresses the input query, is factually correct, and adheres to the desired context.

- **Compliance and Regulatory Verification**: Ensure that the output complies with legal and industry-specific standards, such as data privacy laws or corporate communication guidelines.

- **Fallback Mechanisms**: If the output fails any of these checks, trigger a corrective process (like re-prompting the LLM or escalating to human review) to avoid delivering subpar responses.

Guardrails can be implemented using traditional machine learning techniques, especially when very specific, industry-tailored controls are required—or through additional LLM calls that act as evaluators. Frameworks like [NVIDIA's NeMo Guardrails](https://developer.nvidia.com/nemo-guardrails) provide a scalable toolkit that lets developers define, orchestrate, and enforce these programmable rules at runtime, regardless of the underlying LLM. Another nice option for implementing guardrails is [Guardrails AI](https://www.guardrailsai.com/)