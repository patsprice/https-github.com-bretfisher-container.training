# Secrets management and encryption at rest

- Secrets management = selectively and securely bring secrets to services

- Encryption at rest = protect against storage theft or prying

- Remember:

  - control plane is authenticated through mutual TLS, certs rotated every 90 days

  - control plane is encrypted with AES-GCM, keys rotated every 12 hours

  - data plane is not encrypted by default (for performance reasons),
    <br/>but can be IPSec enabled with a single `network create` option
