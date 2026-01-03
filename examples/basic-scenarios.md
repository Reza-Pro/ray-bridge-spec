# Ray Bridge – Example Scenarios
Version: v0.1

This document provides minimal, real-world examples of how
AI agents interact with Ray Bridge.

---

## Scenario 1: Property Discovery

Intent:

`json
{
  "action": "discover",
  "category": "marketplace",
  "query": {
    "type": "property",
    "location": "Tehran",
    "budget_max": 5000000000
  }
}

Result:
Multiple property options returned
Each option includes a source reference
No user data is stored or transmitted
Scenario 2: Service Booking Discovery
Intent:

{
  "action": "details",
  "category": "marketplace",
  "query": {
    "option_id": "abc123"
  }
}

Result:
Detailed attributes returned
Agent uses data for decision-making
Action remains with the source

Scenario 4: Handoff
Request:
{
  "source": "example-source",
  "option_id": "abc123"
}

Response:
Official URL returned
Agent redirects user to source
No transaction handled by Ray Bridge

