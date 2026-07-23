# WordPress Architecture

## Purpose

This document defines the official WordPress architecture for the AFAQ Alhayat Digital Platform.

The architecture must support large-scale growth, bilingual content, advanced SEO, service bookings, customer management, and future integrations without requiring a full rebuild.

---

# Core Platform

Content Management System:

- WordPress

Primary Language:

- Arabic

Secondary Language:

- English

Direction Support:

- Arabic RTL
- English LTR

---

# Architecture Principles

The WordPress platform must be:

- Scalable
- Modular
- Fast
- Secure
- SEO-First
- Mobile-First
- Easy to Manage
- API-Ready
- Compatible with AI workflows

---

# Recommended WordPress Structure

The platform should use:

- Custom WordPress Theme
- Custom Post Types
- Custom Taxonomies
- Custom Fields
- Reusable Gutenberg Blocks
- REST API
- Role-Based Access Control
- Structured SEO Templates
- Cloudflare Integration

---

# Custom Post Types

Create the following Custom Post Types:

## Services

Used for:

- Maintenance Services
- Cleaning Services
- Pest Control Services
- AC Services
- Plumbing
- Electrical
- Painting
- Handyman
- Water Tank Cleaning
- Future Services

---

## Emirates

Used for:

- Dubai
- Abu Dhabi
- Sharjah
- Ajman
- Ras Al Khaimah
- Fujairah
- Umm Al Quwain

---

## Areas

Used for:

- Cities
- Communities
- Residential Areas
- Commercial Areas
- Service Zones

Each area should be linked to an Emirate.

---

## Service Locations

Used to create scalable pages combining:

- Service
- Emirate
- Area

Example:

- AC Maintenance in Dubai
- Villa Cleaning in Sharjah
- Pest Control in Ajman

---

## Blog Posts

Used for:

- Educational Articles
- Maintenance Guides
- Cleaning Tips
- Pest Control Advice
- Local SEO Content
- Seasonal Content

---

## Reviews

Used for:

- Customer Testimonials
- Google Reviews
- Service Feedback
- Featured Reviews

---

## FAQs

Used for:

- General Questions
- Service Questions
- City Questions
- Booking Questions
- Pricing Questions

---

## Offers

Used for:

- Seasonal Promotions
- Service Packages
- Discounts
- Coupons
- Limited-Time Offers

---

## Bookings

Used for:

- Customer Service Requests
- Appointment Details
- Service Status
- Assigned Technician
- Customer Notes

---

## Technicians

Used for:

- Technician Profiles
- Specializations
- Availability
- Assigned Jobs
- Performance Data

---

# Custom Taxonomies

Create taxonomies for:

- Service Category
- Service Type
- Emirate
- Area
- Property Type
- Customer Type
- Urgency Level
- Blog Category
- Offer Type

---

# Custom Fields

Each service should support:

- Arabic Title
- English Title
- Arabic Description
- English Description
- SEO Title Arabic
- SEO Title English
- Meta Description Arabic
- Meta Description English
- Primary Keyword
- Secondary Keywords
- Service Benefits
- Service Process
- FAQ Selection
- Featured Image
- Gallery
- Call-to-Action Text
- Phone Number
- WhatsApp Number
- Booking Form
- Schema Data
- Related Services
- Related Cities
- Related Areas

---

# Contact Data Source

All contact details must be stored in one centralized settings area.

Required fields:

- Company Name Arabic
- Company Name English
- Primary Phone
- Secondary Phone
- WhatsApp Number
- Email
- Google Maps URL
- Business Address
- Working Hours
- Social Media Links

The website must pull contact data dynamically from this central source.

Do not hard-code the phone number separately on every page.

---

# Phone Number Usage

The phone number should appear in:

- Header
- Mobile Header
- Footer
- Contact Page
- Booking Page
- Service Pages
- City Pages
- Area Pages
- Sticky Call Button
- WhatsApp Button
- Schema Markup
- Conversion Tracking

