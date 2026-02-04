# Real Estate Domain Interaction Specification (v0.1)

This document defines a neutral, non-executable interaction specification for the real-estate service domain within Ray Bridge.

The purpose of this specification is to describe how AI agents express intents and how compatible services respond with normalized data, without binding the system to any specific provider, platform, or data source.

This document is a specification only. It does not define adapters, APIs, crawling mechanisms, or implementation details.

---

## Domain Scope

The real-estate domain covers interactions related to discovering and inspecting property listings, including residential and commercial properties.

The focus of this specification is intent expression and normalized response structure, not listing ownership, transactions, or contracts.

---

## Supported Intents

The following intents are defined for the real-estate domain:

- `discover` — search and explore available property listings
- `details` — retrieve structured information for a specific listing

Additional intents may be introduced in future versions through the Ray Bridge contribution process.

---

## Input Schema

### Discover Request

```json
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
```
## Output Schema
### Discover Response
```json
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
```
## Domain Rules

- No exposure of source branding or proprietary identifiers
- Data must conform to the normalized schema
- Field meanings and types must remain consistent
- Internal enrichment or scoring is allowed as long as semantic intent is preserved

---

## Error Handling

- Errors must be returned gracefully and structured
- Error responses must not leak source-specific information
- Failures should be distinguishable from empty results

---

## Neutrality Principles

This specification avoids:

- Referencing specific websites, companies, or services
- Mandating scraping, crawling, or data acquisition
- Defining execution, ownership, or transactional behavior

Its sole purpose is to provide a shared interaction contract that enables AI agents to interoperate with real-estate services.

---

## Versioning

Part of Ray Bridge v0.1. Changes must preserve backward compatibility when possible; breaking changes require justification and review.
