# Security Review Checklist

## Input Validation

- [ ] All user inputs are validated and sanitized
- [ ] Input size limits are enforced
- [ ] Type checking is performed before processing
- [ ] File upload validation (type, size, content)
- [ ] URL validation for external resources

## Authentication & Authorization

- [ ] Authentication required for protected endpoints
- [ ] Session management is secure (timeout, regeneration)
- [ ] Password requirements meet security standards
- [ ] Multi-factor authentication where appropriate
- [ ] Authorization checks on all resources
- [ ] Principle of least privilege applied

## Data Protection

- [ ] No hardcoded secrets, API keys, or passwords
- [ ] Sensitive data encrypted at rest
- [ ] Sensitive data encrypted in transit (HTTPS/TLS)
- [ ] PII handling complies with regulations (GDPR, CCPA)
- [ ] Secure password hashing (bcrypt, Argon2)

## Injection Vulnerabilities

- [ ] SQL injection prevention (parameterized queries)
- [ ] NoSQL injection prevention
- [ ] Command injection prevention
- [ ] LDAP injection prevention
- [ ] XML injection prevention

## Cross-Site Scripting (XSS)

- [ ] All user-generated content is escaped
- [ ] Content Security Policy (CSP) headers set
- [ ] HTML sanitization for rich text
- [ ] DOM-based XSS prevention

## Cross-Site Request Forgery (CSRF)

- [ ] CSRF tokens on state-changing operations
- [ ] SameSite cookie attribute set
- [ ] Origin/Referer header validation

## Dependencies

- [ ] No known vulnerabilities in dependencies
- [ ] Dependencies are up to date
- [ ] Unused dependencies removed
- [ ] Dependency integrity verification (lock files)

## Error Handling

- [ ] No sensitive information in error messages
- [ ] Stack traces not exposed to users
- [ ] Proper logging without sensitive data
- [ ] Rate limiting on error-prone endpoints

## API Security

- [ ] API authentication implemented
- [ ] Rate limiting configured
- [ ] Request size limits enforced
- [ ] CORS configured properly
- [ ] API versioning in place

## Configuration

- [ ] Security headers configured (HSTS, X-Frame-Options, etc.)
- [ ] Debug mode disabled in production
- [ ] Secure defaults for all settings
- [ ] Environment-specific configurations separated
