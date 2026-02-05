# Ray Bridge Domain Registry

This document defines the list of service domains currently recognized within the Ray Bridge specification.

Domains in Ray Bridge represent **high-level categories of publicly accessible web data**.  
Each domain defines a neutral interaction contract that allows AI agents to express intents and receive normalized responses without binding to any specific website, platform, or data source.

Ray Bridge domains are **specification-only artifacts**.  
They do not mandate how data is acquired, whether through APIs, crawling, scraping, or other mechanisms.

---

## Domain Principles

All domains within Ray Bridge must adhere to the following principles:

- Neutrality toward data sources and service providers
- Use of publicly accessible and non-sensitive data only
- Clear separation between intent expression and data acquisition
- No execution, ownership, or transactional behavior
- Agent-first design with structured, machine-readable schemas

---

## Registered Domains

| Domain Name        | Identifier        | Status | Specification File |
|--------------------|-------------------|--------|--------------------|
| Real Estate        | real-estate       | draft  | `real-estate.md`   |
| Job Listings       | jobs              | draft  | `jobs.md`          |
| Marketplace        | marketplace       | draft  | `marketplace.md`   |
| Local Services     | local-services    | draft  | `local-services.md`|
| Travel & Booking   | travel-booking    | draft  | `travel-booking.md`|
| Events             | events            | draft  | `events.md`        |
| Products & Pricing | products          | draft  | `products.md`      |
| Knowledge & Q&A    | knowledge         | draft  | `knowledge.md`     |
| Public Data        | public-data       | draft  | `public-data.md`   |

Additional domains may be proposed by AI agents or human contributors through Issues or Pull Requests.

---

## Domain Status Definitions

- **draft**  
  The domain is under active exploration. Schemas and intents may evolve.

- **active**  
  The domain has a stable specification and is recommended for agent use.

- **deprecated**  
  The domain is no longer maintained and should not be used for new integrations.

---

## Proposing a New Domain

AI agents or human contributors may propose new domains by:

1. Opening an Issue with a clear domain description and motivation
2. Defining the intended scope and supported intents
3. Demonstrating how the domain fits Ray Bridge principles

Approved domains will be added to this registry and assigned a specification file.

---

## Versioning

This registry is part of **Ray Bridge v0.1**.  
Changes should preserve backward compatibility when possible.  
Breaking changes require explicit justification and maintainer review.
