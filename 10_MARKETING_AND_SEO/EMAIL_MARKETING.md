# Email Marketing and Automation Standard

**Status:** Approved Architecture / Live Setup Pending  
**Owner:** Marketing with Business and Privacy Approval

---

## Objective

Build a permission-based bilingual email channel that converts enquiries, supports customers, generates repeat business, and measures commercial outcomes without damaging domain reputation or customer trust.

Email marketing is an owned channel. It must complement SEO, social media, customer service, and paid media rather than depend on purchased audiences.

---

## Audience Rules

- Marketing email is sent only to contacts with recorded, verifiable consent.
- Purchased, rented, scraped, or third-party lists are prohibited.
- Transactional contacts are not automatically marketing subscribers.
- Consent source, timestamp, wording, language, and withdrawal status must be retained.
- Unsubscribe requests take effect immediately across all marketing journeys.
- Inactive or stale audiences require suppression or reconfirmation.
- Segments must use relevant customer interests and approved service history, not sensitive profiling.

---

## Technical Readiness

Before the first campaign:

- Use a verified sending domain controlled by the company.
- Configure SPF and DKIM.
- Configure DMARC and monitor alignment.
- Send through TLS.
- Set up a branded From name and monitored Reply-To address.
- Configure bounce, complaint, and suppression handling.
- Provide visible unsubscribe and standards-compliant one-click unsubscribe.
- Connect Google Postmaster Tools when applicable.
- Separate transactional and promotional flows where operationally appropriate.
- Test Arabic RTL and English LTR rendering across major inboxes and mobile devices.

No campaign may launch from an unauthenticated or placeholder domain.

---

## Core Lifecycle Journeys

### Welcome

Triggered by explicit subscription:

1. Confirm subscription and expectations.
2. Introduce trusted service categories.
3. Offer useful guidance and preference selection.
4. Invite a relevant enquiry without aggressive selling.

### Enquiry Follow-Up

Triggered only after a legitimate enquiry and according to consent:

- Confirm receipt.
- Explain the next operational step.
- Provide relevant approved preparation information.
- Escalate unanswered or high-value enquiries to the responsible team.

### Booking and Service

Transactional messages may include:

- Booking confirmation.
- Preparation guidance.
- Appointment reminder.
- Completion or report availability.
- Feedback request.

Transactional messages must not disguise promotional content.

### Retention

Use approved service intervals and customer preferences to provide:

- Relevant maintenance reminders.
- Educational seasonal guidance.
- Approved related-service suggestions.
- Re-engagement with frequency control.

Never invent a service interval or claim urgency without an approved source.

---

## Content Standard

Every email requires:

- One clear purpose.
- Accurate subject and preview text.
- Recognizable sender identity.
- Useful bilingual or language-preference content.
- One primary call to action.
- Canonical links with approved tracking parameters.
- Verified contact information.
- Accessible structure, readable text, and meaningful image alternatives.
- Physical or legal sender information where required.
- Visible preference and unsubscribe controls.

Avoid excessive capitalization, punctuation, image-only emails, misleading urgency, unsupported discounts, and link-heavy clutter.

---

## Automation Flow

`Consent event → audience validation → segmentation → content assembly → fact validation → approval → test send → scheduled send → delivery monitoring → conversion measurement → learning`

Each automated journey requires:

- Named owner.
- Entry and exit conditions.
- Frequency cap.
- Suppression rules.
- Canonical content sources.
- Approval class.
- Error and pause mechanism.
- Versioned template.
- Measurable outcome.

---

## Measurement

Primary measures:

- Delivered rate.
- Bounce and complaint rates.
- Unsubscribe rate.
- Click rate.
- Qualified enquiry rate.
- Booking conversion rate.
- Revenue or pipeline contribution where reliable.
- Performance by language, service, location, and journey.

Open rate is directional only and must not be treated as a definitive business outcome.

---

## Launch Gate

- [ ] Sending domain and provider are approved.
- [ ] SPF, DKIM, DMARC, TLS, and alignment pass.
- [ ] Consent and suppression records are operational.
- [ ] Privacy and unsubscribe workflows are tested.
- [ ] Canonical contact details are verified.
- [ ] Arabic and English templates pass inbox tests.
- [ ] Links, analytics, and conversion events pass.
- [ ] Test emails have been reviewed on mobile and desktop.
- [ ] Journey owner and emergency pause control are assigned.
- [ ] No Draft, HOLD, or Unverified facts can enter a send.

---

## Official Operational References

- Google Email Sender Guidelines: https://support.google.com/mail/answer/81126
- Mailchimp Email Marketing Compliance: https://mailchimp.com/help/about-compliance-for-email-marketing/
- Mailchimp Permission Guidance: https://mailchimp.com/help/the-importance-of-permission/

