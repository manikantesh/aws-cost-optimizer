# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability, please open an issue or contact the maintainers directly. Do **not** share sensitive information in public issues.

## Guidelines for Users
- **Never** commit AWS credentials, secrets, or `.tfstate` files.
- Use IAM roles with least privilege for Terraform operations.
- Review all modules before applying them in production.
- Keep your Terraform and AWS CLI tools up to date.
- Enable MFA on your AWS accounts.

## Maintainers
- Enable branch protection and code scanning in GitHub settings.
- Regularly review dependencies for vulnerabilities. 