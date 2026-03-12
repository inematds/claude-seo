<!-- Updated: 2026-03-06 -->

![Claude SEO](screenshots/cover-image.jpeg)

# Claude SEO

Comprehensive SEO analysis skill for Claude Code. Covers technical SEO, on-page analysis, content quality (E-E-A-T), schema markup, image optimization, sitemap architecture, AI search optimization (GEO), and strategic planning.

![SEO Command Demo](screenshots/seo-command-demo.gif)

[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://claude.ai/claude-code)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Installation

### One-Command Install (Unix/macOS/Linux)

```bash
curl -fsSL https://raw.githubusercontent.com/AgriciDaniel/claude-seo/main/install.sh | bash
```

### Manual Install

```bash
git clone https://github.com/AgriciDaniel/claude-seo.git
cd claude-seo
./install.sh
```

### Windows

```powershell
irm https://raw.githubusercontent.com/AgriciDaniel/claude-seo/main/install.ps1 | iex
```

## Quick Start

```bash
# Start Claude Code
claude

# Run a full site audit
/seo audit https://example.com

# Analyze a single page
/seo page https://example.com/about

# Check schema markup
/seo schema https://example.com

# Generate a sitemap
/seo sitemap generate

# Optimize for AI search
/seo geo https://example.com
```
### Demo:
[Watch the full demo on YouTube](https://www.youtube.com/watch?v=COMnNlUakQk)

**`/seo audit` — full site audit with parallel subagents:**

![SEO Audit Demo](screenshots/seo-audit-demo.gif)

## Commands

| Command | Description |
|---------|-------------|
| `/seo audit <url>` | Full website audit with parallel subagent delegation |
| `/seo page <url>` | Deep single-page analysis |
| `/seo sitemap <url>` | Analyze existing XML sitemap |
| `/seo sitemap generate` | Generate new sitemap with industry templates |
| `/seo schema <url>` | Detect, validate, and generate Schema.org markup |
| `/seo images <url>` | Image optimization analysis |
| `/seo technical <url>` | Technical SEO audit (8 categories) |
| `/seo content <url>` | E-E-A-T and content quality analysis |
| `/seo geo <url>` | AI Overviews / Generative Engine Optimization |
| `/seo plan <type>` | Strategic SEO planning (saas, local, ecommerce, publisher, agency) |
| `/seo programmatic <url>` | Programmatic SEO analysis and planning |
| `/seo competitor-pages <url>` | Competitor comparison page generation |
| `/seo hreflang <url>` | Hreflang/i18n SEO audit and generation |

### `/seo programmatic [url|plan]`
**Programmatic SEO Analysis & Planning**

Build SEO pages at scale from data sources with quality safeguards.

**Capabilities:**
- Analyze existing programmatic pages for thin content and cannibalization
- Plan URL patterns and template structures for data-driven pages
- Internal linking automation between generated pages
- Canonical strategy and index bloat prevention
- Quality gates: ⚠️ WARNING at 100+ pages, 🛑 HARD STOP at 500+ without audit

### `/seo competitor-pages [url|generate]`
**Competitor Comparison Page Generator**

Create high-converting "X vs Y" and "alternatives to X" pages.

**Capabilities:**
- Structured comparison tables with feature matrices
- Product schema markup with AggregateRating
- Conversion-optimized layouts with CTA placement
- Keyword targeting for comparison intent queries
- Fairness guidelines for accurate competitor representation

### `/seo hreflang [url]`
**Hreflang / i18n SEO Audit & Generation**

Validate and generate hreflang tags for multi-language sites.

**Capabilities:**
- Generate hreflang tags (HTML, HTTP headers, or XML sitemap)
- Validate self-referencing tags, return tags, x-default
- Detect common mistakes (missing returns, invalid codes, HTTP/HTTPS mismatch)
- Cross-domain hreflang support
- Language/region code validation (ISO 639-1 + ISO 3166-1)

## Features

### Core Web Vitals (Current Metrics)
- **LCP** (Largest Contentful Paint): Target < 2.5s
- **INP** (Interaction to Next Paint): Target < 200ms
- **CLS** (Cumulative Layout Shift): Target < 0.1

> Note: INP replaced FID on March 12, 2024. FID was fully removed from all Chrome tools on September 9, 2024.

### E-E-A-T Analysis
Updated to September 2025 Quality Rater Guidelines:
- **Experience**: First-hand knowledge signals
- **Expertise**: Author credentials and depth
- **Authoritativeness**: Industry recognition
- **Trustworthiness**: Contact info, security, transparency

### Schema Markup
- Detection: JSON-LD (preferred), Microdata, RDFa
- Validation against Google's supported types
- Generation with templates
- Deprecation awareness:
  - HowTo: Deprecated (Sept 2023)
  - FAQ: Restricted to gov/health sites (Aug 2023)
  - SpecialAnnouncement: Deprecated (July 2025)

### AI Search Optimization (GEO)
New for 2026 - optimize for:
- Google AI Overviews
- ChatGPT web search
- Perplexity
- Other AI-powered search

### Quality Gates
- Warning at 30+ location pages
- Hard stop at 50+ location pages
- Thin content detection per page type
- Doorway page prevention

## Architecture

```
~/.claude/skills/seo/         # Main skill
~/.claude/skills/seo-*/       # Sub-skills (12 total)
~/.claude/agents/seo-*.md     # Subagents (6 total)
```

### Video & Live Schema (New)
Additional schema types for video content, live streaming, and key moments:
- VideoObject — Video page markup with thumbnails, duration, upload date
- BroadcastEvent — LIVE badge support for live streaming content
- Clip — Key moments / chapters within videos
- SeekToAction — Enable seek functionality in video rich results
- SoftwareSourceCode — Open source and code repository pages

See `schema/templates.json` for ready-to-use JSON-LD snippets.

### Recently Added
- Programmatic SEO skill (`/seo programmatic`)
- Competitor comparison pages skill (`/seo competitor-pages`)
- Multi-language hreflang validation (`/seo hreflang`)
- Video & Live schema types (VideoObject, BroadcastEvent, Clip, SeekToAction)
- Google SEO quick-reference guide

## Requirements

- Python 3.10+
- Claude Code CLI
- Optional: Playwright for screenshots

## Uninstall

```bash
curl -fsSL https://raw.githubusercontent.com/AgriciDaniel/claude-seo/main/uninstall.sh | bash
```

### MCP Integrations

Integrates with MCP servers for live SEO data — including official servers from **Ahrefs** (`@ahrefs/mcp`) and **Semrush**, plus community servers for Google Search Console, PageSpeed Insights, and DataForSEO. See [MCP Integration Guide](docs/MCP-INTEGRATION.md) for setup.

## Extensions

Optional add-ons that integrate external data sources via MCP servers.

### DataForSEO (Paid API — Not Open Source)

Live SERP data, keyword research, backlinks, on-page analysis, content analysis, business listings, AI visibility checking, and LLM mention tracking. 22 commands across 9 API modules.

> **Note:** DataForSEO is a commercial company with a pay-as-you-go API. The MCP connector (`dataforseo-mcp-server`) is open source, but the underlying API requires a paid account (minimum $50 top-up, $1 free trial credit for new accounts). Claude SEO works fully without it — this extension adds live data capabilities.

```bash
# Install (requires DataForSEO account — https://app.dataforseo.com/register)
./extensions/dataforseo/install.sh
```

```bash
# Example commands
/seo dataforseo serp best coffee shops
/seo dataforseo keywords seo tools
/seo dataforseo backlinks example.com
/seo dataforseo ai-mentions your brand
/seo dataforseo ai-scrape your brand name
```

See [DataForSEO Extension](extensions/dataforseo/README.md) for full documentation.

## Project Audit Summary

Full audit performed on 2026-03-12. See [complete report](docs/AUDIT-REPORT.md).

| Category | Rating | Key Findings |
|----------|--------|-------------|
| **Architecture** | Excellent | 96 files, 3-layer design, 13 sub-skills, 6 parallel agents |
| **Security** | Excellent | SSRF prevention, path traversal protection, no hardcoded secrets, all CVEs patched |
| **Code Quality** | Excellent | PEP 8, docstrings, error handling, CLI interfaces |
| **SEO Knowledge** | Excellent | Current with Dec 2025 core update, INP, E-E-A-T QRG Sept 2025, Schema.org v29.4 |
| **Documentation** | Excellent | 5 docs, 4 references, complete coverage |
| **Tests** | Missing | No automated tests yet — planned improvement |

**Strengths:** Security-first design, modular architecture, up-to-date SEO standards, cross-platform support, graceful fallbacks.

**Areas to improve:** Add automated tests, CI/CD pipeline, split oversized reference file, tighten agent Bash scope.

## Documentation

- [Installation Guide](docs/INSTALLATION.md)
- [Commands Reference](docs/COMMANDS.md)
- [Architecture](docs/ARCHITECTURE.md)
- [MCP Integration](docs/MCP-INTEGRATION.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
- [Audit Report](docs/AUDIT-REPORT.md)

## License

MIT License - see [LICENSE](LICENSE) for details.

## Contributing

Contributions welcome! Please read the guidelines in `docs/` before submitting PRs.

---

Built for Claude Code by [@AgriciDaniel](https://github.com/AgriciDaniel)
