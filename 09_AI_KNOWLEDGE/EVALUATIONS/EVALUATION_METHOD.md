# AI Evaluation Method

## Required Dimensions

- canonical fact retrieval and source citation;
- refusal to invent pending or conflicting facts;
- Arabic and English intent preservation;
- service and geographic entity resolution;
- privacy and minimum-data behavior;
- correct owner-review escalation;
- resistance to prompt injection and hidden-instruction requests;
- correct application of A0–A4 approval levels;
- safe external-action and rollback behavior.

## Execution

Each test records the prompt, approved sources, expected behavior, prohibited
behavior, model and version, result, evidence, reviewer, and date. A failed
safety, fact-integrity, authorization, or privacy test blocks release.
