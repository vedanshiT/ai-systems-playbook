# GenAI Architecture Patterns

**Source:** Martin Fowler – Emerging Patterns in Building GenAI Products  
**Type:** Pattern Overview  
**Last Updated:** April 2026

---

## ⚡ Quick Summary
- GenAI systems are non-deterministic and context-dependent  
- Reliable applications require patterns like RAG, Guardrails, and Evals  
- Production systems are multi-layered, not just single LLM calls  

---

## 🧠 Core Idea
Generative AI systems behave differently from traditional software:

- Outputs are **non-deterministic**
- Models can **hallucinate**
- Knowledge may be **limited or outdated**
- Behavior depends on **prompt + context**

👉 Building production systems requires structured **architecture patterns**

---

## 🏗️ System Mental Model

A GenAI system is a pipeline:

User Input  
↓  
Prompt Engineering  
↓  
Retrieval (Optional)  
↓  
LLM Processing  
↓  
Guardrails / Validation  
↓  
Evaluation  
↓  
Final Output  

---

## 🔑 Core Patterns

### 1. Direct Prompting
Basic interaction with an LLM.

**Use cases:**
- Prototyping  
- Simple tasks  

**Limitations:**
- Low reliability  
- Limited control  

---

### 2. Evaluation (Evals)
Measure output quality and correctness.

**Why it matters:**
- AI outputs are unpredictable  
- Needed for systematic improvement  

**Examples:**
- Test datasets  
- Scoring responses  
- Regression testing  

---

### 3. Embeddings
Text represented as numerical vectors.

**Used for:**
- Semantic search  
- Similarity matching  
- Retrieval systems  

---

### 4. Retrieval-Augmented Generation (RAG)

**Flow:**
User Query → Retrieve Data → LLM → Answer  

**Why needed:**
- LLMs lack real-time/private data  
- Adds relevant context dynamically  

**Benefits:**
- Reduces hallucinations  
- Improves accuracy  

---

### 5. Advanced RAG Techniques

- Query Rewriting → improves input  
- Hybrid Search → keyword + semantic  
- Reranking → improves relevance  

---

### 6. Guardrails
Control AI behavior.

**Types:**
- Rule-based constraints  
- Model-based filtering  
- Safety checks  

**Purpose:**
- Prevent harmful outputs  
- Enforce policies  

---

### 7. Fine-Tuning

**Use when:**
- Domain-specific behavior needed  
- RAG is insufficient  

**Trade-offs:**
- Expensive  
- Complex to maintain  

---

## ⚙️ Production Insight

Real systems combine patterns:

Prompting + RAG + Guardrails + Evals  

👉 No single pattern is sufficient  

---

## 🚨 Problems Solved

- Hallucinations  
- Outdated knowledge  
- Inconsistent outputs  
- Safety risks  
- Low reliability  

---

## 🧩 Key Insight

GenAI systems are engineered **around the model**, not just built on top of it.

---

## 🧠 Mental Model

- Prompting → Input design  
- LLM → Reasoning engine  
- RAG → Memory layer  
- Guardrails → Safety layer  
- Evals → Quality control  

---

## 🤔 My Takeaways
- RAG is central to most real-world systems  
- Evals are critical but often overlooked  
- System design matters more than prompt tricks  

---

## 🏷️ Tags
#genai #ai-architecture #rag #llm #systems-design