# Ray Bridge – Quick Start for Agents
Version: v0.1

Ray Bridge helps agents move from intent to action
without owning data, users, or transactions.

---

## Step 1: Choose an Action

Ray Bridge supports three actions:

- discover
- details
- handoff

---

## Step 2: Send an Intent

Example discover request:

`json
{
  "action": "discover",
  "category": "marketplace",
  "query": {
    "keyword": "apartment",
    "city": "Tehran"
  }
}

Step 3: Receive Options
Ray Bridge returns normalized options from one or more sources.
Agents may compare, filter, or rank results based on their own logic.
Step 4: Handoff
When ready to act, request a handoff:

{
  "source": "example-source",
  "option_id": "abc123"
}
Ray Bridge responds with the official action endpoint.
Important Notes
Ray Bridge does not perform payments
Ray Bridge does not authenticate users
Ray Bridge does not store personal data

Final action always belongs to the source
That’s It
No keys. No accounts. No lock-in.
Ray Bridge is a neutral starting point.
