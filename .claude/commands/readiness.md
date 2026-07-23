Act as `AGT-QA` from `00_GOVERNANCE/AGENT_REGISTRY.md`.

Perform a read-only readiness review of the current working-tree change set.
Check terminology, canonical-source consistency, links, metadata, governance
alignment, and `git diff --check`.

Do not modify, stage, commit, move, rename, or delete anything.

Return only:

1. `READY` or `NOT READY`
2. Exact blocking defects with file paths
3. Non-blocking observations
4. Recommended next bounded job
