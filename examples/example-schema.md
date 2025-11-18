# Example Token Schema (ST v1.0)

This file shows the canonical structure of a Semantic Token and an example Semantic Frame using ST v1.0.

---

# 1. Canonical Semantic Token Schema

```
token_id: ST-{family}-{version}-{uuid}
family: {INTENT | ENTITY | STATE | CONSTRAINT | OP}
type: {specific token type}
version: 1.0

fields:
  {key}: {value}

invariants:
  - list of rules that must remain true
```

Every token in ST v1.0 must follow this structure.

---

# 2. Example: Fully-Structured Token (Intent)

```
token_id: ST-INTENT-1.0-9f2c4ac1
family: INTENT
type: PLAN
version: 1.0
fields:
  goal: "build-architecture"
  target: "Semantic Core"
  modifiers:
    detail_level: "high"
    justification_required: true
invariants:
  - goal must be explicit
  - modifiers may not change type across steps
```

---

# 3. Example Semantic Frame (L1 → L2)

A Semantic Frame is a structured set of tokens representing a stable segment of meaning.

```
frame_id: ST-FRAME-v1-aa210fe2
tokens:
  - ST-INTENT-1.0-9f2c4ac1
  - ST-ENTITY-1.0-bb42f119
  - ST-CONSTRAINT-1.0-a122def0

relations:
  - subject → INTENT.goal → ENTITY
  - CONSTRAINT applies-to → INTENT

anchors:
  continuity: true
  grounding: true

validation:
  schema_check: PASS
  invariant_check: PASS
```

---

End of `example-schema.md`
