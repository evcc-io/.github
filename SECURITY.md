# Security Policy

## Supported Versions

Security updates are provided for the latest release version of evcc.

| Version  | Supported |
| -------- | --------- |
| latest   | ✅        |
| < latest | ❌        |

## Reporting Vulnerabilities

To report a security vulnerability:

1. **DO NOT** create a public GitHub issue
2. Send details to the maintainers:
   - via E-Mail: [info@evcc.io](mailto:info@evcc.io)
   - via Slack: https://evcc.io/slack (DM to `andig`, `naltatis` or `premultiply`)
   - via GitHub Security Advisory: https://github.com/evcc-io/evcc/security/advisories/new

Include in your report:

- Description of the vulnerability
- Steps to reproduce
- Affected versions
- Potential impact

### Coordinated Disclosure

We follow responsible disclosure - we'll work with you on appropriate timelines based on severity and complexity. Critical issues get priority, and we're flexible if you need more time for research.

## Response Timeline

We are an open source project and not full-time maintainers.
While we take security seriously and will do our best to respond quickly, we cannot guarantee specific response times.

- We aim to acknowledge reports within 24-72 hours
- Updates will be provided as we investigate
- Resolution time depends on severity and complexity

## Scope

In scope:

- evcc core application
- official packages and containers (apt, Docker, GitHub Releases, ...)
- configuration security
- evcc.io service endpoints (telemetry, sponsors, ...)
- evcc images (Raspberry Pi, ...)
- mobile app

Out of scope:

- third-party integrations (e.g. Home Assistant Addon)
- user configurations
- hardware devices
- upstream dependencies (Linux, Docker, ...)

## Incident Response Plan

### What qualifies as a security incident

Security incidents requiring this response process:

- Vulnerabilities in evcc software (core application, official Docker images, mobile apps)
- Compromised release/build pipeline or malicious releases
- Breach of evcc cloud services or APIs
- Compromise of evcc infrastructure

**Not covered**: Vulnerabilities in upstream dependencies, third-party integrations, or user configurations.

### Severity Classification

- **Critical**:

  - Remote control of EV chargers, vehicles, or energy systems without authentication
  - Exposure of sensitive data via cloud APIs (user credentials, location data, energy usage)
  - Malicious releases or compromised distribution channels

- **Medium**:

  - Bypass of local authentication (web UI, API access from local network)
  - Exposure of configuration data (device credentials, network settings)
  - Build pipeline compromise affecting integrity

- **Low**:
  - Information disclosure of non-sensitive data (system info, anonymized usage stats)
  - Local privilege escalation within evcc process

### Response Process

1. **Initial Response** (24-72 hours)

   - Breathe and make a coffee
   - Acknowledge vulnerability receipt
   - Assign one of the maintainers as incident lead
   - Assess severity and impact
   - Begin investigation

2. **Mitigation**

   - Disable affected cloud endpoints if applicable
   - Remove compromised releases/packages from distribution channels
   - Coordinate with vendors and distribution partners
   - Issue emergency patches if needed

3. **Communication**

   - **Always notify**: Slack community, GitHub (Discussions or Issues)
   - **Severe vulnerabilities**: Pinned GitHub Discussions post, website/README banners, social media
   - Share general nature of vulnerability (not full details during active response)
   - Include security information in release notes

4. **Resolution & Disclosure**
   - Publish detailed security advisory with full technical details
   - Document lessons learned internally
   - Implement preventive security improvements

### Distribution Channels

During vulnerability response, we may need to coordinate with:

- Docker Hub, Cloudsmith package repositories
- Mobile app stores (Google Play, Apple App Store, F-Droid)
- Package managers (Homebrew, apt repositories)
- Hardware vendors shipping devices with preinstalled evcc

### Vendor Coordination

For vulnerabilities affecting integrations, we may notify:

- Integration platforms (Home Assistant, openHAB, ...)
- Vehicle manufacturers, EV charger manufacturers
- Inverter/storage system vendors
- Solar forecast and energy provider services
