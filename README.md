# AWS-Static-Website

## Project Overview
This repository hosts the static website for Joe Botha, a tattoo artist. The site is designed to showcase portfolio work, contact details, and an introduction to the artist. It is built with HTML, CSS, and JavaScript, and deployed using AWS services with a custom domain registered via GoDaddy.

 **AWS Services Integration**:
   - **Amazon S3**:
     - Hosted the static website files (HTML, CSS, JS, and images).
     - Configured as a static website endpoint.
   - **AWS Certificate Manager (ACM)**:
     - Secured the website with an SSL/TLS certificate to enable HTTPS.
   - **Amazon CloudFront**:
     - Configured a content delivery network (CDN) to improve performance and security.
     - Set up as a distribution layer to deliver content globally with reduced latency.
   - **Amazon Route 53**:
     - Configured the custom domain `joe-tattoo.co.za`.
     - Created A and CNAME records for seamless domain mapping.
   - **DNS and Propagation**:
     - Ensured proper DNS configuration for both root and www subdomains.
     - Verified DNS propagation globally.

## Deployment Highlights
- **Custom Domain**: [www.joe-tattoo.co.za](https://www.joe-tattoo.co.za)
- Files are version-controlled using GitHub, and deployed to AWS with secure and optimized configurations.
