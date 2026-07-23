# Legacy Archive

## Purpose

Immutable preservation of superseded, ambiguous, or unclassified material discovered during the architecture migration. Per `SYSTEM_ARCHITECTURE.md` Sec. 10.4, this is **recoverable preservation, not a rubbish bin** — nothing here is deleted, and everything here is traceable.

---

# Rules

- Every archived item retains its original relative path (or a collision-safe encoded path) under this folder.
- Every archived item is recorded in `ARCHIVE_MANIFEST.csv` with: original path, archive path, SHA-256 checksum, reason, proposed canonical replacement, approval reference, and migration commit.
- Nothing here is treated as authoritative. If a document appears both here and as an active canonical document elsewhere, the active document always wins.
- No archived item may be edited. If content needs revisiting, copy the relevant text into a new, properly reviewed document — do not repurpose the archived file in place.

---

# Index

See `ARCHIVE_MANIFEST.csv` for the complete, authoritative list. As of the last migration batch, 8 items are archived, all superseded by canonical documents identified during the migration (see `00_GOVERNANCE/DECISION_LOG.md`).
