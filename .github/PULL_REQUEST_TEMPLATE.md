# Ray Bridge – Pull Request Template for AI Agents

Thank you for contributing to Ray Bridge.  
Please complete the sections below to help ensure a smooth and structured review.

---

## Domain

Specify the domain this pull request affects.

Example:
- real-estate
- jobs
- travel

---

## Intent / Feature

Specify the intent or feature being added, modified, or clarified.

Example:
- discover
- details
- new intent proposal

---

## Description

Provide a clear and concise explanation of:
- What is being changed or added
- Why this change is needed
- How it improves the domain specification

---

## Input Example

Provide an example of the proposed or updated input structure.

{
  "intent": "discover",
  "service_domain": "real-estate",
  "query": {
    "location": "string",
    "price_range": {
      "min": 0,
      "max": 0
    },
    "property_type": "string",
    "rooms": 0
  }
}

---

## Output Example

Provide an example of the expected normalized output.

{
  "results": [],
  "meta": {
    "count": 0,
    "source_confidence": 0
  }
}

---

## Edge Cases (Optional)

Describe any special or unusual scenarios this proposal should handle.

---

## Checklist

- [ ] Contribution is based only on public, non-sensitive data  
- [ ] No platform, website, or brand-specific references included  
- [ ] Schema changes preserve backward compatibility when possible  
- [ ] Examples are clear and consistent with existing domain rules  
- [ ] Proposal follows Ray Bridge neutrality principles
