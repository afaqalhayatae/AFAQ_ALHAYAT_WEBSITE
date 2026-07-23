# Custom Taxonomies Architecture

## Purpose

This document defines the taxonomy architecture for the AFAQ Alhayat WordPress platform.

Taxonomies organize content, improve scalability, power advanced search and filtering, strengthen SEO, and support AI-driven recommendations.

---

# Architecture Principles

Every taxonomy must be:

- Hierarchical where appropriate
- Multilingual
- SEO-Ready
- API-Ready
- Searchable
- Filterable
- Reusable
- Future-Proof

---

# 1. Service Category

Taxonomy Key:

service_category

Examples:

- AC Services
- Cleaning
- Pest Control
- Plumbing
- Electrical
- Painting
- Handyman
- Water Services

---

# 2. Service Type

Taxonomy Key:

service_type

Examples:

- Installation
- Repair
- Preventive Maintenance
- Emergency
- Inspection
- Cleaning
- Disinfection

---

# 3. Emirate

Taxonomy Key:

emirate

Examples:

- Dubai
- Abu Dhabi
- Sharjah
- Ajman
- Ras Al Khaimah
- Fujairah
- Umm Al Quwain

---

# 4. Area

Taxonomy Key:

area

Examples:

- Jumeirah
- Dubai Marina
- Business Bay
- Al Barsha
- Al Nahda
- Al Majaz
- Al Rashidiya

Each Area belongs to exactly one Emirate.

---

# 5. Property Type

Taxonomy Key:

property_type

Examples:

- Apartment
- Villa
- Townhouse
- Office
- Retail Shop
- Restaurant
- Hotel
- Warehouse
- Factory
- School
- Hospital

---

# 6. Customer Type

Taxonomy Key:

customer_type

Examples:

- Residential
- Commercial
- Corporate
- Government
- Industrial

---

# 7. Urgency Level

Taxonomy Key:

urgency

Examples:

- Emergency
- Same Day
- Scheduled
- Preventive

---

# 8. Booking Status

Taxonomy Key:

booking_status

Examples:

- New
- Confirmed
- Assigned
- In Progress
- Completed
- Cancelled

---

# 9. Technician Skill

Taxonomy Key:

technician_skill

Examples:

- AC
- Plumbing
- Electrical
- Pest Control
- Painting
- Cleaning

---

# 10. Blog Category

Taxonomy Key:

blog_category

Examples:

- Maintenance Tips
- Cleaning Guides
- Pest Control Advice
- Seasonal Tips
- Home Care
- Business Maintenance

---

# 11. Blog Tags

Taxonomy Key:

blog_tag

Used for detailed article organization and internal linking.

---

# 12. FAQ Category

Taxonomy Key:

faq_category

Examples:

- Booking
- Pricing
- Warranty
- Services
- Payment
- Emergency

---

# 13. Offer Category

Taxonomy Key:

offer_category

Examples:

- Seasonal
- AMC
- New Customer
- Holiday
- Bundle Offer

---

# 14. Project Category

Taxonomy Key:

project_category

Examples:

- Residential
- Commercial
- Industrial
- Government

---

# 15. Review Category

Taxonomy Key:

review_category

Examples:

- AC
- Cleaning
- Plumbing
- Pest Control

---

# 16. Language

Taxonomy Key:

language

Values:

- Arabic
- English

---

# SEO Rules

Every taxonomy archive should support:

- SEO Title
- Meta Description
- Canonical URL
- Breadcrumbs
- Schema
- Internal Links
- Featured Content
- FAQ Section

---

# URL Examples

/services/ac-services/

/services/plumbing/

/dubai/

/dubai/jumeirah/

/blog/cleaning-guides/

---

# AI Requirements

Taxonomies must support:

- Semantic Search
- AI Recommendations
- Related Services
- Related Areas
- Smart Internal Linking

---

# Scalability Goal

The taxonomy system must support:

- Unlimited services
- Unlimited locations
- Unlimited blog categories
- Unlimited filters
- Multiple countries
- Multiple languages

Without structural changes.

---

End of Document