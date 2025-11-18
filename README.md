# Semantic Tokens v1.0 (ST)  
_Public-Stable Specification for SynCE_

Semantic Tokens v1.0 defines the **typed meaning substrate** used across the SynCE engine.  
Where LOS provides linguistic structure and DLC provides deep semantic grounding, **Semantic Tokens provide the unit-level representation of meaning** that higher layers operate on.

ST v1.0 is designed for:

- deterministic multi-agent reasoning  
- stable meaning propagation  
- cross-step semantic continuity  
- schema-bound interpretation  
- drift-resistant meaning frames  
- compatibility with SCP, ORCH-C, and Binder v2.0  

This repository contains the **official, stable, public-facing specification** of Semantic Tokens.

---

## 1. What Semantic Tokens Are

Semantic Tokens are **typed, structured units of meaning** that represent:

- intents  
- entities  
- constraints  
- states  
- relationships  
- operations  
- contextual roles  

They are not embeddings, probabilities, or freeform text.  
They are **discrete, machine-interpretable meaning units** with stable schemas.

ST frames make reasoning:

- aligned  
- interpretable  
- auditable  
- deterministic  

---

## 2. Why Semantic Tokens Exist

LLMs hallucinate because natural language alone lacks:

- structure  
- grounding  
- stable meaning boundaries  
- machine-enforceable interpretation rules  

Semantic Tokens solve this by providing:

- **schema-locked meaning**  
- **typed constraints**  
- **interpretation invariants**  
- **versioned token families**  
- **semantic frame inheritance**  

SynCE uses Semantic Tokens to run a predictable reasoning engine above raw LLM output.

---

## 3. Architecture (GitHub-Safe Diagram)

```
Semantic Tokens v1.0 — Meaning Architecture

+--------------------------------------------------------------+
| Token Families                                               |
|  - Intent Tokens                                             |
|  - Entity Tokens                                             |
|  - Constraint Tokens                                         |
|  - Operation Tokens                                          |
|  - State Tokens                                              |
+--------------------------------------------------------------+
| Token Schema Engine                                          |
|  - field typing                                              |
|  - invariants                                                |
|  - validation rules                                          |
+--------------------------------------------------------------+
| Semantic Frames                                              |
|  - composite token groups                                    |
|  - inheritance + stability                                   |
+--------------------------------------------------------------+
| Integration Layer                                            |
|  - LOS → linguistic substrate                                |
|  - DLC → deep semantic anchors                               |
|  - SCP → control directives                                  |
|  - ORCH-C → plan inputs                                      |
+--------------------------------------------------------------+
```

---

## 4. Components in This Repository

### `semantic-tokens-spec-v1.0.md`
The full public-stable specification, including:

- definitions  
- token families  
- schema rules  
- invariants  
- frame construction  
- validation  
- engine integration  
- versioning  

### `/paper/ST_v1.0.pdf`
Research brief generated from LaTeX:  
*“Semantic Tokens v1.0 — Typed Meaning for Deterministic AI Reasoning.”*

### `/examples/`
Practical examples:

- example-tokens.md  
- example-schemas.md  
- example-frames.md  

### `/schemas/`
Optional subfolder for future JSON/YAML schema definitions.

---

## 5. Versioning

Semantic Tokens follows the SynCE versioning rules:

- **v1.0** — public-stable meaning substrate  
- **experimental token families**  
  live in EDEN only  
- promotions require **EdenBridge compatibility validation**

This repo tracks only **public-stable** ST releases.

---

## 6. Relationship to SynCE

Semantic Tokens are **Layer L1** in the SynCE stack:

- L0 — Semantic Core (LOS + DLC)  
- **L1 — Semantic Tokens (meaning substrate)**  
- L2 — SCP (control substrate)  
- L3 — ORCH-C (orchestration)  
- L4 — Binder/CAP (governance)  
- L5 — SynCE Runtime  
- L6 — Developer APIs  

Tokens provide the meaning that all higher layers depend on.

---

## 7. License
MIT or Apache-2.0 (select per your preference)


---
