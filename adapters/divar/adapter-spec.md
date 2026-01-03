# Divar Adapter – Technical Specification
Version: v0.1

This adapter consumes Divar public endpoints
and transforms responses into Ray Bridge
DecisionResult objects.

---

## Input

- Ray Bridge Intent object

## Output

- Ray Bridge DecisionResult object

---

## Normalization Rules

- listing.id → option.id
- listing.title → option.label
- listing.description → option.summary
- listing.url → metadata.url

---

## Error Handling

- On partial failure, return empty options
- Do not propagate Divar-specific errors
  
- Do not retry aggressively

