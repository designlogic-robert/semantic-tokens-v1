# Semantic Tokens Specification (v1.0)
_Public-Stable Meaning Substrate for SynCE_

Semantic Tokens v1.0 (ST) define the **typed, structured meaning units** used throughout the SynCE engine.  
They provide deterministic interpretation, enforce meaning boundaries, and enable cross-step semantic continuity.

This document is the **canonical public-stable specification** of ST v1.0.

---

# 1. Purpose
Semantic Tokens exist to:

- enforce predictable interpretation of meaning  
- remove ambiguity from natural language  
- stabilize meaning across steps and sessions  
- provide typed schemas for reasoning and control  
- serve as the meaning substrate for SCP, ORCH-C, Binder v2.0, and SynCE Runtime  
- ensure that reasoning operates on **structured meaning**, not freeform text  

ST v1.0 defines the first complete meaning substrate for SynCE.

---

# 2. What a Semantic Token Is

A Semantic Token is a:

- **typed meaning unit**  
- with **schema-bound fields**  
- with **interpretation rules**  
- with **validation invariants**  
- with **versioned definition**  

Tokens may represent:

- intents  
- entities  
- states  
- relationships  
- constraints  
- operations  
- temporal markers  
- reasoning roles  

Tokens are *not* embeddings or probabilities.  
They are discrete, deterministic meaning atoms.

---

# 3. Token Families (v1.0)

ST v1.0 defines five stable token families.

## 3.1 Intent Tokens
Represent the agent’s intended action or goal.

Examples:

- `INTENT/QUERY`
- `INTENT/PLAN`
- `INTENT/CLARIFY`
- `INTENT/EXECUTE`

Fields:

- `goal`  
- `target`  
- `modifiers`  
- `scope`  

---

## 3.2 Entity Tokens
Represent objects, actors, concepts, or referents.

Examples:

- `ENTITY/USER`
- `ENTITY/TOPIC`
- `ENTITY/DATASET`
- `ENTITY/OBJECT/{type}`

Fields:

- `id` (canonical or temporary)  
- `role`  
- `attributes`  

---

## 3.3 State Tokens
Represent environmental, cognitive, or process states.

Examples:

- `STATE/CONTEXT`
- `STATE/CONSTRAINT`
- `STATE/MODE`
- `STATE/POSTURE`

Fields:

- `value`  
- `confidence`  
- `source`  

---

## 3.4 Constraint Tokens
Represent restrictions, rules, boundaries, or conditions.

Examples:

- `CONSTRAINT/LIMIT`
- `CONSTRAINT/SAFETY`
- `CONSTRAINT/ALIGNMENT`
- `CONSTRAINT/RESOURCE`

Fields:

- `type`  
- `severity`  
- `required`  

---

## 3.5 Operation Tokens
Represent reasoning or control actions.

Examples:

- `OP/SELECT`
- `OP/TRANSFORM`
- `OP/VALIDATE`
- `OP/ROUTE`

Fields:

- `operation`  
- `inputs`  
- `expected_output`  

---

# 4. Semantic Token Schema (v1.0)

All Semantic Tokens share a standard schema:

```
token_id: ST-{family}-{version}-{uuid}
family: {INTENT | ENTITY | STATE | CONSTRAINT | OP}
type: {specific token type}
fields: {key-value map}
invariants: {list}
version: 1.0
```

### Required fields
- `family`  
- `type`  
- `version`  
- at least one `field`  
- at least one `invariant`

---

# 5. Invariants (Mandatory Meaning Rules)

All ST tokens must satisfy:

### 5.1 Type Invariance
Token meaning does not change mid-reasoning.

### 5.2 Field Stability
Fields cannot be reinterpreted across steps.

### 5.3 Deterministic Interpretation
Same token → same meaning → same behavior.

### 5.4 Version Consistency
Mixed-version tokens are prohibited in a single frame.

---

# 6. Semantic Frames

A **Semantic Frame** is a structured set of tokens that represent a stable segment of meaning.

Frames contain:

- tokens  
- relationships  
- inheritance rules  
- context anchors  
- validation metadata  

### 6.1 Frame Structure

```
frame_id: ST-FRAME-v1-{uuid}
tokens: [...]
relations: [...]
anchors:
  - continuity
  - grounding
validation:
  - schema_check: PASS/FAIL
  - invariant_check: PASS/FAIL
```

### 6.2 Frame Inheritance
Frames can inherit:

- semantic roles  
- token families  
- constraints  

Inheritance is **additive**, never mutative.

---

# 7. Integration with SynCE Layers

Semantic Tokens sit at **L1** and feed:

## 7.1 LOS (L0 → L1)
Provides:

- normalized linguistic context  
- pre-tokenized structures  
- semantic cues  

## 7.2 SCP (L2)
Consumes:

- intent tokens  
- constraint tokens  
- mode/state tokens  

## 7.3 ORCH-C (L3)
Uses:

- operation tokens  
- frame structure  
- constraints  
- context anchors  

## 7.4 Cognitive Governance (L4)
Evaluates:

- alignment  
- CAP metrics  
- affective posture tokens  

## 7.5 SynCE Runtime (L5)
Executes:

- structured reasoning over stable meaning frames  

---

# 8. Validation Model

Semantic Tokens use a three-stage validation:

## 8.1 Schema Validation
Correct family, fields, and structure.

## 8.2 Invariant Validation
Each invariant must resolve to true.

## 8.3 Frame Validation
Cross-token consistency checks.

---

# 9. Example Tokens

## 9.1 Intent Token Example

```
family: INTENT
type: QUERY
version: 1.0
fields:
  goal: "retrieve-information"
  target: "user-topic"
invariants:
  - goal must be explicit
```

## 9.2 Entity Token Example

```
family: ENTITY
type: OBJECT
version: 1.0
fields:
  id: "topic:semantic-tokens"
  role: "subject"
```

## 9.3 State Token Example

```
family: STATE
type: MODE
fields:
  value: "analytical"
```

---

# 10. Versioning Rules

- v1.0 → public-stable  
- all experimental types live in EDEN  
- promotion to v1.x requires:  
  - schema stability  
  - invariant stability  
  - SynCE compatibility  
  - EdenBridge approval  

No breaking changes allowed in patch releases.

---

# 11. Future Extensions (Not in v1.0)

- quantitative token fields  
- cross-frame temporal logic  
- probabilistic confidence overlays  
- dynamic meaning morphologies  

These require additional Binder rules and are EDEN-only.

---


