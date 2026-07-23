# Global Settings Engine

## Purpose

This document defines the centralized configuration system for the AFAQ Alhayat platform.

All global business information, integrations, branding, communication channels, SEO defaults, tracking codes, and operational settings must be managed from one unified location.

No page, template, or component should hard-code global business data.

---

# Architecture Principles

The Global Settings Engine must be:

- Centralized
- Secure
- Dynamic
- Multilingual
- API-Ready
- AI-Ready
- Scalable
- Easy to Manage

---

# 1. Company Information

Store:

- Company Name (Arabic)
- Company Name (English)
- Commercial Name
- Company Description (Arabic)
- Company Description (English)
- Trade License Number
- VAT Number
- Company Registration Details

---

# 2. Contact Information

Store:

- Primary Phone
- Secondary Phone
- WhatsApp Number
- Emergency Hotline
- Email Address
- Customer Support Email
- Sales Email

All phone numbers must support:

- Click to Call
- WhatsApp
- Schema
- Dynamic Display
- Conversion Tracking

---

# 3. Office Information

Store:

- Head Office
- Branches
- Address (Arabic)
- Address (English)
- Working Hours
- Holiday Schedule
- Google Maps URL
- Latitude
- Longitude

---

# 4. Live Maps

Store:

- Google Maps API Key
- Default Map Center
- Default Zoom
- Place Autocomplete
- Reverse Geocoding
- Live GPS Support
- Service Radius
- Coverage Validation

---

# 5. Company Branding

Store:

- Main Logo
- White Logo
- Dark Logo
- Mobile Logo
- Favicon
- Apple Touch Icon
- Brand Colors
- Typography
- Default Images

---

# 6. Social Media

Store official URLs for:

- Facebook
- Instagram
- LinkedIn
- X (Twitter)
- TikTok
- Snapchat
- YouTube
- Threads

---

# 7. SEO Defaults

Store:

- Default SEO Title (AR)
- Default SEO Title (EN)
- Default Meta Description (AR)
- Default Meta Description (EN)
- Default OG Image
- Robots Settings
- Canonical Rules
- Sitemap Settings
- hreflang Configuration

---

# 8. Schema Defaults

Support:

- Organization Schema
- LocalBusiness Schema
- Website Schema
- ContactPoint Schema
- Social Profiles
- Logo
- Geo Coordinates

---

# 9. Analytics

Store IDs for:

- Google Analytics 4
- Google Tag Manager
- Google Search Console
- Google Ads
- Meta Pixel
- TikTok Pixel
- Snapchat Pixel
- Microsoft Clarity
- LinkedIn Insight Tag

---

# 10. Communication

Configure:

- WhatsApp Templates
- Email Templates
- SMS Templates
- Push Notifications
- Booking Notifications
- Technician Notifications

---

# 11. Booking Defaults

Store:

- Default Service Duration
- Booking Buffer Time
- Working Days
- Working Hours
- Emergency Booking Rules
- Maximum Daily Capacity

---

# 12. Performance

Manage:

- Cache Settings
- CDN Settings
- Image Optimization
- Lazy Loading
- Compression
- WebP / AVIF
- Core Web Vitals Targets

---

# 13. Security

Manage:

- SSL
- Firewall
- Login Protection
- API Keys
- reCAPTCHA
- Backup Schedule
- Audit Logs

---

# 14. AI Settings

Configure:

- AI Assistant
- Knowledge Base
- Smart Search
- AI Recommendations
- AI FAQ
- AI Content Assistant

---

# 15. Future Integrations

Reserve settings for:

- Payment Gateways
- CRM
- ERP
- Mobile Applications
- Fleet Tracking
- Live Technician Tracking
- Multi-Branch Management
- GCC Expansion

---

# Golden Rule

Every page, component, widget, email, notification, and API response must retrieve shared business information from the Global Settings Engine.

Never duplicate global business data.

Update once.

Reflect everywhere.

---

End of Document