# End-to-End Flow Example – Real Estate (v0.1)

This example demonstrates a complete intent resolution
flow using Ray Bridge for the real-estate domain.

---

## Step 1: Agent Intent

The agent submits a discovery intent.

Request:
{
  "intent": "discover",
  "service_domain": "real-estate",
  "query": {
    "location": "Tehran",
    "property_type": "apartment",
    "price_range": {
      "max": 15000000000
    },
    "rooms": 2
  }
}

---

## Step 2: Ray Bridge Processing

- Domain Router resolves domain = real-estate
- All enabled real-estate adapters are selected
- Queries are dispatched in parallel
- Responses are normalized and scored

---

## Step 3: Normalized Response

Response:
{
  "status": "ok",
  "domain": "real-estate",
  "results": [
    {
      "id": "re-001",
      "title": "Two-bedroom apartment",
      "location": "Tehran",
      "price": 14500000000,
      "currency": "IRR",
      "rooms": 2,
      "area": 95,
      "score": 0.87
    }
  ],
  "meta": {
    "result_count": 1,
    "latency_ms": 320
  }
}

---

## Step 4: Agent Decision

The agent evaluates results and may:
- present options to the user
- request details
- initiate handoff to source

Ray Bridge does not perform final actions.
