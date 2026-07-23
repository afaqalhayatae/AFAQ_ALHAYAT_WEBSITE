# Pinterest Growth and Search Strategy

**Status:** Approved Architecture / Account and Website Connection Pending  
**Priority:** Core Organic Growth Channel

---

## Strategic Objective

Build Pinterest into a durable visual-search and website-traffic engine for AFAQ Alhayat.

Pinterest is not a duplicate feed for Instagram. Each Pin should answer a searchable customer need, earn saves, and lead to a relevant service, guide, checklist, or location page.

The long-term advantage comes from:

- Searchable evergreen content.
- High-quality original visuals.
- Clear board architecture.
- Strong website destinations.
- Consistent publication.
- Performance-led iteration.

---

## Foundation

Before scaling content:

- Create or convert to an organization-owned Pinterest Business account.
- Use the approved company name, logo, biography, and canonical website.
- Enable two-factor authentication and role-based access.
- Claim the official website through an approved HTML tag, file, or DNS method.
- Confirm Pinterest Analytics access.
- Install Pinterest Tag and conversion measurement only after privacy and consent review.
- Configure a secure scheduler or official Pinterest API connection.
- Keep credentials and tokens outside source control and Notion.

One website may be claimed by only one Pinterest account. Account ownership must therefore be resolved before verification.

---

## Search Architecture

### Keyword Sources

Research terms by:

- Customer problems.
- Service category.
- Property type.
- Room or facility.
- Seasonal need.
- Prevention and maintenance question.
- Approved UAE location.
- Pinterest search suggestions and performance data.

Keywords must describe real page content. Location terms are prohibited until the relevant coverage is approved.

### Board Structure

Boards should be stable search destinations with clear titles and descriptions.

Initial board candidates, subject to service approval:

- Pest Control Tips
- Home Cleaning Guides
- Deep Cleaning Checklists
- Water Tank Care
- AC Maintenance Tips
- Plumbing Maintenance
- Electrical Safety and Maintenance
- Villa and Apartment Care
- Office and Facility Care
- UAE Seasonal Home Maintenance
- Before and After — Verified Projects Only

Create separate Arabic boards or a deliberate bilingual taxonomy after keyword research; do not mix languages randomly.

### Sections

Use sections only when they improve browsing, for example by problem, property type, or approved service. Avoid an excessive hierarchy that weakens board focus.

---

## Pin-to-Page Model

Every Pin maps to one canonical destination:

- Service page.
- Useful guide.
- Checklist.
- FAQ.
- Approved location page.
- Booking or quotation landing page.

The destination must deliver the promise made by the image, title, and description.

Do not send every Pin to the homepage. Do not create a Pin when no high-quality destination exists.

---

## Content Pillars

1. **Step-by-step guides** — useful preparation, prevention, and maintenance.
2. **Checklists** — printable or saveable household and facility tasks.
3. **Problem identification** — approved signs, causes, and safe next steps.
4. **Premium spaces** — clean, organized, well-maintained UAE properties.
5. **Verified transformations** — truthful projects with consistent photography and consent.
6. **Seasonal planning** — approved, locally relevant maintenance moments.
7. **Service process** — inspection, preparation, quality control, and follow-up.
8. **Short video education** — concise vertical explanations with captions.

Never publish invented results, customer stories, credentials, prices, guarantees, or safety claims.

---

## Creative System

### Image Pins

- Prefer a `2:3` vertical composition.
- Use authentic, premium photography or approved original graphics.
- Add a short, readable benefit or checklist title.
- Keep Arabic and English typography consistent with the Design System.
- Use one idea per Pin.
- Preserve safe margins and mobile readability.
- Avoid clutter, tiny text, generic stock imagery, and poster-like advertisements.

### Video Pins

- Use a strong cover image.
- Show the problem, useful process, and result quickly.
- Include captions and sound-off comprehension.
- Use a vertical mobile-first composition.
- Keep branding restrained and visible.

