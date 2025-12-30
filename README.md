# Static Website Hosting on AWS (S3 + CloudFront + Route 53)

This project demonstrates how to design, deploy, and operate a **secure, globally distributed static website** on AWS using modern cloud best practices.

The site is hosted on Amazon S3, delivered through Amazon CloudFront for HTTPS and performance, and accessible via a custom domain managed with Amazon Route 53. Website content is version-controlled in GitHub and deployed to AWS in a repeatable, production-style workflow.

---

## Architecture Overview

The architecture follows AWS best practices for static web hosting:

- **Amazon S3** stores static website assets (HTML, CSS, images)
- **Amazon CloudFront** provides HTTPS, CDN caching, and edge delivery
- **AWS Certificate Manager (ACM)** issues and manages TLS certificates
- **Amazon Route 53** handles DNS resolution for the custom domain
- **GitHub** stores source code and deployment documentation

End users access the site securely via HTTPS through CloudFront, while S3 remains private and protected.

---

## Key AWS Services Used

- Amazon S3 (static content storage)
- Amazon CloudFront (CDN + HTTPS)
- AWS Certificate Manager (TLS certificates)
- Amazon Route 53 (DNS)
- IAM (secure access control)

---

## Domain & DNS Strategy

- Domain purchased externally (Squarespace)
- Nameservers delegated to Route 53
- Route 53 hosted zone manages all DNS records
- Root and `www` domains point to CloudFront using Alias records

This approach allows AWS to fully manage routing, SSL, and performance while keeping domain ownership flexible.

---

## Security Design

Security is intentionally layered:

- **S3 bucket is not public**
- Access is restricted to CloudFront only
- **Default encryption enabled (SSE-S3)**
- HTTPS enforced at the CDN level
- TLS certificates managed by ACM (no manual renewals)

This prevents direct bucket access and aligns with AWS security best practices.

---

## Deployment Workflow

1. Website files are stored and versioned in GitHub
2. Changes are committed locally
3. Static assets are uploaded to S3
4. CloudFront caches are invalidated when needed
5. DNS routes traffic to CloudFront automatically

This keeps deployments simple, auditable, and repeatable.

---

## Why This Architecture

This design was chosen because it is:

- **Low cost** (no servers, no EC2)
- **Highly available** (global edge locations)
- **Secure by default**
- **Production-grade**
- **Scalable without redesign**

It mirrors how many real-world companies host marketing pages, landing pages, and documentation sites.

---

## Skills Demonstrated

- Cloud architecture design
- Static website hosting on AWS
- CDN configuration and caching strategy
- DNS and domain management
- TLS/HTTPS implementation
- S3 security hardening
- GitHub-based project documentation
- Production-style deployment thinking

---

## Future Enhancements

Potential improvements include:

- CI/CD with GitHub Actions
- Infrastructure as Code (Terraform)
- Custom error pages
- Monitoring with CloudWatch
- WAF integration for security filtering

---

## Project Purpose

This project was built as a **hands-on cloud engineering exercise** to demonstrate practical AWS knowledge beyond certifications, focusing on real-world architecture, security, and deployment patterns.

