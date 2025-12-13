# ** Data Annotation for RAG Evaluations (Clean Explanation)**

To properly evaluate a RAG system, you must know four things for each data point:

1. The **question**
2. The **ideal context** (ideal chunks)
3. The **predicted context** retrieved by your pipeline
4. The **ideal answer** and **predicted answer**

Retrieval metrics (context precision, context recall, MRR, etc.) rely specifically on knowing the **ideal chunks**.
But in real systems, *ideal chunks almost never exist*. You have long documents, not pre-labeled passages.

This lesson explains **how to create those annotations**—efficiently, scalably, and without breaking them every time chunking or retrievers change.

---

# **1. What an Annotated Data Point Looks Like**

### **Example: Internal Policy Q/A**

**Question:**
*What’s the retention policy for customer chat transcripts in Zendesk?*

**Ideal Context (gold chunks):**

* “Zendesk chat transcripts are stored for 90 days…”
* “Enterprise accounts can extend retention up to one year…”
* “Transcripts older than retention period are automatically deleted.”
* “Admins can export transcripts manually before deletion.”

**Predicted Context (retriever output):**

* “Zendesk chat transcripts are stored for 90 days…”
* “Transcripts can be exported manually…”
* *Noise:* “Ticket attachments stored in S3 indefinitely.”
* *Noise:* “Chat macros allow predefined templates.”

**Retrieval Metrics:**

* Context Recall = 3/4 = **0.75**
* Context Precision = 2/4 = **0.50**

**Ideal Answer:**
Detailed retention policy including default period, enterprise extension, and auto-deletion.

**Predicted Answer:**
Slightly incomplete but mostly correct.

---

# **2. The Real Challenge: No One Has “Ideal Chunks”**

In real-world companies:

* You have long PDFs, HTML pages, manuals, emails, Confluence pages.
* You do **not** have a map of which passages support which answers.
* When you change chunk size or overlap, all manual labels break.

So we need **robust, cheap, repeatable annotation methods**.

---

# **3. Method 1 — Use the Ideal Answer as a Retrieval Proxy**

It is much easier to get a **correct answer** (from SMEs or gold QA pairs) than to label exact chunks.

### **How to bootstrap ideal chunks:**

## **Step 1 — “Claimify” the ideal answer**

Split the answer into **atomic facts**.

Example ideal answer → facts:

1. Default retention = 90 days
2. Enterprise accounts can extend to 1 year
3. Old transcripts auto-delete
4. Admins can export before deletion

Each fact becomes its own retrieval query.

---

## **Step 2 — Retrieve top-K chunks per fact**

Retrieve ~5 chunks per claim → ~20 candidates total.

Human annotators then confirm which chunks actually support each claim.

This creates a high-quality fact ↔ chunk mapping.

---

# **4. Method 2 — Expand Labels via Similarity or Clustering**

Once some chunks are labeled:

1. Compute similarity to all other chunks
2. Promote semantically similar chunks as “likely relevant”
3. Annotators only validate the top cluster neighbors

This greatly reduces manual work and leverages redundancy in enterprise documentation.

---

# **5. Method 3 — Use Multiple Retrievers and Promote Overlaps**

Use **BM25 + Dense Retrieval + Hybrid Retrieval**.

If a chunk is retrieved by **multiple retrievers for the same claim**, it is highly likely to be relevant.

Label it automatically; humans only review disagreements.

---

# **6. Pro Tip — Label Exact Evidence Spans, Not Just Chunks**

Once you know which chunk is relevant, annotate the **exact offsets** that support the claim.

### Example spans:

| chunk_id | question_id   | claim_id | span_text                                | offsets    |
| -------- | ------------- | -------- | ---------------------------------------- | ---------- |
| ch_215   | q_procurement | c1       | “create a new purchase order…”           | [12, 95]   |
| ch_215   | q_procurement | c2       | “Orders above $10,000 require approval…” | [97, 157]  |
| ch_215   | q_procurement | c3       | “sent to Finance for processing”         | [175, 216] |

Benefits:

* Allows fine-grained recall measurement
* Survives chunk-resplitting
* Enables explainable RAG systems (“Why did you retrieve this?”)

---

# **7. Moving Faster: Reference-Free Metrics**

Full annotation becomes expensive as datasets scale.
A practical alternative is **reference-free retrieval evaluation**.

Instead of comparing retrieved chunks to gold-labeled chunks, compare them **directly to the ideal answer**.

---

# **Reference-Free Context Recall**

Measures how much of the **ideal answer’s content** appears in retrieved chunks.

### Example:

Ideal answer: “Employees get 10 sick days.”

Retrieved chunks:

* “Employees are entitled to 10 sick days annually.” → **High semantic overlap**
* Noise chunks

Recall = 1/1 = **100%**

If the retriever missed this line entirely, recall = **0%**.

---

# **Reference-Free Context Precision**

Measures what fraction of retrieved chunks actually contribute meaningfully to the ideal answer.

Example:
5 retrieved chunks → only 1 overlaps with ideal answer → precision = 1/5 = **20%**

This reveals:

* Lots of noise
* Retriever is not discriminating well

---

# **Why Reference-Free Metrics Are Useful**

* No need for ideal chunks
* Works with only question + ideal answer
* Fast to compute
* Good for early development
* Works across chunking configurations

Not perfect — but extremely practical.

LLM-judge-only methods (no ideal answer at all) exist but are less reliable than answer-based methods.

---

# **Key Takeaways from Lesson 7**

### **You cannot evaluate RAG without annotated data — but manual annotation is expensive.**

These strategies reduce the cost by 5–10×:

1. **Claimify ideal answers → retrieve per claim → annotate only true matches**
2. **Expand via similarity/clustering**
3. **Use multi-retriever agreement**
4. **Label exact spans, not just chunks**
5. **Use reference-free precision/recall when full annotation is not feasible**

Together, these create a scalable, maintainable framework for building high-quality RAG evaluation datasets.

---
