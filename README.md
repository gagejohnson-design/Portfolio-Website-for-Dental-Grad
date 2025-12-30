# Girlfriend-Appreciation-Website

A simple, secure, and highly available **static website** built as a personal project and gift.  
The goal of this repository is to demonstrate a **clean, production-style AWS approach** to hosting static web content using modern best practices.

---

## Overview

This project hosts a static HTML/CSS website using AWS-managed services to achieve:

- Low cost
- High availability
- HTTPS by default
- Minimal operational overhead
- Clean separation of responsibilities (DNS, CDN, storage, CI/CD)

The site content itself is intentionally simple; the focus is on **architecture, security, and deployment quality**.

---

## Architecture

GitHub Repository
↓
GitHub Actions (CI/CD)
↓
Amazon S3 (Static Assets)
↓
Amazon CloudFront (CDN + HTTPS)
↓
Custom Domain (Route 53 DNS)

**Design principles:**
- No servers
- No backend unless required
- CDN as the public entry point
- Infrastructure that can scale without rework

---

## AWS Services Used

- **Amazon S3**
  - Stores static website files (HTML, CSS, images)
  - Default encryption enabled (SSE-S3)
- **Amazon CloudFront**
  - Global content delivery
  - HTTPS enforcement
  - Caching for performance
- **AWS Certificate Manager (ACM)**
  - Free TLS certificates for the custom domain
- **Amazon Route 53**
  - DNS hosting for the domain
- **GitHub Actions**
  - Automated deployments from GitHub to S3

---

## Security & Best Practices

- HTTPS enforced via CloudFront
- Encryption at rest enabled for all S3 objects
- No inbound ports or servers exposed
- IAM permissions scoped to minimum required access
- No long-lived credentials committed to the repository

This setup follows AWS-recommended patterns for static site hosting.

---

## Deployment Strategy

- All source files live in this GitHub repository
- A GitHub Actions workflow runs on pushes to the main branch
- The workflow synchronizes files to the S3 bucket
- CloudFront serves updated content globally

This ensures deployments are:
- Repeatable
- Auditable
- Low-risk
- Easy to roll forward

---


## Why This Approach

This architecture was chosen because it:

- Avoids unnecessary servers
- Keeps costs extremely low
- Uses managed AWS services wherever possible
- Matches real-world static hosting patterns
- Scales automatically without redesign

For a static website, this provides the highest return on simplicity.

---

