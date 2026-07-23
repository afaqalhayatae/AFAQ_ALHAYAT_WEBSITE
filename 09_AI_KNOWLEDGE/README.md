# AI Knowledge

## Purpose

Defines how AI systems (assistants, agents, generative search) should retrieve, interpret, and answer using AFAQ Alhayat's knowledge base. Per `SYSTEM_ARCHITECTURE.md` Sec. 5, this domain owns retrieval, entities, and AI policy — it must not invent business facts or duplicate source content.

---

# Documents

| Document | Purpose |
|---|---|
| `KNOWLEDGE_INDEX.md` | Map of which domain owns which fact type. |
| `ENTITY_REGISTRY.md` | The company's core named entities (organization, services, brand). |
| `ENTITY_RELATIONSHIPS.md` | How those entities relate to each other. |
| `AI_SYSTEM_PROMPT.md` | Baseline instruction set for any AI assistant answering on behalf of AFAQ Alhayat. |
| `CONVERSATIONAL_ASSISTANT_STANDARD.md` | Product, safety, UX, retrieval, handoff, evaluation, and launch standard for a natural bilingual chatbot. |
| `RETRIEVAL_POLICY.md` | Rules for which source an AI system must retrieve from for a given fact type. |
| `ANSWER_POLICY.md` | Rules for what an AI system may and may not claim, and how to handle uncertainty. |
| `GEO_STRATEGY.md` | Generative-Engine-Optimization approach — how content should be structured so AI search engines can find and cite it. |
| `EVALUATIONS/` | Test cases and evaluation criteria for AI answer quality (not yet populated). |

---

# Governing rule

Every rule in this domain traces back to one already established for this repository during its migration: never invent facts, cite the canonical source, disclose uncertainty, and never present a Draft/Unverified value as approved.
