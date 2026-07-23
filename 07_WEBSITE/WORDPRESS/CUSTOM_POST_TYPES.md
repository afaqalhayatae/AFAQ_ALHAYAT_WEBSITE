# Custom Post Types Architecture

## Purpose

This document defines the official Custom Post Types architecture for the AFAQ Alhayat WordPress platform.

The structure must support large-scale growth, multilingual content, advanced Local SEO, booking workflows, maps, analytics, AI integrations, and future expansion across the UAE and GCC.

---

# Architecture Principles

Every Custom Post Type must be:

- Scalable
- Multilingual
- SEO-Ready
- Schema-Ready
- API-Ready
- Searchable
- Filterable
- Secure
- Easy to Manage
- Compatible with future mobile applications

---

# 1. Services

Post Type Key:

`service`

Purpose:

Store all company services and future service categories.

Examples:

- AC Maintenance
- AC Repair
- AC Cleaning
- Plumbing
- Electrical Maintenance
- Deep Cleaning
- Villa Cleaning
- Pest Control
- Painting
- Handyman
- Water Tank Cleaning

Required Fields:

- Arabic Title
- English Title
- Arabic Slug
- English Slug
- Arabic Short Description
- English Short Description
- Arabic Full Content
- English Full Content
- Service Category
- Service Subcategory
- Featured Image
- Gallery
- Benefits
- Service Process
- Pricing Type
- Starting Price
- Estimated Duration
- Emergency Availability
- Property Types
- Supported Emirates
- Supported Areas
- Related Services
- FAQs
- Reviews
- Booking CTA
- Phone CTA
- WhatsApp CTA
- SEO Metadata
- Schema Configuration
- Status
- Sort Order

---

# 2. Service Categories

Post Type Key:

`service_category`

Purpose:

Organize services into scalable groups.

Examples:

- Maintenance
- Cleaning
- Pest Control
- AC Services
- Plumbing
- Electrical
- Painting
- Handyman
- Water Services

Required Fields:

- Arabic Name
- English Name
- Arabic Description
- English Description
- Icon
- Image
- Parent Category
- SEO Metadata
- Schema Settings
- Display Order

---

# 3. Emirates

Post Type Key:

`emirate`

Purpose:

Store all Emirates and support future country expansion.

Examples:

- Dubai
- Abu Dhabi
- Sharjah
- Ajman
- Ras Al Khaimah
- Fujairah
- Umm Al Quwain

Required Fields:

- Arabic Name
- English Name
- Country
- Arabic Slug
- English Slug
- Introduction
- Latitude
- Longitude
- Map Zoom Level
- Google Maps URL
- Service Availability
- Service Areas
- Local FAQs
- Local Reviews
- SEO Metadata
- LocalBusiness Schema
- Hero Image

---

# 4. Areas

Post Type Key:

`area`

Purpose:

Store cities, communities, districts, neighborhoods, and service zones.

Examples:

- Jumeirah
- Dubai Marina
- Al Barsha
- Mirdif
- Al Nahda
- Al Majaz
- Al Nuaimiya

Required Fields:

- Arabic Name
- English Name
- Parent Emirate
- Parent Area
- Area Type
- Arabic Slug
- English Slug
- Latitude
- Longitude
- Google Place ID
- Google Maps URL
- Service Coverage Status
- Delivery Radius
- Area Description
- Area FAQs
- Area Reviews
- SEO Metadata
- Local Schema
- Featured Image

---

# 5. Service Location Pages

Post Type Key:

`service_location`

Purpose:

Generate scalable pages combining service, Emirate, and area.

Examples:

- AC Maintenance in Dubai
- Villa Cleaning in Jumeirah
- Pest Control in Sharjah
- Plumbing in Ajman

Required Fields:

- Linked Service
- Linked Emirate
- Linked Area
- Arabic Page Title
- English Page Title
- Arabic Content
- English Content
- Unique Local Introduction
- Local Benefits
- Local Service Process
- Local FAQs
- Local Reviews
- Phone CTA
- WhatsApp CTA
- Booking CTA
- Map Section
- Coordinates
- Nearby Areas
- Related Services
- SEO Metadata
- Canonical URL
- hreflang
- Service Schema
- LocalBusiness Schema
- FAQ Schema
- Breadcrumb Schema
- Indexing Status
- Content Quality Score

Important Rule:

Pages must not be generated with thin, duplicate, or low-value content.

Every indexable page must provide meaningful and unique local value.

---

# 6. Bookings

Post Type Key:

`booking`

Purpose:

Store customer service requests and operational workflow data.

