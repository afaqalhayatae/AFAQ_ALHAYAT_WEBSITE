# Painting SEO and AI Knowledge

## Document Information

- **Service ID:** `SVC-PAINTING`
- **Status:** Migrated (Pilot) — Pending Final Approval Checkpoint for the publication half; Live AI Answers remain separately gated and unaffected by this migration (per `09_AI_KNOWLEDGE/ANSWER_POLICY.md`). SEO fields below are transcribed from `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` (`painting`) per `00_GOVERNANCE/PAINTING_CONTENT_SYNC_EXECUTION_PLAN.md`.

## SEO Fields (transcribed, pending final approval)

- **SEO Title (EN):** Painting Services in the UAE | AFAQ AL HAYAT
- **SEO Title (AR):** خدمات الدهانات في الإمارات | آفاق الحياة
- **Meta Description (EN):** Professional interior and exterior painting across the UAE from AFAQ AL HAYAT — surface preparation, color consultation, and clean finishing for homes and businesses.
- **Meta Description (AR):** طلاء داخلي وخارجي احترافي في جميع أنحاء الإمارات من آفاق الحياة — تحضير الأسطح واستشارة الألوان وتشطيب نظيف للمنازل والمنشآت.
- **Keywords (EN, illustrative/unresearched):** Painting Services UAE; House Painter Dubai; Wall Painting; Interior Painting UAE
- **Keywords (AR, illustrative/unresearched):** دهانات الإمارات؛ دهان دبي؛ طلاء جدران؛ دهانات داخلية

**Resolved finding (applied per Owner decision):** the source record's keyword lists originally included "Villa Painting" (EN) and "دهان فلل" (AR). Both were removed per `00_GOVERNANCE/PAINTING_SEO_DECISION_APPLIED.md` §1 — the keyword risked implying full villa exterior-painting capability, including height-access work, while Scope — Excluded disclaims "work at heights requiring specialized access equipment beyond standard reach." English and Arabic keyword lists are now aligned (4 of the original 5 in each language). All other SEO fields (title, meta description, remaining keywords) are unchanged from source.

## Canonical Entity

- **Name:** Painting
- **ID:** `SVC-PAINTING`

## Safe Intent Framework

- Understand the service and its approved scope
- Determine whether assessment is required
- Request a quotation or booking through approved channels
- Check confirmed geographic availability
- Find approved preparation, limitations, and follow-up information

## Guardrails

- Do not generate local claims beyond approved registries.
- Do not invent methods, products, equipment, credentials, response times,
  prices, results, warranties, or regulatory claims.
- AI answers must cite canonical sources and escalate missing facts.

## Evidence Gate

These facts require owner confirmation or competent evidence before approval:

- included and excluded scope;
- operational methods, tools, materials, and resources;
- competency, safety, compliance, and escalation requirements;
- duration, availability, commercial terms, price, and warranty;
- performance, quality, licensing, and regulatory claims.

Unknown facts remain `Pending Owner Input`; they must not be inferred from a
service name, generic industry practice, or a source draft.

## Canonical References

- Service identity: [`SERVICE_CATALOG.md`](../SERVICE_CATALOG.md)
- Geographic availability: [`SERVICE_MATRIX.md`](../SERVICE_MATRIX.md) and
  [`SERVICE_AREAS.md`](../../03_MARKET/SERVICE_AREAS.md)
- Contact facts: [`CONTACT_INFORMATION.md`](../../02_BRAND/CONTACT_INFORMATION.md)
- Package standard: [`SERVICE_TEMPLATE.md`](../../99_STANDARDS/SERVICE_TEMPLATE.md)
