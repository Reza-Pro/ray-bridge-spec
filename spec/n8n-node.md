# n8n Node Specification – Ray Bridge v0.1

This document defines the Ray Bridge node for n8n-style
agent automation platforms.

---

## Node Name
Ray Bridge – Intent Resolver

---

## Node Type
Action Node

---

## Inputs

### Required Fields
- intent (string)
- service_domain (string)

### Optional Fields
- query (object)
- constraints (object)

---

## Output

- status
- domain
- results
- meta

---

## Behavior

- Node sends intent to Ray Bridge Public Intent API
- Node remains stateless
- Node does not manage authentication
- Node does not store execution history

---

## Example Usage

Intent: discover  
Service Domain: real-estate  
Query: location=Tehran

---

## Design Principles

- Minimal configuration
- Agent-first design
- Forward compatible
- No vendor lock-in