Required Fields:

- Booking Number
- Customer
- Service
- Emirate
- Area
- Full Address
- Latitude
- Longitude
- Google Place ID
- Preferred Date
- Preferred Time
- Urgency Level
- Property Type
- Description
- Uploaded Images
- Assigned Technician
- Booking Status
- Payment Status
- Quotation
- Internal Notes
- Customer Notes
- Source Channel
- UTM Data
- Created Date
- Updated Date

Booking Statuses:

- New
- Contacted
- Quotation Required
- Quotation Sent
- Confirmed
- Assigned
- On The Way
- Arrived
- In Progress
- Completed
- Cancelled
- Follow-Up Required

---

# 7. Customers

Post Type Key:

`customer`

Purpose:

Store customer profiles and service history.

Required Fields:

- Full Name
- Phone
- WhatsApp
- Email
- Preferred Language
- Customer Type
- Saved Addresses
- Latitude
- Longitude
- Booking History
- Reviews
- Notes
- Marketing Consent
- Loyalty Points
- Referral Code
- Customer Status
- Created Date

---

# 8. Technicians

Post Type Key:

`technician`

Purpose:

Manage technicians, skills, availability, jobs, and performance.

Required Fields:

- Full Name
- Phone
- Email
- Profile Image
- Employee ID
- Languages
- Specializations
- Assigned Emirates
- Assigned Areas
- Availability Status
- Current Latitude
- Current Longitude
- Live Tracking Permission
- Assigned Jobs
- Completed Jobs
- Rating
- Performance Score
- Documents
- Expiry Dates
- Employment Status

---

# 9. Reviews

Post Type Key:

`review`

Purpose:

Store verified customer feedback.

Required Fields:

- Customer
- Booking
- Service
- Emirate
- Area
- Rating
- Arabic Review
- English Review
- Review Source
- Google Review URL
- Verification Status
- Featured Status
- Response
- Published Date

---

# 10. FAQs

Post Type Key:

`faq`

Purpose:

Centralize reusable questions and answers.

FAQ Types:

- General
- Service
- Emirate
- Area
- Booking
- Pricing
- Warranty
- Emergency
- Payment

Required Fields:

- Arabic Question
- English Question
- Arabic Answer
- English Answer
- FAQ Type
- Related Services
- Related Emirates
- Related Areas
- Display Priority
- Schema Enabled
- Status

---

# 11. Offers

Post Type Key:

`offer`

Purpose:

Manage offers, discounts, coupons, and seasonal campaigns.

Required Fields:

- Arabic Title
- English Title
- Offer Type
- Discount Type
- Discount Value
- Coupon Code
- Start Date
- End Date
- Applicable Services
- Applicable Emirates
- Applicable Areas
- Customer Eligibility
- Terms
- CTA
- Tracking Code
- Status

---

# 12. Projects

Post Type Key:

`project`

Purpose:

Showcase completed work, case studies, and before-and-after results.

Required Fields:

- Arabic Title
- English Title
- Service
- Emirate
- Area
- Property Type
- Problem
- Solution
- Results
- Before Images
- After Images
- Completion Date
- Customer Review
- Related Services
- SEO Metadata
- Schema

---

# 13. Before & After Galleries

Post Type Key:

`before_after`

Purpose:

Store visual service proof.

Required Fields:

- Service
- Emirate
- Area
- Before Image
- After Image
- Caption Arabic
- Caption English
- Date
- Technician
- Customer Permission
- SEO Alt Text
- Status

---

# 14. Blog Articles

Post Type Key:

`knowledge_article`

Purpose:

Publish educational, SEO, seasonal, and local content.

Required Fields:

- Arabic Title
- English Title
- Arabic Content
- English Content
- Article Category
- Related Service
- Related Emirate
- Related Area
- Featured Image
- Author
- Publish Date
- Update Date
- SEO Metadata
- Article Schema
- FAQ Schema
- Internal Links
- Conversion CTA

---

# 15. Knowledge Base

Post Type Key:

`knowledge_base`

Purpose:

Store internal and public help content for customers, technicians, and AI assistants.

Knowledge Types:

- Customer Help
- Technician Guide
- Service Procedure
- Troubleshooting
- Safety Guide
- Booking Help
- Admin Help
- AI Reference

Required Fields:

- Audience
- Arabic Content
- English Content
- Related Service
- Related System
- Access Level
- Version
- Last Reviewed Date
- Status

---

# 16. Notifications

Post Type Key:

`notification`

Purpose:

Store email, WhatsApp, SMS, dashboard, and push notification events.

Required Fields:

