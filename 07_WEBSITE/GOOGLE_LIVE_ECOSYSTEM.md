# Google Live Ecosystem for the Website

**Status:** Approved Architecture / Verified Google Assets Required  
**Applies To:** Public website, booking journey, contact experience, local pages, analytics, and future customer portal

---

## Objective

Integrate live, verified Google services into the AFAQ Alhayat website to improve trust, location accuracy, discoverability, booking measurement, and customer experience.

“Google Live” in this project means live data and integrations from supported Google products. It does not mean the discontinued Google Business Profile Chat service.

---

## Supported Experience

### Live Google Map

The website may display an interactive Google Map using:

- Google Maps Embed API for a simple official place or directions experience.
- Maps JavaScript API only when custom interaction is genuinely required.
- Stable Google Place ID rather than an ambiguous text address.

The map must:

- Use the verified business location or approved service interaction.
- Load lazily.
- Provide a text address and “Open in Google Maps” alternative.
- Remain usable on mobile and by keyboard.
- Use an API key restricted by domain and API.
- Never expose customer or technician locations publicly.

### Live Place Information

Where technically and commercially justified, Google Places API may retrieve approved fields such as:

- Display name.
- Address.
- Google Maps URL.
- Phone number.
- Rating.
- Reviews or review link.
- Opening hours.

Google data is displayed according to current Maps Platform terms, attribution requirements, field availability, and billing controls.

The website must not overwrite the company’s canonical internal data with Google responses automatically. Differences enter a review queue.

### Verified Google Reviews

The website may show Google review information only when:

- The correct Place ID is confirmed.
- The display method complies with Google’s current API and attribution requirements.
- Review text, author attribution, time, and source remain accurate.
- Cached information respects platform rules.
- Moderation does not create a misleading impression.

Never use fabricated reviews, manually changed wording, combined ratings from unrelated sources, or a static rating presented as live.

Provide a direct approved link to read or leave a review where appropriate.

### Directions and Location Selection

Customers may:

- Open directions to an approved branch or destination.
- Search and validate a service address during booking.
- Place or adjust a location marker.
- Confirm the structured address.

Booking integrations follow `WORDPRESS/LIVE_MAPS_ARCHITECTURE.md`.

### Search and Business Profile

The Google Business Profile must:

- Be owned by the company or authorized representatives.
- Follow eligibility and service-area-business rules.
- Use verified NAP, hours, categories, website, and service information.
- Link to the canonical HTTPS website.
- Grant access through individual manager accounts, never shared passwords.

No location, branch, or service area may be created merely for SEO.

---

## Chat and Contact

Google Business Profile’s former native chat and call-history features ended on 31 July 2024.

The supported contact architecture is:

- Human-like AI assistant on the website under the approved assistant standard.
- Owner-review escalation.
- Verified phone and WhatsApp.
- Booking or enquiry form.
- Eligible Google Business Profile contact or business links where available.

The website must not advertise “Google Live Chat” as an active Google product.

---

## Google Measurement Layer

Subject to consent and privacy approval:

- Google Tag Manager.
- Google Analytics 4.
- Google Search Console.
- Google Ads conversion measurement.
- Call, WhatsApp, form, booking-start, and booking-complete events.
- Qualified-lead and completed-service feedback through an approved privacy-safe process.

Clicks are intent signals. They are not automatically qualified leads, bookings, or revenue.

Consent Mode must receive the user’s current choices before Google tags process applicable advertising or analytics signals.

---

## Search Console

Before launch:

- Verify the canonical domain property.
- Submit approved XML sitemaps.
- Monitor indexing, crawl issues, structured data, Core Web Vitals, manual actions, and security issues.
- Keep all language, canonical, redirect, and URL rules aligned with `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md`.

Search Console access must use role-based company accounts.

---

## Performance and Cost Controls

- Prefer Maps Embed API where its capabilities are sufficient.
- Load maps only near user interaction or viewport.
- Request only required Places fields through a field mask.
- Set Google Cloud budgets, alerts, quotas, and restricted keys.
- Keep server-only credentials off the client.
- Monitor failed requests and unexpected billing.
- Provide a useful static fallback if Google services are unavailable.
- Do not allow third-party scripts to block essential content.

---

## Privacy and Security

- Request geolocation only after a clear user action and explanation.
- Collect only the precision required for service delivery.
- Do not expose customer addresses in analytics URLs or event parameters.
- Restrict customer coordinates to authorized operations users.
- Define retention and deletion rules.
- Separate public map data from operational and future live-tracking data.
- Obtain valid consent before optional analytics or advertising processing.
- Use the current approved privacy policy and consent platform.

---

## Data Authority

| Data | Canonical Source | Google Role |
|---|---|---|
| Company contact facts | `02_BRAND/CONTACT_INFORMATION.md` | Verification and public channel |
| Publishable local profile | `02_BRAND/LOCAL_SEO_PROFILE.md` | Business Profile and Place entity |
| Service coverage | `03_MARKET/SERVICE_AREAS.md` | Never inferred from map reach |
| Service availability | `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md` | Never inferred from search results |
| Customer address | Approved booking system | Validation and routing |
| Reviews | Verified Google Place/API | Displayed with source attribution |
| Analytics meaning | `10_MARKETING_AND_SEO/ANALYTICS.md` | Measurement platform |

Google is an external distribution and data provider, not the internal owner of business truth.

---

## Implementation Sequence

1. Confirm verified company NAP and business model.
2. Identify or create the eligible Google Business Profile under owner control.
3. Confirm the correct Place ID.
4. Verify the canonical domain in Search Console.
5. Create a restricted Google Cloud project and keys.
6. Implement consent management and Tag Manager.
7. Add the lazy live map with an accessible fallback.
8. Add approved Place/review fields only if compliant and valuable.
9. Connect booking address validation.
10. Test analytics and Google Ads conversions.
11. Validate Arabic, English, mobile, accessibility, performance, security, and cost.
12. Launch with monitoring and rollback controls.

---

## Release Gate

- [ ] Legal business owner and authorized Google managers are confirmed.
- [ ] NAP and service-area data are approved.
- [ ] Business Profile eligibility and status are confirmed.
- [ ] Correct Place ID is recorded.
- [ ] Search Console domain ownership is verified.
- [ ] API keys are restricted and budgets/alerts are active.
- [ ] Map has an accessible text and external-link fallback.
- [ ] Reviews are authentic, attributed, current, and policy-compliant.
- [ ] Consent Mode and Tag Assistant tests pass.
- [ ] No personal address appears in page URLs or analytics payloads.
- [ ] Booking address and coverage decisions remain separate.
- [ ] Page speed and Core Web Vitals remain acceptable.
- [ ] Failure and rollback procedures are tested.

---

## Official References

- Maps Embed API: https://developers.google.com/maps/documentation/embed/get-started
- Places API Place Details: https://developers.google.com/maps/documentation/places/web-service/place-details
- Business Profile chat changes: https://support.google.com/business/answer/14919056
- Business Profile ownership: https://support.google.com/business/answer/3403100
- Consent Mode: https://developers.google.com/tag-platform/security/guides/consent

