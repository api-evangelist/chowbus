# Chowbus

Chowbus is a Chicago-headquartered restaurant technology company founded in 2016 by Linxin Wen and Suyu Zhang. It began as an online food ordering, payment and delivery marketplace for Asian restaurants and has since pivoted to a cloud-based, AI-assisted restaurant operating platform: point of sale, self-ordering kiosks, handheld and tablet ordering, kitchen display systems, waitlist and reservations, online ordering, branded restaurant websites and mobile apps, loyalty, gift cards, SMS marketing, a promotions engine, multi-location management, and an AI suite. Chowbus states it serves 9,000+ restaurants across all 50 U.S. states and Canada, and raised an $81M growth round in March 2026 led by Prysm Capital and Left Lane Capital.

- https://www.chowbus.com/

## API surface

As of the 2026-08-02 enrichment pass, Chowbus publishes **no public developer portal, API reference, OpenAPI/Swagger, GraphQL endpoint, AsyncAPI, webhook catalog, SDK, CLI, or sandbox**. A live JSON API host (`pos-api.chowbus.com`) exists and returns a structured error envelope, but it is undocumented and gated. A private partner integration surface demonstrably exists — Chowbus markets two-way order/menu sync with 45+ delivery marketplaces, and aggregators such as Deliverect publish Chowbus POS connectors — but none of it is publicly specified.

The one machine-readable agent artifact Chowbus does publish is a hand-authored bilingual (EN/ZH) `llms.txt`.

## Artifacts

| Artifact | Method | Notes |
|---|---|---|
| `llms/chowbus-llms.txt` | searched | Verbatim from https://www.chowbus.com/llms.txt (HTTP 200, 28,644 bytes) |
| `well-known/chowbus-well-known.yml` | probed | 4 hosts × 20 paths; the only 200 was `/llms.txt` |
| `conventions/chowbus-conventions.yml` | probed | Observed API hosts, error-envelope shape, and the full contract-discovery negative record |
| `security/chowbus-domain-security.yml` | probed | TLS 1.3 + HSTS on all four hosts; DNSSEC on, no CAA, SPF + DMARC (`p=quarantine`) |

No `a2a/`, `mcp/`, `openapi/`, `packages/`, `skills/`, `sandbox/`, `changelog/`, or `errors/` artifacts were written — nothing to search, generate, or derive without a contract or published surface.
