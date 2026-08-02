# Plumbing SEO and AI Knowledge

## Document Information

- **Service ID:** `SVC-PLUMBING`
- **Status:** Migrated (Pilot) — Pending Final Approval Checkpoint for the publication half; Live AI Answers remain separately gated and unaffected by this migration (per `09_AI_KNOWLEDGE/ANSWER_POLICY.md`). SEO fields below are transcribed from `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` (`plumbing`) per `00_GOVERNANCE/PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md`.

## SEO Fields (transcribed, pending final approval)

- **SEO Title (EN):** Plumbing Services in the UAE | AFAQ AL HAYAT
- **SEO Title (AR):** خدمات السباكة في الإمارات | آفاق الحياة
- **Meta Description (EN):** Professional plumbing repair and maintenance across the UAE from AFAQ AL HAYAT — leak repair, fixture maintenance, and drain checks for homes and businesses.
- **Meta Description (AR):** خدمات إصلاح وصيانة السباكة الاحترافية في جميع أنحاء الإمارات من آفاق الحياة — إصلاح التسربات وصيانة التجهيزات وفحص الصرف للمنازل والمنشآت.
- **Keywords (EN, illustrative/unresearched):** Plumbing UAE; Plumber Dubai; Leak Repair; Pipe Repair UAE; Bathroom Plumbing
- **Keywords (AR, illustrative/unresearched):** سباكة الإمارات؛ سباك دبي؛ إصلاح تسرب؛ إصلاح أنابيب؛ سباكة حمامات

**Scope-tension check (per `PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md` §5):** "Pipe Repair UAE" was checked against `CONTENT_EN.md`'s Scope — Excluded item "Major re-piping or full bathroom re-plumbing projects." No conflict found — Scope — Included explicitly names "Pipe joint and fitting inspection and repair" as in-scope, so this keyword accurately reflects included work. No keyword removed.

## Canonical Entity

- **Name:** Plumbing
- **ID:** `SVC-PLUMBING`

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
