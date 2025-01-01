# AWS-Static-Website

## Project Overview
This repository contains a static website for showcasing the portfolio of tattoo artist Joe Botha. The website is hosted on AWS, leveraging modern DevOps practices to ensure seamless deployment, scalability, and security.

## Features
- **Static Website**: Built with HTML, CSS, and JavaScript.
- **Responsive Design**: Optimized for all screen sizes.
- **CI/CD Pipeline**: Automates the deployment of website files to an AWS S3 bucket.
- **Secure Hosting**: Utilizes HTTPS with CloudFront and AWS Certificate Manager.
- **Custom Domain**: Configured via Route 53 for `https://joe-tattoo.co.za`.

---

## Functions Implemented So Far

1. **Website Development**:
   - Designed a portfolio website with sections for **About Me**, **Portfolio**, and **Contact**.

2. **AWS S3 Hosting**:
   - Hosted the static website on an S3 bucket named `joe-tattoo.co.za`.
   - Enabled public read access for website files.

3. **AWS IAM Configuration**:
   - Created a custom IAM policy (`JoeTattooS3Policy`) to grant limited access to the S3 bucket.
   - Created an IAM user with **programmatic access** for GitHub Actions.

4. **GitHub Secrets Management**:
   - Stored the following secrets in the repository to securely enable CI/CD:
     - `AWS_ACCESS_KEY_ID`
     - `AWS_SECRET_ACCESS_KEY`
     - `AWS_REGION`

5. **CI/CD Pipeline with GitHub Actions**:
   - Configured a workflow (`deploy.yml`) to:
     - Sync files to the S3 bucket automatically whenever changes are pushed to the `main` branch.
     - Use the `aws-actions/configure-aws-credentials` plugin to authenticate securely.

6. **Domain and SSL Configuration**:
   - Configured the custom domain (`joe-tattoo.co.za`) using Route 53.
   - Deployed SSL via AWS Certificate Manager (ACM) for secure HTTPS access.
   - Integrated CloudFront for caching and performance optimization.

---

## Workflow Details
The CI/CD pipeline is defined in `.github/workflows/deploy.yml`:
- **Trigger**: Runs on every push to the `main` branch.
- **Actions**:
  1. Checks out the code from the repository.
  2. Configures AWS credentials using GitHub secrets.
  3. Deploys the website to the S3 bucket using `aws s3 sync`.
