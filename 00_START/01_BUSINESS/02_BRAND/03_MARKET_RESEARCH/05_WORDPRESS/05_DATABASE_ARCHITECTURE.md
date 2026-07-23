# Database Architecture

## Purpose

This document defines the official database architecture for the AFAQ Alhayat Enterprise Platform.

The architecture is designed to support high traffic, enterprise scalability, multilingual content, advanced SEO, AI integrations, live booking, technician management, and future GCC expansion.

---

# Architecture Strategy

The platform uses a Hybrid Database Architecture.

## WordPress Native Tables

Use for:

- Pages
- Blog Articles
- Custom Post Types
- Taxonomies
- Media
- Menus

---

## Custom Database Tables

Use for high-volume operational data.

Avoid storing large operational datasets inside wp_postmeta.

---

# Core Database Modules

## Customers

Store:

- Customer Profile
- Contact Information
- Saved Addresses
- Booking History
- Preferred Language
- Marketing Consent
- Loyalty Points

---

## Bookings

Store:

- Booking Number
- Service
- Location
- Technician
- Schedule
- Status
- Notes
- Attachments
- Payment Status
- GPS Coordinates

---

## Technicians

Store:

- Technician Profile
- Skills
- Certifications
- Working Hours
- Live Status
- Assigned Jobs
- Performance Metrics
- Current GPS Location

---

## Pricing Engine

Store:

- Base Prices
- Dynamic Pricing
- Area Pricing
- Emergency Fees
- Seasonal Pricing
- Promotions
- Corporate Pricing

---

## Coverage Engine

Store:

- Supported Emirates
- Supported Areas
- Coverage Radius
- Response Time
- Service Availability

---

## Live Maps

Store:

- Latitude
- Longitude
- Google Place ID
- Route Information
- Navigation Status

---

## Reviews

Store:

- Ratings
- Comments
- Review Source
- Verification Status

---

## AI Knowledge

Store:

- Embeddings Reference
- Knowledge Articles
- AI Search Index
- AI FAQ Links

---

## Notifications

Store:

- WhatsApp Logs
- Email Logs
- SMS Logs
- Push Notifications

---

## Analytics

Store:

- Conversion Events
- Booking Funnels
- Call Tracking
- Campaign Performance

---

# Performance Principles

- Normalize operational data.
- Index frequently queried fields.
- Cache heavy queries.
- Archive historical records.
- Minimize unnecessary joins.

---

# Scalability

The database must support:

- Millions of visitors
- Hundreds of thousands of bookings
- Thousands of services
- Thousands of locations
- Multiple countries
- Multiple companies (future SaaS)
- AI integrations
- Mobile applications

---

# Security

Sensitive tables must include:

- Encryption where appropriate
- Audit Logs
- Role-Based Access
- Backup Strategy
- Soft Delete
- Data Retention Policies

---

# Future Ready

The architecture must support:

- Multi-Branch
- Multi-Tenant (Future SaaS)
- ERP Integration
- CRM Integration
- Payment Gateways
- Fleet Management
- Technician Live Tracking
- AI Automation

---

# Golden Rule

Content belongs in WordPress.

Operational data belongs in optimized custom database tables.

This separation guarantees long-term performance and scalability.

---

End of Document