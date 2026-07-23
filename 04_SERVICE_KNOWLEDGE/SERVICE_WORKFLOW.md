# Service Workflow

## Purpose

Defines the shared shape of a service-delivery workflow across AFAQ Alhayat's services, so every service package follows a consistent structure. Per `SYSTEM_ARCHITECTURE.md` Sec. 9.3, individual service packages (e.g. `01_PEST_CONTROL/OPERATIONS.md`) own the detailed, service-specific steps; this document owns the shared shape only.

Derived from the one currently complete and approved service package (`01_PEST_CONTROL/OPERATIONS.md`). Not yet validated against the other 8 services, since their packages don't exist yet — treat this as a draft pattern to confirm once those packages are authored.

---

# Shared Workflow Shape

1. **Customer Request** — inbound lead via website, phone, or WhatsApp.
2. **Scheduling** — appointment booked, technician assigned.
3. **Site Visit / Inspection** — on-site assessment before or as part of service execution.
4. **Planning** — service-specific plan formed (treatment plan, cleaning scope, repair plan, etc.).
5. **Customer Approval** — where applicable, plan or pricing confirmed with the customer before execution.
6. **Service Execution** — the work itself, per the service's own Operations document.
7. **Quality Inspection** — internal check that work meets `99_STANDARDS/QUALITY_CHECKLIST.md` (once authored) and service-specific acceptance criteria.
8. **Customer Education / Handover** — customer informed of results, care instructions, or follow-up needs.
9. **Service Report** — documentation of what was done, for the customer record and internal QA.
10. **Follow-up** — scheduled if the service requires it (warranty visit, repeat treatment, etc.).

---

# Ownership boundary

- This document: the shape above, and nothing service-specific.
- Each service's own `OPERATIONS.md`: the detailed steps, checklists, equipment, and materials for that service.
- `05_OPERATIONS/`: cross-service SOPs, QA, and safety rules that apply regardless of which service is being delivered.

---

# Status

Draft — single-source derived pattern, pending validation once additional service packages exist.
