# Social Media Automation and Publishing Architecture

**Status:** Approved Architecture / Account Connections Pending

---

## Goal

Create a fast, reliable publishing system for TikTok, Snapchat, Instagram, Facebook, YouTube, LinkedIn, and other approved channels without sacrificing factual accuracy, brand quality, account safety, or platform compliance.

The first automation target is not uncontrolled auto-posting. It is a controlled production pipeline that removes repetitive work while preserving final accountability.

---

## Workflow

`Approved strategy → canonical facts → content brief → script/copy draft → media production → bilingual/platform review → approval → scheduling → publishing → monitoring → analytics → learning`

### Automated

- Generate ideas from approved content pillars.
- Retrieve approved service facts.
- Create platform-specific draft captions and scripts.
- Prepare shot lists, thumbnails, subtitles, and aspect-ratio variants.
- Check prohibited claims, missing consent, and placeholder data.
- Add approved UTM parameters.
- Build an approval queue.
- Schedule already-approved assets.
- Collect performance data and prepare reports.

### Human Controlled

- Account authentication and permissions.
- Final approval of public content.
- Customer consent and media rights.
- Prices, offers, guarantees, licenses, and compliance claims.
- Crisis, complaint, safety, and legal responses.
- Publishing access-policy changes.
- Deleting or materially editing live content.

---

## Platform Connection Policy

- Use official platform APIs or an approved publishing partner.
- Never store passwords, access tokens, backup codes, or secrets in Markdown, Notion, chat, or source control.
- Use organization-owned business accounts, not an employee’s personal login.
- Enforce two-factor authentication and role-based access.
- Maintain at least two approved administrators.
- Record account owner, platform ID, recovery channel, permission roles, and connection status in a restricted credential register.
- Revoke access immediately when a team member’s role ends.

---

## Publishing Controls

Every scheduled item contains:

- Content ID and version.
- Platform and account.
- Objective and audience.
- Approved copy, media, subtitles, and thumbnail.
- Canonical sources used.
- Rights and consent status.
- CTA and verified destination.
- UTM or campaign tracking.
- Approver and approval timestamp.
- Scheduled time and timezone.
- Monitoring owner.
- Rollback or takedown path.

Use an idempotency key to prevent duplicate posts.

---

## Fast-Track Classes

### Class A — Auto-Draft

Educational ideas, briefs, and unpublished variants may be generated automatically.

### Class B — Approval Queue

Evergreen content derived entirely from approved sources may be assembled and queued automatically, but requires one authorized approval before release.

### Class C — Enhanced Approval

Offers, customer stories, service-area claims, realistic generated media, and campaign content require marketing and business-owner approval.

### Class D — Manual Only

Prices, warranties, licenses, safety claims, emergencies, complaints, legal matters, payments, and personal data require specialist and owner review for every item.

---

## Failure Handling

- Stop if the canonical source is missing, Draft, HOLD, Unverified, expired, or conflicting.
- Stop if media rights or customer consent are absent.
- Stop if the platform account or destination link is ambiguous.
- Retry transient API failures with limits.
- Never retry a publish action without confirming whether the first request succeeded.
- Alert the owner for partial publishing across channels.
- Preserve the approved asset and audit record for investigation.

---

## Initial Implementation Sequence

1. Create and secure organization-owned accounts.
2. Complete business verification where available.
3. Approve profile identity, bios, links, and recovery controls.
4. Connect an approved scheduler or official API in a test environment.
5. Build the content and approval database.
6. Pilot draft-only automation.
7. Pilot approved scheduled posts on one account.
8. Validate duplicates, timing, links, analytics, and rollback.
9. Expand platform by platform.
10. Enable limited Class B release only after quality evidence.

No live posting is authorized by this document alone.

