# Technology Stack

## Document Information

- **Owner:** Business Owner
- **Status:** Approved Direction / Hosting Verification Pending
- **Version:** 1.1
- **Last Updated:** 2026-07-24

## Purpose

This document defines the official technology stack for the AFAQ Alhayat Digital Platform.

---

# Canonical Implementation Decision

The canonical implementation direction is Next.js, TypeScript, React,
Tailwind CSS, Node.js, PostgreSQL, and Prisma.

Documents under `07_WEBSITE/WORDPRESS/` and the WordPress database research
document are retained as non-canonical historical research. They do not
authorize a WordPress or hybrid implementation unless the owner records a new
decision.

Hostinger compatibility remains a deployment gate and must be verified against
the actual purchased plan before infrastructure implementation.

---

# Frontend

Framework

- Next.js

Language

- TypeScript

UI Library

- React

Styling

- Tailwind CSS

Icons

- Lucide React

Animations

- Framer Motion

---

# Backend

Framework

- Next.js API Routes

Runtime

- Node.js

API Style

- REST API

---

# Database

Database Engine

- PostgreSQL

ORM

- Prisma ORM

---

# Authentication

- Secure Authentication
- Role-Based Access Control (RBAC)
- Session Management

---

# Storage

- Cloud Storage for images and documents

---

# SEO

- Server-Side Rendering (SSR)
- Metadata Management
- XML Sitemap
- Robots.txt
- Schema.org Markup
- Open Graph Tags

---

# Performance

- Image Optimization
- Lazy Loading
- Code Splitting
- Caching
- Compression

---

# Security

- HTTPS
- Input Validation
- CSRF Protection
- XSS Protection
- Secure Headers
- Environment Variables

---

# Analytics

- Google Analytics
- Google Search Console
- Google Tag Manager

---

# Development Tools

- Visual Studio Code
- Git
- GitHub
- Claude
- ChatGPT

---

# Deployment

Hosting

- Hostinger — confirmed by the business owner on 2026-07-23.
- The exact Hostinger plan, runtime support, database service, deployment
  method, limits, region, backups, staging support, and SSH/CI capabilities
  require technical verification before the stack is deployed.

Production Domain

- https://afaqalhayatae.com
- Canonical apex versus `www` redirect must be validated during deployment.

Continuous Integration

- GitHub Actions (planned)

Backup

- Automated Backups

Monitoring

- Error Logging
- Performance Monitoring

---

# Technology Principles

- Scalable
- Secure
- SEO-First
- Mobile-First
- Accessible
- Maintainable
- AI-Friendly

---

End of Document
