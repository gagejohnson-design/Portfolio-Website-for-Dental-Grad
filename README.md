# Static Portfolio Website on AWS (S3 + CloudFront + Route 53 + GitHub Actions)

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

---

## Architecture Overview
