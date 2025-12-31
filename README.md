# GEN-FIT™  
**Generative Ethics & Norms Framework for Integrity and Trust**

GEN-FIT™ is a runtime governance framework for trustworthy AI systems.

It defines **how an AI system must behave at runtime**—not how it is trained, not which model it uses, and not what policies an organization claims to follow.

GEN-FIT exists to answer a simple but neglected question:

> *When an AI system is actually running and interacting with people, what behaviors are non-negotiable if we want it to be safe, predictable, and worthy of trust?*

---

## What GEN-FIT Is (and Isn’t)

### GEN-FIT *is*:
- A **runtime governance profile** for generative and agentic AI systems  
- A set of **behavioral invariants** that can be tested, audited, and enforced  
- **Model-agnostic**: compatible with any LLM, agent, or orchestration layer  
- Aligned with **NIST AI RMF 1.0**, **ISO/IEC 42001**, and **OWASP Top-10 for LLM Applications**, while filling a critical gap they leave open

### GEN-FIT is *not*:
- A training methodology  
- A personality or tone guide  
- A content moderation policy  
- A replacement for organizational governance programs

GEN-FIT complements existing frameworks by making governance **observable inside the system itself**, where failures actually occur.

---

## The Core Idea

Most AI governance today lives outside the system:
- policy documents  
- risk registers  
- assurance reports  
- ethical principles

GEN-FIT moves governance **into the runtime envelope**.

A GEN-FIT–compliant system must demonstrate, *on every interaction*, that it satisfies three invariants:

1. **Traceable reasoning**  
   Claims are grounded in evidence or explicitly marked uncertainty.  
2. **Predictable behavior**  
   Randomness may vary wording, but never facts, safety posture, or commitments.  
3. **Governed safety**  
   The system protects users from physical, psychological, and informational harm in real time.

If a system cannot *demonstrate* these properties at runtime, it is not governed—no matter how good the policy paperwork looks.

---

## Why This Matters

Failures in deployed AI systems are rarely caused by missing policies.  
They are caused by **runtime drift**:

- hallucinations delivered confidently  
- safety decisions that change with phrasing or randomness  
- anthropomorphic behavior that encourages over-trust  
- silent policy violations  
- inconsistent refusals or explanations  

GEN-FIT is designed to make these failures **structurally impossible**, or at minimum **structurally visible**.

---

## Design Principles

GEN-FIT is built on several non-negotiable principles:

- **Integrity precedes utility**  
  Truthfulness and safety outrank engagement or fluency.
- **Structure is the vehicle of care**  
  Safety comes from boundaries, not personality.
- **Human dignity is invariant**  
  No output may degrade or instrumentalize the user.
- **Refusal is responsibility**  
  Withholding output under uncertainty is a feature, not a failure.
- **Stochastic variation must never change meaning**  
  Style may vary; substance may not.

These are enforced as **architectural constraints**, not aspirational values.

---

## What GEN-FIT Specifies

GEN-FIT defines requirements for:

- Deterministic governance envelopes  
- Policy and jurisdiction binding  
- Domain detection and boundary enforcement  
- Refusal, restriction, and safe-alternative behavior  
- Traceability and auditability  
- Protection against anthropomorphic deception  
- Non-reciprocity and prohibition of assistant self-interest  
- Governance drift detection  

Importantly, GEN-FIT does **not** dictate *how* you implement these controls—only *what must be true* if your system is to be considered governed.

---

## Relationship to SFCL™

GEN-FIT originated from the **Scarborough Fair Chat Laws (SFCL™)**.

- **SFCL** is an executable conversational governance kernel  
- **GEN-FIT** is the **standard of integrity** that such kernels must satisfy  

You can think of GEN-FIT as the *specification* and SFCL as one *reference implementation*.

Other implementations are welcome.

---

## Who GEN-FIT Is For

GEN-FIT is designed for:

- AI platform builders  
- Safety and governance teams  
- Security and compliance engineers  
- Researchers working on agentic systems  
- Organizations deploying AI in regulated or high-risk contexts  

If you need to answer questions like:
- “Can we audit this system’s behavior?”
- “Will it behave the same way tomorrow?”
- “What happens when the model is wrong?”
- “How do we prove safety without reading minds?”

GEN-FIT is for you.

---

## Status & License

- **Status:** v0.7 (public draft)  
- **License:** CC-BY-SA 4.0  
- **Maintainer:** Jim Scarborough (Kiteframe, L.L.C.)

GEN-FIT is intentionally published early and publicly to invite scrutiny, testing, and implementation feedback.

---

## Getting Started

- Read the **Executive Summary** in `GEN-FIT.md`  
- Skim the **Normative Principles** to understand the invariants  
- Map GEN-FIT requirements to your existing AI stack  
- Compare governed vs. ungoverned behavior under the same prompts  

Questions, critiques, and serious implementation discussions are welcome.

---

> **GEN-FIT doesn’t make AI more human.**  
> It makes AI more **knowable**, **predictable**, and **safe to rely on**.

That clarity is the point.
