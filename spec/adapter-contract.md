# Ray Bridge – Adapter Contract
Version: v0.1

This document defines the minimal contract required for a service
to be connected to Ray Bridge through an adapter.

Adapters translate Ray Bridge intents into source-specific requests
and normalize responses back to Ray Bridge decision objects.

## Design Principles

- Adapters are stateless
- Adapters do not store user data
- Adapters do not handle payments or authentication
- Adapters expose only discovery and detail capabilities

## Required Capabilities

An adapter MUST support the following actions:

### 1. Discover

Input:
- category
- query (free-form object)

Output:
- list of options with minimal descriptive fields

### 2. Details

Input:
- option identifier
- optional context

Output:
- structured information for decision-making

## Optional Capabilities

Adapters MAY support:
- availability checks
- pricing snapshots
- metadata enrichment

These capabilities must not require user authentication.

## Adapter Interface (Conceptual)

- receive intent from Ray Bridge
- call source API or data layer
- normalize response
- return decision object

## Error Handling

Adapters should:
- return empty results on partial failure
- avoid propagating source-specific errors
- never expose internal identifiers

## Compliance

Any service implementing this contract can be
connected to Ray Bridge without approval or registration.
