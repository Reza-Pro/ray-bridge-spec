# Real Estate Adapter Interface v0.1

This document defines the standard interface between
Ray Bridge and real-estate adapters.

Adapters must implement this interface.

---

## Adapter Capabilities

Supported actions:
- discover
- details

---

## Input Schema

### Discover Request

{
  "intent": "discover",
  "service_domain": "real-estate",
  "query": {
    "location": "string",
    "price_range": {
      "min": number,
      "max": number
    },
    "property_type": "string",
    "rooms": number
  }
}

---

## Output Schema

### Discover Response

{
  "results": [
    {
      "id": "string",
      "title": "string",
      "location": "string",
      "price": number,
      "currency": "IRR",
      "property_type": "string",
      "rooms": number,
      "area": number,
      "attributes": {},
      "score": number
    }
  ],
  "meta": {
    "count": number,
    "source_confidence": number
  }
}

---

## Adapter Rules

- Adapter must not expose source branding
- Adapter must normalize data
- Adapter must return consistent fields
- Adapter may enrich results internally

---

## Error Handling

Adapters should return graceful errors
without leaking source information.

