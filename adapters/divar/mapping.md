# Divar Adapter – Intent Mapping
Version: v0.1

This document maps Ray Bridge intents
to Divar public listing parameters.

---

## Supported Categories

- marketplace.property
- marketplace.vehicle
- marketplace.goods

---

## Intent to Divar Mapping

### Discover

Ray Bridge Intent:
- action: discover
- category: marketplace
- query fields are mapped to Divar filters

Examples:

| Intent Field | Divar Parameter |
|-------------|----------------|
| location    | city           |
| price_min  | price[min]     |
| price_max  | price[max]     |
| keyword    | q              |

---

### Details

Ray Bridge Intent:
- action: details
- query.option_id maps to Divar listing ID

---

## Unsupported Features

- Messaging
- Phone number retrieval
- User profiles
  
