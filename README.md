# VRLY - AI-Powered Workflow Automation for Psychotherapists

<div align="center">

[![Bun](https://img.shields.io/badge/Bun-1.0+-black?logo=bun&logoColor=white)](https://bun.sh)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-blue?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare-Workers-orange?logo=cloudflare&logoColor=white)](https://workers.cloudflare.com/)
[![Astro](https://img.shields.io/badge/Astro-4.0+-purple?logo=astro&logoColor=white)](https://astro.build/)
[![License: BSL-1.1](https://img.shields.io/badge/License-BSL%201.1-blue)](LICENSE)

**Empowering psychotherapists with intelligent automation, so they can focus on what matters most: their patients.**

[Website](https://vrly.de) • [Documentation](#-documentation) • [Contact](mailto:info@vrly.de)

</div>

---

## 🎯 Overview

VRLY is a specialized technology partner exclusively for psychotherapists in Hannover, Germany. We combine expertise in AI, workflow automation, and project management with deep understanding of practice workflows and strict DSGVO compliance to give therapists valuable time back and make their practices future-proof.

### Key Features

- 🤖 **AI-Powered Automation** - Intelligent workflow automation for administrative tasks
- 🔒 **DSGVO & §203 StGB Compliant** - Built with German data protection laws at the core
- ⚡ **Edge-First Architecture** - Powered by Cloudflare Workers for blazing-fast performance
- 🏥 **Practice Management Integration** - Compatible with leading PVS systems (Elefant, Psyprax, Epikur)
- 📊 **Multi-Tenant Platform** - Secure isolation and customization for each practice

## 📚 Documentation

This project is documented following our internal standards. Below is an overview of the key documentation files found in the `docs/` directory.

### [Branding (`BRANDING.md`)](docs/BRANDING.md)

Outlines the company's brand identity, including our vision, mission, values, and visual and language guidelines.

### [Code of Conduct (`CODE_OF_CONDUCT.md`)](docs/CODE_OF_CONDUCT.md)

Our commitment to a positive and ethical environment. It details our ethics policy, scope, and reporting guidelines.

### [Development Cycle (`DEVELOPMENT-CYCLE.md`)](docs/DEVELOPMENT-CYCLE.md)

Describes our 2-week sprint cycle, followed by a 1-week cooldown period for planning and system maintenance.

### [Estimates (`ESTIMATES.md`)](docs/ESTIMATES.md)

Details our T-shirt sizing method (S, M, L, XL) for issue estimation, along with time estimates for each size.

### [Labels (`LABELS.md`)](docs/LABELS.md)

Provides a comprehensive list of GitHub labels used for issue tracking, categorized by type, priority, and status.

### [PR Workflow (`PR-WORKFLOW.md`)](docs/PR-WORKFLOW.md)

Explains the pull request process, from creating a PR to the review and merge criteria, including the use of V-Codes for security.

### [Security (`SECURITY.md`)](docs/SECURITY.md)

Covers our security policy, including technical and organizational measures, and the V-Code system for confidential information.

### [Statuses (`STATUSES.md`)](docs/STATUSES.md)

Defines the statuses used in our project management tools to track the progress of tasks and projects.

### [Versioning (`VERSIONING.md`)](docs/VERSIONING.md)

Our versioning strategy, which follows Semantic Versioning (SemVer) standards for all our packages and releases.

---

## 🏗️ Monorepo Structure

This repository uses [Bun workspaces](https://bun.sh/docs/install/workspaces) to manage multiple packages:

```text
monorepo/
├── packages/
│   ├── platform/         # Core VRLY platform (Cloudflare Workers)
│   ├── website/          # Marketing website (Astro + Cloudflare Workers)
│   ├── clients/          # Client-specific implementations
│   ├── integrations/     # Third-party service integrations
│   ├── shared/           # Shared libraries and design system
│   └── internal/         # Internal tools and utilities
│       └── email-signature-builder/  # Email signature generator
├── scripts/              # Automation and utility scripts
├── docs/                 # Documentation
└── .github/              # GitHub Actions workflows
```

## 🚀 Quick Start

### Prerequisites

- [Bun](https://bun.sh) >= 1.0
- [Node.js](https://nodejs.org/) >= 18 (for some tooling compatibility)
- [Cloudflare Account](https://dash.cloudflare.com/sign-up) (for deployment)

### Installation

```bash
# Clone the repository
git clone https://github.com/vrly-de/monorepo.git
cd monorepo

# Install dependencies
bun install

# Copy environment variables
cp .dev.vars.example .dev.vars
```

### Development

```bash
# Start all development servers
bun dev

# Start specific packages
bun dev:platform           # Platform API
bun dev:website            # Marketing website
bun dev:email-signature    # Email signature builder

# Run tests
bun test

# Type checking
bun type-check

# Linting
bun lint
```

## 📦 Package Overview

### `@vrly-de/platform`

Core platform powering all VRLY services. Built on Cloudflare Workers for Platforms, providing multi-tenant infrastructure, AI capabilities, and workflow automation.

### `@vrly-de/website`

Public-facing marketing website built with Astro. Showcases services, provides documentation, and handles lead generation.

### `@vrly-de/shared`

Shared utilities, TypeScript types, and the VRLY Design System. Ensures consistency across all applications.

### `@vrly-de/internal`

Internal tools for business operations:

- **Email Signature Builder** - Tool for generating standardized email signatures
- Billing automation
- Analytics tools

### `@vrly-de/integrations`

Pre-built integrations with third-party services, including practice management systems, workflow automation, and calendar/email services.

### `@vrly-de/clients`

Client-specific implementations and customizations, organized by vertical (e.g., psychotherapists).

## 🛠️ Technology Stack

- **Runtime**: [Bun](https://bun.sh) - Fast all-in-one JavaScript runtime
- **Language**: [TypeScript](https://www.typescriptlang.org/) - Type-safe development
- **Backend**: [Cloudflare Workers](https://workers.cloudflare.com/) - Serverless edge computing
- **Frontend**: [Astro](https://astro.build/) - Modern web framework
- **Database**: [Cloudflare D1](https://developers.cloudflare.com/d1/) - Serverless SQL
- **Storage**: [Cloudflare R2](https://developers.cloudflare.com/r2/) - Object storage
- **AI**: [Cloudflare Workers AI](https://developers.cloudflare.com/workers-ai/) - Edge AI inference

## 📝 Scripts

```bash
# Development
bun dev:website          # Start marketing website server with wrangler types and astro dev
bun dev:email-signature  # Start email signature builder

# Build & Deploy
bun build:website        # Build website with wrangler types, astro check, and astro build
bun preview:website      # Preview website deployment with wrangler dev
bun deploy               # Deploy to staging environment
bun deploy:production    # Deploy to production environment

# Utilities
bun clean                # Clean build artifacts, node_modules, .wrangler, and .astro
bun format               # Format code with prettier
```

## 🧪 Testing & Quality (TODO)

```bash
# bun test                 # Run all tests
# bun lint                 # Run linting
# bun type-check           # Run type checking
```

## 🔐 Security

Security is paramount in healthcare technology:

- All data is encrypted in transit and at rest
- DSGVO and §203 StGB compliant by design
- Regular security audits and penetration testing

For security concerns, please email security@vrly.de

## 📄 License

We use the Business Source License 1.1 (BSL-1.1). See [LICENSE](LICENSE) for details.

---

<div align="center">

**Built with ❤️ by [heyFlorentin](https://github.com/heyFlorentin) and the VRLY team**  
_VRLY automatisiert Effizienz mit Künstlicher Intelligenz_

</div>
