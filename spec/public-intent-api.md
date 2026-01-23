# Public Intent API v0.1

This API is the primary entry point for agents interacting with Ray Bridge.

---

## Endpoint

POST /intent

---

## Request Schema

{
  "intent": "discover",
  "service_domain": "real-estate",
  "query": {
    "location": "string",
    "constraints": {}
  }
}

---

## Response Schema

{
  "status": "ok",
  "domain": "real-estate",
  "results": [],
  "meta": {
    "latency_ms": number,
    "result_count": number
  }
}

---

## Error Response

{
  "status": "error",
  "code": "INVALID_INTENT",
  "message": "string"
}

---

## Design Principles

- Stateless
- Source-agnostic
- Domain-driven
- Forward-compatible
