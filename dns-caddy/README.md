# Caddy and Internal DNS

## Overview

I configured internal DNS and Caddy so I can access homelab services using simple `.home.arpa` hostnames instead of remembering IP addresses and port numbers.

Caddy handles HTTPS and reverse proxies requests to the correct backend service.

## What I Implemented

- Internal DNS records
- `.home.arpa` hostnames
- HTTPS for internal services
- Reverse proxying
- DNS access over WireGuard

## What I Learned

- DNS resolution
- Reverse proxies
- TLS certificates
- Service routing
- VPN DNS troubleshooting
