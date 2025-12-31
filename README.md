# Static Portfolio Website on AWS for Upcoming Dental Grad

## Project Overview
This project documents the design, deployment, and automation of a production-grade static website hosted on AWS. The website was created for my girlfriend, who is currently in dental school and preparing for her board exams in Summer 2026. The goal was to provide her with a professional, reliable personal site she can use during graduation, residency applications, and early career networking.

Beyond the website itself, this project demonstrates real-world cloud architecture, security best practices, and CI/CD automation using AWS and GitHub Actions.

---

## Challenge
Dental students often rely on PDFs, email attachments, or informal profiles when graduating and applying for residencies or professional opportunities. These methods:
- Lack a centralized, professional online presence
- Are difficult to update or version over time
- Do not scale well for sharing credentials, achievements, or updates
- Provide little control over branding, performance, or reliability

At the same time, I wanted to build a hands-on AWS project that went beyond tutorials and demonstrated practical, employer-relevant cloud skills.

---

## What I Did
I designed and implemented a fully automated static website hosting solution using AWS services and modern DevOps practices:

- Built a static HTML/CSS website tailored to a healthcare professional audience
- Hosted the site using Amazon S3 with static website hosting
- Secured global HTTPS delivery using Amazon CloudFront and AWS Certificate Manager
- Configured DNS using Amazon Route 53 (with a domain purchased externally)
- Automated deployments using GitHub Actions and OpenID Connect (OIDC)
- Implemented cache invalidation to ensure updates are immediately visible
- Applied AWS security best practices for encryption and access control

All infrastructure decisions were made to balance simplicity, cost efficiency, security, and real-world applicability.

---

## Solution & Impact
The final solution provides a fast, secure, and professional personal website that my girlfriend can use to:
- Share academic achievements, certifications, and milestones
- Present herself professionally during graduation and residency applications
- Easily update content without relying on third parties
- Maintain a permanent, branded online presence early in her career

From a technical perspective, this project demonstrates my ability to:
- Design cloud-native architectures on AWS
- Secure static workloads using IAM, OIDC, and encryption
- Build CI/CD pipelines that deploy to production automatically
- Translate a real personal need into a scalable technical solution

This was not a demo project — it was built for real use, real users, and long-term value.

## Architecture Overview

GitHub Repository (production branch)
|
| GitHub Actions (OIDC)
v
Amazon S3 (Static Website Hosting)
|
v
Amazon CloudFront (HTTPS + CDN)
|
v
Amazon Route 53 (Custom Domain DNS)

---

## Technologies Used

### AWS Services
- **Amazon S3**
  - Static website hosting
  - Default encryption enabled (SSE-S3)
- **Amazon CloudFront**
  - Global content delivery (CDN)
  - HTTPS enforcement
  - Cache invalidation on deploy
- **AWS Certificate Manager (ACM)**
  - TLS certificate for custom domain
- **Amazon Route 53**
  - DNS management and domain routing
- **AWS IAM**
  - OIDC-based role for GitHub Actions
  - No long-lived AWS credentials

### DevOps & Automation
- **GitHub Actions**
  - Automated deployments on push to `production` branch
  - Secure authentication using OpenID Connect (OIDC)
- **CloudFront Cache Invalidation**
  - Ensures updates propagate immediately worldwide

### Web Technologies
- HTML
- CSS
- Static asset hosting

---

## Deployment Workflow
1. Developer pushes changes to the `production` branch  
2. GitHub Actions authenticates to AWS using OIDC  
3. Website files are synced to the S3 bucket  
4. CloudFront cache is invalidated  
5. Updated content is served globally over HTTPS  

---

## Security Considerations
- No AWS access keys stored in GitHub
- IAM role scoped to least-privilege permissions
- S3 bucket encrypted at rest
- CloudFront enforces HTTPS-only access
- Public access limited to static content delivery

---

## Impact

### Personal Impact
This project provides a polished, professional web presence for my girlfriend as she completes dental school and prepares for board examinations, graduation, and early-career opportunities. The site serves as a long-term professional asset that can evolve alongside her career, supporting applications, networking, and personal branding.

### Professional / Technical Impact
From an engineering perspective, this project demonstrates:
- Real-world AWS architecture used in production environments
- Secure CI/CD pipelines leveraging modern authentication (OIDC)
- Cloud security best practices (least privilege, encryption, HTTPS)
- Ability to translate a non-technical personal need into a scalable technical solution
- End-to-end ownership across design, implementation, deployment, and documentation

---

## Future Enhancements
- Infrastructure as Code (Terraform)
- Automated frontend testing
- Custom error pages and centralized logging
- Analytics integration
- AWS WAF for additional edge security

---

## Author
Created and maintained by **Gage**  
ERP / Cloud / Data Consultant