- Recipient
- Notification Type
- Channel
- Message Template
- Related Booking
- Scheduled Date
- Sent Date
- Delivery Status
- Failure Reason
- Retry Count

---

# 17. Service Areas and Coverage Rules

Post Type Key:

`coverage_rule`

Purpose:

Control whether a service is available in a specific location.

Required Fields:

- Service
- Emirate
- Area
- Coverage Status
- Priority Level
- Service Fee Adjustment
- Minimum Booking Value
- Estimated Response Time
- Emergency Availability
- Technician Capacity
- Valid From
- Valid Until

---

# 18. Pricing Rules

Post Type Key:

`pricing_rule`

Purpose:

Support flexible and scalable pricing.

Required Fields:

- Service
- Emirate
- Area
- Property Type
- Pricing Model
- Base Price
- Minimum Price
- Emergency Surcharge
- Distance Surcharge
- Weekend Surcharge
- Material Cost
- Tax Rules
- Valid From
- Valid Until
- Status

---

# 19. Branches

Post Type Key:

`branch`

Purpose:

Support future multi-branch operations.

Required Fields:

- Branch Name
- Country
- Emirate
- Address
- Latitude
- Longitude
- Phone
- WhatsApp
- Email
- Working Hours
- Manager
- Service Coverage
- Technicians
- Google Maps URL
- Google Business URL
- Status

---

# 20. Countries

Post Type Key:

`country`

Purpose:

Prepare the platform for future GCC expansion.

Required Fields:

- Arabic Name
- English Name
- Country Code
- Currency
- Time Zone
- Default Language
- Supported Languages
- Tax Settings
- Phone Prefix
- Map Center
- Status

---

# Relationships

The architecture must support these relationships:

- Service belongs to Service Category.
- Area belongs to Emirate.
- Emirate belongs to Country.
- Service Location links Service + Emirate + Area.
- Booking links Customer + Service + Location + Technician.
- Review links Customer + Booking + Service + Location.
- Pricing Rule links Service + Location + Property Type.
- Coverage Rule links Service + Emirate + Area.
- Project links Service + Emirate + Area.
- FAQ may link to multiple Services and Locations.
- Articles may link to Services, Emirates, and Areas.

---

# Multilingual Requirements

Every public content type must support:

- Arabic content
- English content
- Arabic SEO metadata
- English SEO metadata
- Arabic slugs where appropriate
- English slugs
- hreflang
- RTL and LTR layouts
- Language-specific internal links

Arabic remains the primary language.

---

# Maps Requirements

Location-related content types must support:

- Latitude
- Longitude
- Google Place ID
- Google Maps URL
- Live Map Display
- Address Autocomplete
- GPS Location Selection
- Service Radius
- Coverage Validation
- Route Navigation
- Future Live Technician Tracking

---

# SEO Requirements

Every public content type must support:

- SEO Title
- Meta Description
- Canonical URL
- Index / Noindex
- Open Graph
- Twitter Cards
- Schema Type
- Breadcrumbs
- Internal Links
- Related Content
- Sitemap Inclusion
- Last Modified Date

---

# Phone Number Requirements

Phone and WhatsApp data must come from centralized global settings.

The system must support dynamic insertion into:

- Visible Headings
- Hero Sections
- CTA Buttons
- Sticky Mobile Buttons
- Service Pages
- Location Pages
- Contact Pages
- Booking Pages
- Schema
- Tracking Events

Do not hard-code phone numbers in every content record.

---

# API Requirements

Each relevant Custom Post Type should be available through a secure REST API or GraphQL layer where needed.

The API must support:

- Filtering
- Pagination
- Search
- Multilingual responses
- Role-based permissions
- Mobile application access
- AI assistant access
- External CRM integration

---

# Performance Requirements

The architecture must avoid:

- Excessive database queries
- Unnecessary post meta usage
- Duplicate content generation
- Uncontrolled page creation
- Heavy plugin dependence

Use optimized tables or custom database tables where WordPress post meta becomes inefficient.

---

# Security Requirements

Sensitive content types such as bookings, customers, technicians, pricing rules, and notifications must:

- Not be publicly indexed
- Require authentication
- Use role-based permissions
- Log important changes
- Validate all inputs
- Protect personal data
- Use secure API access

---

# Scalability Goal

The Custom Post Types architecture must support:

- Hundreds of services
- Thousands of areas
- Tens of thousands of service-location pages
- Multiple branches
- Multiple countries
- Multiple languages
- High booking volume
- AI integrations
- Mobile applications
- Long-term growth without rebuilding the platform

---

End of Document