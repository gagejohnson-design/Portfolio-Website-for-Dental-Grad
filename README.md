Static Website Hosting on AWS (S3 + CloudFront + Route 53)
Overview

This project demonstrates how to design, deploy, and operate a secure, globally distributed static website on AWS using Amazon S3, CloudFront, Route 53, and ACM.

The solution follows AWS best practices for security, performance, and scalability while remaining simple and cost-effective.
It was implemented end-to-end, including domain management, HTTPS, encryption, and CI/CD-style updates from GitHub.

Architecture Summary

Amazon S3 hosts static website assets (HTML, CSS, images)

Amazon CloudFront provides HTTPS, caching, and global content delivery

AWS Certificate Manager (ACM) manages SSL/TLS certificates

Amazon Route 53 handles DNS routing

GitHub serves as the source of truth for website code

High-Level Architecture Flow

User requests the website via a custom domain

DNS resolves through Route 53

CloudFront serves cached content over HTTPS

CloudFront fetches origin content from S3 when needed

S3 stores encrypted static files securely

AWS Services Used
Service	Purpose
Amazon S3	Static website storage
Amazon CloudFront	CDN, HTTPS termination
AWS Certificate Manager	SSL/TLS certificates
Amazon Route 53	DNS management
GitHub	Source control & deployment workflow
Security Design

S3 Default Encryption enabled using SSE-S3

Bucket Key disabled (not cost-effective for static websites)

Public access blocked at the bucket level

CloudFront Origin Access Control (OAC) restricts direct S3 access

HTTPS enforced via CloudFront viewer policies

No hard-coded secrets stored in repository

Deployment Process

Static site files are stored in a GitHub repository

Updates are pushed to GitHub

Files are uploaded to the S3 bucket (manually or via automation)

CloudFront automatically serves updated content

Cache invalidation used when immediate refresh is required

DNS & Domain Configuration

Domain purchased via third-party registrar (Squarespace)

DNS hosted in Amazon Route 53

Registrar nameservers updated to Route 53

Alias A-record points to CloudFront distribution

Encryption & Compliance

At-rest encryption: SSE-S3

In-transit encryption: TLS 1.2+ via CloudFront

Least-privilege IAM access model

Aligns with AWS Well-Architected Framework (Security & Reliability pillars)

Cost Considerations

S3 static hosting: minimal monthly cost

CloudFront: pay-per-use CDN pricing

Route 53: low fixed hosted zone fee

ACM certificates: free

Designed to stay within low-cost personal project budgets

Key Skills Demonstrated

AWS Cloud Architecture

DNS & Domain Management

HTTPS & Certificate Management

Cloud Security Best Practices

CDN & Performance Optimization

Infrastructure Design & Documentation

GitHub-based deployment workflow

Why This Project Matters

This project mirrors real-world production patterns used by companies hosting marketing sites, documentation portals, and lightweight web applications.

It demonstrates the ability to:

Design secure cloud architectures

Work across multiple AWS services

Make cost-aware architectural decisions

Document systems clearly for technical stakeholders

Future Enhancements

GitHub Actions for automated deployments

Infrastructure as Code using Terraform or AWS CDK

Monitoring with CloudWatch metrics

WAF integration for enhanced security

Author

Built and maintained by Gage
Cloud / Data / Systems Consultant
AWS-focused infrastructure project
