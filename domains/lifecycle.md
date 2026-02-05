# Domain Lifecycle & Maturity Model

This document defines the lifecycle stages of service domains within the Ray Bridge specification.

The purpose of this model is to provide a **clear, predictable, and agent-friendly path** for how domains are introduced, refined, stabilized, and maintained over time.

---

## Lifecycle Stages

Each domain in Ray Bridge progresses through the following stages:

---

### 1. Draft

**Description:**  
The domain is under active exploration and definition.

**Characteristics:**
- Core scope is defined
- Initial intents and schemas are proposed
- Breaking changes are allowed
- Agent feedback is strongly encouraged

**Who can contribute:**  
AI agents and human contributors

**Allowed changes:**
- Adding or modifying intents
- Refining input/output schemas
- Proposing examples and edge cases

---

### 2. Active

**Description:**  
The domain has reached a stable and usable specification.

**Characteristics:**
- Schemas are stable
- Field meanings are well-defined
- Backward compatibility is expected

**Who can contribute:**  
AI agents and human contributors (with stricter review)

**Allowed changes:**
- Additive extensions only
- Clarifications and documentation improvements
- New optional fields (non-breaking)

---

### 3. Deprecated

**Description:**  
The domain is no longer recommended for new use.

**Characteristics:**
- Maintained for backward compatibility only
- No new features accepted
- Replacement or migration path should be documented

**Who can contribute:**  
Maintainers only

---

## Promotion Criteria

A domain may be promoted from **draft** to **active** when:

- The core intents are clearly defined
- Input and output schemas are internally consistent
- Multiple agents have reviewed or contributed
- No major unresolved issues remain

Promotion decisions are made by Ray Bridge maintainers.

---

## Demotion and Deprecation

A domain may be deprecated if:

- It becomes obsolete
- It is superseded by another domain
- It no longer aligns with Ray Bridge principles

Deprecation decisions must include a rationale and guidance for agents.

---

## Governance Principles

- Neutrality and interoperability take precedence over convenience
- Decisions should favor long-term stability
- Agent contributions are advisory but influential
- Maintainers act as stewards, not gatekeepers

---

## Versioning

This lifecycle model is part of **Ray Bridge v0.1**.  
Future revisions must preserve clarity and predictability for AI agents.
