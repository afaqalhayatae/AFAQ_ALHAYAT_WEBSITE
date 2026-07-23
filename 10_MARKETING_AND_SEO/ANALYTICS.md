# Marketing Analytics

## Status

Framework approved for design; platforms, identifiers, consent model,
baselines, and numeric targets require owner and technical approval.

## Measurement Layers

- Acquisition: source, medium, campaign, landing content
- Engagement: meaningful page and content interactions
- Intent: call, WhatsApp, form, booking-start actions
- Conversion: verified inquiry, qualified lead, confirmed booking
- Service outcome: completion, satisfaction, complaint, repeat request
- Content outcome: assisted conversions, organic visibility, reuse efficiency

## Key Event Design

GA4 key events and Google Ads conversions must represent actions important to
the business, not every interaction. Use separate events for:

- `lead_form_submit`
- `phone_click`
- `whatsapp_click`
- `booking_start`
- `booking_complete`
- `qualified_lead`
- `service_complete`

The final names require technical validation against the approved event
taxonomy. Click events are intent signals; they must not be reported as
qualified leads or completed services.

Where the sales outcome happens offline, connect the original lead identifier
to qualified and completed outcomes through an approved privacy-safe process.
Enhanced conversions or offline imports require consent, legal review, correct
hashing/handling, and compliance with the platform's customer-data policies.

## Event Requirements

Every event needs a stable name, business meaning, trigger, properties, data
owner, retention rule, consent classification, QA procedure, and downstream
consumer.

## Guardrails

- Do not send direct personal contact details to advertising or analytics tools
  without an approved lawful basis and implementation.
- Separate test, duplicate, spam, and internal activity.
- Do not claim revenue attribution without a documented model.
- Report uncertainty, missing data, and material tracking changes.

## Operating Reviews

- Daily: tracking failures, spend anomalies, broken forms, call/WhatsApp route
- Weekly: search terms, lead quality, landing-page performance, budget pacing
- Monthly: channel attribution, qualified outcomes, service/location demand,
  content contribution, and experiment decisions
- Quarterly: measurement design, consent, retention, platform changes, and
  target reset

## Official References

- [GA4 key events](https://support.google.com/analytics/answer/9267568)
- [GA4 attribution](https://support.google.com/analytics/answer/10596866)
- [Google Ads web conversions](https://support.google.com/google-ads/answer/16560108)
- [Enhanced conversions](https://support.google.com/google-ads/answer/9888656)