The phone number may be included in visible page headings when commercially useful.

Do not automatically place the phone number in every SEO title or meta title because this may create repetitive and low-quality search snippets.

---

# URL Structure

Recommended URLs:

Arabic:

- /ar/services/
- /ar/services/ac-maintenance/
- /ar/dubai/
- /ar/dubai/ac-maintenance/
- /ar/dubai/jumeirah/ac-maintenance/

English:

- /en/services/
- /en/services/ac-maintenance/
- /en/dubai/
- /en/dubai/ac-maintenance/
- /en/dubai/jumeirah/ac-maintenance/

URLs should remain:

- Clean
- Short
- Logical
- Scalable
- Search-Friendly

---

# Multilingual System

The platform must support:

- Arabic as the default language
- English as the secondary language
- Separate SEO metadata for each language
- hreflang tags
- Arabic RTL layouts
- English LTR layouts
- Language-specific menus
- Language-specific slugs where appropriate

---

# Page Builder Strategy

Use native Gutenberg blocks or custom Gutenberg blocks.

Avoid unnecessary heavy page builders that may reduce performance.

Reusable blocks should include:

- Hero Section
- Service Cards
- Benefits Section
- Process Section
- FAQ Section
- Reviews Section
- Location Section
- Booking CTA
- WhatsApp CTA
- Phone CTA
- Before & After Gallery
- Related Services
- Related Areas

---

# Theme Requirements

The theme must be:

- Custom-Built
- Lightweight
- Responsive
- Accessible
- RTL-Compatible
- Translation-Ready
- Schema-Ready
- Core Web Vitals Optimized

---

# Plugin Strategy

Use the minimum number of plugins necessary.

Plugins should be selected based on:

- Security
- Performance
- Active Maintenance
- Compatibility
- Scalability

Avoid duplicate plugins that perform the same function.

---

# SEO Architecture

The WordPress platform must support:

- Dynamic SEO Templates
- Service Schema
- LocalBusiness Schema
- FAQ Schema
- Breadcrumb Schema
- Review Schema
- Article Schema
- XML Sitemaps
- Canonical URLs
- hreflang
- Internal Linking
- Image SEO
- Redirect Management

---

# Performance Architecture

Use:

- Cloudflare CDN
- Full Page Caching
- Object Caching
- Image Optimization
- WebP or AVIF
- Lazy Loading
- Minified Assets
- Database Optimization
- Limited Plugin Usage

---

# Security Architecture

Implement:

- Secure Hosting
- SSL
- Web Application Firewall
- Two-Factor Authentication for Admins
- Login Protection
- Role-Based Permissions
- Automated Backups
- Malware Scanning
- Activity Logging
- Secure File Uploads
- Regular Updates

---

# User Roles

Recommended roles:

## Administrator

Full access.

## Manager

Manage bookings, customers, services, and reports.

## Content Manager

Manage pages, services, blog posts, FAQs, and SEO content.

## Technician

View and update assigned jobs only.

## Customer

View personal bookings and account information.

---

# Booking Integration

The booking system should connect:

- Website Forms
- Customer Records
- Service Selection
- Location Selection
- Appointment Scheduling
- Technician Assignment
- Notifications
- Booking Status
- Admin Dashboard

---

# Future Integrations

The architecture must support future integration with:

- Mobile Applications
- Payment Gateways
- CRM
- WhatsApp API
- Email Automation
- SMS Notifications
- AI Chat Assistant
- Accounting Systems
- ERP
- Multi-Branch Management
- GCC Expansion

---

# Scalability Goal

The WordPress architecture should support:

- Hundreds of services
- Thousands of local landing pages
- Multiple languages
- High traffic
- Large content libraries
- Future mobile applications
- API-driven integrations

The platform must be designed to grow without requiring a complete structural rebuild.

---

End of Document