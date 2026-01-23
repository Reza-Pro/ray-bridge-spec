# Domain Router v0.1

The Domain Router is responsible for resolving incoming
intents to the appropriate service domain and its adapters.

---

## Responsibilities

- Validate incoming intent
- Resolve service_domain
- Select eligible adapters
- Dispatch requests in parallel
- Aggregate and normalize responses

---

## Routing Rules

1. service_domain is mandatory
2. Each domain maintains its own adapter registry
3. Adapters may be enabled or disabled dynamically
4. Router must not expose adapter identity externally

---

## Adapter Selection Strategy (v0.1)

- All enabled adapters within the domain are queried
- Optional internal weighting may apply
- Failures in one adapter do not affect others

---

## Response Aggregation

- Results are merged into a single list
- Duplicate entries may be deduplicated
- Final scoring is domain-specific

---

## Non-Responsibilities

- Authentication
- Payments
- User session management
- Business logic beyond routing
