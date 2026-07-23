# Live Maps Architecture

## Purpose

This document defines the live mapping system for the AFAQ Alhayat platform.

The system must support real-time location selection, customer address validation, technician navigation, and future live technician tracking.

---

# Objectives

The Live Maps system should:

- Improve booking accuracy.
- Reduce technician travel time.
- Support Local SEO.
- Improve customer experience.
- Enable future fleet management.

---

# Supported Map Provider

Primary

- Google Maps Platform

Future Support

- Mapbox
- OpenStreetMap

---

# Governing Integration Standard

The complete public-site integration, Google Business Profile, Place ID,
reviews, Search Console, analytics, consent, security, performance, and
authority rules are defined in:

- `../GOOGLE_LIVE_ECOSYSTEM.md`

This document remains the operational map and booking architecture. It must
not independently publish contact, coverage, review, or branch facts.

---

# Customer Features

Customers can:

- Search for an address.
- Pin their exact location.
- Use Current Location (GPS).
- Move the map pin.
- Save location coordinates.
- View service coverage.
- Open directions in Google Maps.

---

# Booking Integration

Each booking should store:

- Full Address
- Emirate
- Area
- Community
- Building Name
- Villa / Apartment Number
- Latitude
- Longitude
- Google Place ID

---

# Technician Features

Technicians should be able to:

- View customer location.
- Open navigation directly.
- View optimized route.
- Confirm arrival.
- Update job status.

Future versions may support live technician tracking.

---

# Admin Features

Administrators can:

- View all bookings on a map.
- Filter bookings by Emirate.
- Filter bookings by service.
- View technician locations (future).
- Analyze service coverage.

---

# Service Area Validation

The system should verify whether a customer location is inside the supported service area before confirming a booking.

---

# Local SEO

Every service area should support:

- Emirate
- City
- Community
- Coordinates
- Google Maps Link
- Structured Data

---

# Performance

Maps should:

- Load lazily.
- Use optimized API requests.
- Cache location lookups where possible.
- Minimize unnecessary API calls.

---

# Privacy

Customer location data must:

- Be stored securely.
- Be accessible only to authorized staff.
- Be used only for service delivery.
- Comply with applicable privacy regulations.

---

# Future Enhancements

Planned features include:

- Live technician tracking.
- ETA calculation.
- Route optimization.
- Multi-branch dispatching.
- Heat maps of service demand.
- AI-assisted technician assignment.

---

End of Document
