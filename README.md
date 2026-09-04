# Why AI Models Drift

**A Technical Framework for Detecting, Diagnosing and Responding to Drift in Machine Learning and GenAI Systems**

**Mohan Arumugam** · September 2026

---

> **MODEL DEPLOYED → REAL-WORLD CHANGE → MONITOR → DETECT → DIAGNOSE → REMEDIATE**
> A model is trained once. Production keeps changing. Drift is the name for the gap that opens between the two — and it opens whether or not anyone is watching for it.

📄 **[Read the guide](https://github.com/mohanarumugam-ai/enterprise-ai-model-drift/blob/main/docs/Why_AI_Models_Drift.pdf)** — 13 pages · Executive Technical Guide
**Audience:** CTO · Engineering Leadership · AI/ML & Platform Teams

---

## The Core Principle

> A model's learned relationship reflects the world at training time. Nothing about deployment freezes that world in place. The discipline that follows — monitor, detect, diagnose, remediate — exists to make that gap measurable and correctable before it becomes a business problem.

## How the guide is organized

| Part | Focus |
|---|---|
| **I — Why Models Drift** | The mechanism behind data, concept, label and pipeline drift — and why GenAI/RAG systems degrade across more layers than a single model's weights |
| **II — Detecting and Monitoring Drift** | The statistical methods (PSI, KL divergence, Jensen–Shannon, Wasserstein, KS test), a layered monitoring model, and the continuous baseline → deploy → monitor → detect lifecycle |
| **III — Responding to Drift** | Why retraining is often the wrong first move, how to diagnose the real cause, and how a golden evaluation suite keeps GenAI systems honest as they change |

## Key ideas

- **Drift is a family of failures, not one thing.** Data drift, concept drift, label drift and prediction drift are genuine statistical changes in the world; pipeline/serving skew is an engineering bug that only looks like drift — and diagnosing which one you have determines which fix is correct.
- **A drifting model rarely fails loudly.** It erodes gradually — no error thrown, no code change to point to — until a business metric makes the problem impossible to ignore.
- **GenAI and RAG systems have at least five independently changing layers** — system prompt, embedding/retrieval, knowledge base, the model itself, and tools/APIs — and a "worse answer" looks identical regardless of which layer actually broke.
- **"Just retrain" is often the wrong reflex.** Retraining fixes genuine concept drift; it does not fix a broken pipeline, a schema change, or a quietly edited system prompt — and retraining against the same broken pipeline just reproduces the failure with a new version number attached.
- **A layered monitoring model** — data, features, predictions, performance, business metrics, segments, and infrastructure/operations — because each layer catches a failure the others miss.
- **The continuous loop:** Baseline → Deploy → Monitor → Detect → Root-cause → Remediate → Revalidate → Update baseline → Redeploy. It runs continuously, not once at launch.
- **A golden evaluation suite** is the GenAI equivalent of a held-out test set — a fixed, representative set of inputs scored on correctness, groundedness, relevance, safety and tool-use accuracy, re-run every time the model, prompt, retrieval corpus, embeddings, chunking, tools or guardrails change.
- **Eight questions every CTO should be able to answer** on demand — from "which models have a documented baseline" to "when was our last false negative."

## Sourcing discipline

The guide distinguishes three kinds of statement throughout: **sourced facts** (numbered citations to NIST's AI 800-4 guidance on monitoring deployed AI systems, Google's ML engineering practices on training-serving skew, and Evidently AI's drift-metrics documentation), **framework recommendations** (this guide's own synthesis of how those sourced facts fit together), and **illustrative figures** (the charts in Chapters 2 and 4 use round, hypothetical data to demonstrate a method — not benchmarks for any real system's drift).

## Connect

- LinkedIn: [linkedin.com/in/mohan-arumugam-3891464](https://www.linkedin.com/in/mohan-arumugam-3891464)
- Substack: [substack.com/@mohanarumugam](https://substack.com/@mohanarumugam)
- GitHub: [github.com/mohanarumugam-ai](https://github.com/mohanarumugam-ai)

---

*Part of the [Enterprise AI thought-leadership portfolio](https://github.com/mohanarumugam-ai) — see also [enterprise-ai-strategy](https://github.com/mohanarumugam-ai/enterprise-ai-strategy), [enterprise-ai-transformation](https://github.com/mohanarumugam-ai/enterprise-ai-transformation), [enterprise-ai-assurance](https://github.com/mohanarumugam-ai/enterprise-ai-assurance), [enterprise-ai-economics-roi](https://github.com/mohanarumugam-ai/enterprise-ai-economics-roi), and [enterprise-ai-model-selection](https://github.com/mohanarumugam-ai/enterprise-ai-model-selection).*