### Variants

One approved source asset may generate multiple genuinely useful variants:

- Different hook.
- Different crop.
- Arabic or English.
- Checklist or how-to framing.
- Service or property-type framing.

Variants must not become near-duplicate spam.

---

## Metadata Standard

Every Pin requires:

- Clear title built around one natural search intent.
- Useful description that adds context.
- Relevant board and section.
- Canonical HTTPS destination.
- Approved UTM parameters.
- Meaningful alternative text.
- Language designation in the content workflow.
- Asset and source version.
- Rights and approval status.

Hashtags are secondary to clear topics, titles, descriptions, boards, visuals, and destination relevance.

---

## Publishing Automation

Pinterest supports official creation of image and video Pins and management of boards through its API after application connection and authorization.

Approved flow:

`Canonical page → approved creative brief → asset variants → metadata validation → human approval → scheduler/API → publish → Pin ID log → analytics → optimization`

Automation must:

- Use `boards:read`, `boards:write`, `pins:read`, and `pins:write` only when required.
- Prevent duplicate creation with an idempotency key.
- Confirm the intended board and destination.
- Stop on Draft, HOLD, Unverified, conflicting, or expired facts.
- Record Pin ID, URL, asset version, approver, and publish time.
- Never mass-create low-value or near-duplicate Pins.

---

## Content Cadence

Pinterest recommends regular creation of original Pins. AFAQ’s exact cadence will be based on production capacity and quality evidence.

Start with a controlled pilot:

- Build complete board architecture.
- Publish a sustainable weekly set of original Pins.
- Test image, checklist, and video formats.
- Review search terms, saves, outbound clicks, and conversions weekly.
- Expand winning topics and retire weak or misleading patterns.

Consistency is more important than one large upload followed by inactivity.

---

## Measurement

Primary measures:

- Qualified outbound clicks.
- Engaged sessions on the destination page.
- Enquiry and booking conversions.
- Saves.
- Search impressions by topic.
- Performance by board, Pin format, service, language, and destination.
- Assisted conversions.
- Growth of claimed-domain distribution.

Follower count and impressions alone do not define success.

---

## Ninety-Day Execution Plan

### Days 1–15 — Foundation

- Secure the Business account.
- Claim the website.
- Approve profile identity and account ownership.
- Confirm analytics and privacy-safe conversion measurement.
- Research Arabic and English search demand.
- Approve board taxonomy.

### Days 16–45 — Content Library

- Produce initial original Pin families from approved services and guides.
- Build Arabic and English creative templates.
- Connect every Pin to a strong destination.
- Start controlled weekly publication.
- Log results and search terms.

### Days 46–90 — Scale Winners

- Increase production around proven themes.
- Add video and verified project formats.
- Improve landing pages using Pinterest visitor behaviour.
- Pilot approved API or scheduler automation.
- Consider paid promotion only for proven organic assets and measurable destinations.

---

## Launch Gate

- [ ] Business account ownership and administrators are confirmed.
- [ ] Website is claimed by the correct account.
- [ ] Profile name, bio, logo, link, and contact facts are approved.
- [ ] Board taxonomy and keywords are approved.
- [ ] At least one strong destination exists per launch topic.
- [ ] Arabic and English creative templates pass design review.
- [ ] Asset rights and customer consent are documented.
- [ ] Pinterest Tag or API measurement passes privacy review.
- [ ] Scheduler/API uses least privilege and duplicate prevention.
- [ ] Approval, monitoring, and rollback owners are assigned.
- [ ] No placeholder or unverified fact can publish.

---

## Official References

- Claim a website: https://help.pinterest.com/en/business/article/claim-your-website
- Create boards and Pins with the API: https://developers.pinterest.com/docs/work-with-organic-content-and-users/create-boards-and-pins/
- How to make Pins: https://business.pinterest.com/en-us/how-to-make-pins/
- Pinterest Developer Platform: https://developers.pinterest.com/

