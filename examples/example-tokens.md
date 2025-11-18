# Example Semantic Tokens (ST v1.0)

This file provides concrete examples of Semantic Tokens defined under the public-stable ST v1.0 specification.  
Each example uses the correct schema, families, and invariants.

---

## 1. Intent Token Example

```
family: INTENT
type: QUERY
version: 1.0
fields:
  goal: "retrieve-information"
  target: "semantic-tokens-spec"
  scope: "single-turn"
invariants:
  - goal must be explicit
  - scope must be defined
```

---

## 2. Entity Token Example

```
family: ENTITY
type: OBJECT
version: 1.0
fields:
  id: "topic:semantic-tokens"
  role: "subject"
  attributes:
    category: "documentation"
invariants:
  - id must be unique within the frame
```

---

## 3. State Token Example

```
family: STATE
type: MODE
version: 1.0
fields:
  value: "analytical"
  source: "AMC"
invariants:
  - value must match a known mode
```

---

## 4. Constraint Token Example

```
family: CONSTRAINT
type: SAFETY
version: 1.0
fields:
  severity: "medium"
  required: true
invariants:
  - required must be boolean
  - severity ∈ {low, medium, high}
```

---

## 5. Operation Token Example

```
family: OP
type: SELECT
version: 1.0
fields:
  operation: "choose-mode"
  inputs:
    - "MODE:analytical"
    - "POSTURE:deterministic"
  expected_output: "analytical-mode-activated"
invariants:
  - operation must be deterministic
```

---

End of `example-tokens.md`
