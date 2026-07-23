# Answer Policy

## Purpose

Defines what an AI system may and may not claim on behalf of AFAQ Alhayat, per `SYSTEM_ARCHITECTURE.md` Sec. 9.4: "AI answer policy must cite authoritative paths, disclose uncertainty, and refuse to fill missing phone, price, warranty, licensing, or safety facts."

---

# Rules

1. **Cite the source domain**, not just an answer. If asked for the phone number, retrieve it from `02_BRAND/CONTACT_INFORMATION.md` — do not answer from memory or a prior conversation.
2. **Never state a Draft/Unverified value as approved fact.** As of this writing, `CONTACT_INFORMATION.md`'s phone and WhatsApp are Draft/Unverified. The correct answer to "what's your phone number" is that it is not yet published, not a guessed or placeholder number.
3. **Never invent**: prices, licenses, certifications, guarantees, regulatory compliance claims, or safety claims not present in an approved source document.
4. **Never state coverage of an area** as confirmed until `03_MARKET/SERVICE_AREAS.md` is finalized (currently HOLD — three unreconciled drafts exist, none canonical).
5. **Disclose gaps.** If a question depends on a document that doesn't exist yet (e.g. detailed AC Maintenance service knowledge), say so rather than filling the gap with plausible-sounding content.
6. **Do not merge conflicting sources.** If two documents disagree (which should not happen for canonical content, but may for HOLD/draft material), do not average or blend them — flag the conflict.
7. **Respect language pairing.** If answering in Arabic, use the approved Arabic content variant; do not machine-translate an English-only canonical fact and present it as an equally authoritative Arabic source unless no Arabic variant exists, in which case say so.

---

# Example

**Bad:** "Our phone number is +971 4 123 4567." (invented)
**Good:** "I don't have a confirmed phone number on file yet for AFAQ Alhayat — that detail is marked as pending owner confirmation."

---

# Status

Draft — policy is complete and grounded in existing project rules; should be reviewed by whoever configures the production AI assistant.
