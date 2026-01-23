# Service Domain Registry v0.1

Ray Bridge exposes services through high-level service domains.
Agents interact with domains, not with sources or platforms.

## Supported Domains (v0.1)

### 1. Real Estate

Domain ID: real-estate

Description:
Services related to property discovery and listing.

Supported Intents:
- search_property
- filter_property
- get_property_details

Typical Query Parameters:
- location
- price_range
- property_type
- rooms
- area

Output Characteristics:
- normalized property objects
- ranked results
- optional source metadata (internal only)

---

### 2. Booking

Domain ID: booking

Description:
Reservation-based services including hotels, flights, and transportation.

Supported Intents:
- search_availability
- check_price
- get_booking_options

Typical Query Parameters:
- destination
- date_range
- guests
- service_type (hotel, flight, train)

Output Characteristics:
- availability slots
- pricing information
- booking constraints

---

### 3. Marketplace

Domain ID: marketplace

Description:
Product and service discovery across marketplaces.

Supported Intents:
- search_product
- compare_prices
- get_product_details

Typical Query Parameters:
- product_name
- category
- price_range
- brand

Output Characteristics:
- normalized product listings
- price comparison
- seller metadata

