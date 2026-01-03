# Ray Bridge – Intent Schema

Version: v0.1
Status: Draft

## Purpose

This document defines the structure and constraints of intents accepted by Ray Bridge.
An intent represents a clear, action-oriented request expressed by an AI agent.

Ray Bridge validates and routes intents without executing the underlying action.

---

## Design Goals

* Keep the schema minimal and predictable
* Support agent-native communication
* Prevent unsafe or out-of-scope actions
* Enable consistent routing across heterogeneous services

---

## Supported Intent Types (v0.1)

Ray Bridge supports exactly three intent types in version v0.1:

### 1. discover

Used to identify relevant services or options based on a stated need.

Examples:

* Find available real estate listings in a given area
* Identify travel booking providers for a specific route

---

### 2. understand

Used to retrieve structured details required to evaluate or compare options.

Examples:

* Retrieve pricing and availability details
* Fetch key attributes of a selected option

---

### 3. handoff

Used to obtain the official endpoint or workflow required to proceed with an action.

Examples:

* Get the official booking URL
* Obtain the API endpoint for final execution

Ray Bridge does not perform the action itself.

---

## Intent Object Structure

Each intent submitted to Ray Bridge MUST include the following fields:

* intent_type: one of [discover, understand, handoff]
* domain: the service domain (e.g. real_estate, travel, commerce)
* parameters: key-value pairs describing the request context

Optional fields MAY include:

* locale
* time_constraints
* budget_constraints

---

## Validation Rules

Ray Bridge rejects intents that:

* Request transaction execution
* Require user authentication
* Attempt to store or retrieve personal data
* Fall outside the supported intent types

Rejected intents MUST return a clear validation error.

---

## Determinism and Neutrality

Given identical intent objects, Ray Bridge MUST return equivalent routing results.
No randomness, personalization, or paid prioritization is permitted.

---

## Evolution Policy

New intent types may be introduced in future versions.
Existing intent types MUST remain backward compatible.

service_domain (required)

