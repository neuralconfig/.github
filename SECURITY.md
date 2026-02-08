# Security Policy

## Reporting Vulnerabilities

If you find a security issue in any neural\[config\] project, please email security@neuralconfig.com rather than opening a public issue.

Include:
- Description of the vulnerability
- Steps to reproduce
- Potential impact

## Security Practices

- Dependencies kept updated
- Secrets managed through environment variables, never hardcoded
- API credentials use OAuth2 or token-based auth
- Code linted and type-checked (mypy)
