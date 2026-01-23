End-to-End Flow Example – Real Estate (v0.2 Executable)

This document demonstrates a fully executable intent resolution flow using Ray Bridge in the real-estate domain, connected to a live Divar-compatible API hosted on Sarenakha.

This version upgrades the previous conceptual example (v0.1) into a realistic, adapter-backed execution flow.

Step 1: Agent Intent (Standardized Request)

The agent submits a discovery intent to Ray Bridge without referencing any provider.

Request:

{
  "intent": "discover",
  "service_domain": "real-estate",
  "query": {
    "location": "Tehran",
    "property_type": "apartment",
    "price_max": 15000000000,
    "rooms": 2
  },
  "limit": 5
}

Step 2: Ray Bridge Domain Routing

Ray Bridge processes the request as follows:

Resolves service_domain = real-estate

Loads all enabled adapters for the domain

Selects divar-real-estate adapter

Maps the intent query into provider-compatible parameters

Dispatches a live request to the provider API endpoint hosted on Sarenakha

Target Request Example:

GET https://api.sarenakha.ir/divar/search?city=Tehran&rooms=2&max_price=15000000000&limit=5

Step 3: Provider Raw Response (Live Sample)

Example of raw response returned by the provider API:

{
  "items": [
    {
      "id": "987",
      "title": "آپارتمان ۲ خوابه در صادقیه",
      "price": 2700000000,
      "district": "صادقیه",
      "area": 92,
      "rooms": 2,
      "url": "https://divar.ir/v/987",
      "images": [
        "https://cdn.divar.ir/img1.jpg",
        "https://cdn.divar.ir/img2.jpg"
      ]
    }
  ]
}

Step 4: Ray Bridge Normalization Layer

Ray Bridge transforms provider data into a provider-agnostic standardized response, ensuring:

Uniform field naming

Currency consistency

Comparable scoring

Domain-based output abstraction

Normalized Response:

{
  "status": "ok",
  "domain": "real-estate",
  "results": [
    {
      "id": "987",
      "title": "آپارتمان ۲ خوابه در صادقیه",
      "location": "Tehran - Sadeghieh",
      "price": 2700000000,
      "currency": "IRR",
      "rooms": 2,
      "area": 92,
      "score": 0.91,
      "source_adapter": "real-estate.divar",
      "url": "https://divar.ir/v/987",
      "images": [
        "https://cdn.divar.ir/img1.jpg",
        "https://cdn.divar.ir/img2.jpg"
      ]
    }
  ],
  "meta": {
    "result_count": 1,
    "provider_count": 1,
    "latency_ms": 183,
    "execution_version": "v0.2"
  }
}

Step 5: Agent Decision Layer

The agent receives normalized results without visibility into the underlying provider.

The agent may:

Display results to the end user

Request additional filtering

Ask for more details

Trigger a follow-up intent

Ray Bridge does not execute final transactions and does not expose provider identity at the agent level.

Summary

This flow proves that Ray Bridge can:

Accept provider-agnostic intents

Route them through domain-based adapters

Execute real provider-backed queries

Return normalized, provider-neutral results

Operate as a decision-routing and intent-resolution engine

This marks the first live executable milestone for Ray Bridge in the real-estate domain.
