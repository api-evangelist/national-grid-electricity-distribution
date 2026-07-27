# National Grid Electricity Distribution (national-grid-electricity-distribution)

National Grid Electricity Distribution (NGED) is the licensed electricity distribution network operator for the Midlands, the South West of England and South Wales — the poles-and-wires DNO that delivers power to over 7.9 million customers across roughly 55,500 square kilometres, formed when National Grid acquired Western Power Distribution in 2021. It sits between the transmission network and the retail suppliers, owning the physical network, the connection queue and the low-voltage measurement estate, while selling nothing to consumers directly. Its home market is the United Kingdom, where there is no consumer data-portability mandate equivalent to Australia's Consumer Data Right: individual household smart-meter data flows through the licensed Smart DCC monopoly and the energy suppliers, not through the distributor. What Britain mandated instead lands squarely on NGED — Ofgem's Data Best Practice Guidance is a licence condition on every DNO, and NGED has actually implemented it. The Connected Data Portal at connecteddata.nationalgrid.co.uk is a live CKAN 2.9.8 instance carrying 91 datasets and 8,687 resources under a genuine open licence derived from the Open Government Licence v3.0, with a documented public CKAN Action API, published API-token guidance, and DCAT catalogue exports in JSON-LD, Turtle, N3 and RDF/XML. The posture is therefore the inverse of most utilities in this study: open, documented and machine-readable on grid and market data — including the Ofgem-mandated aggregated smart-meter consumption data at LV feeder and secondary substation level — and completely absent on individual consumer data, which the distributor is neither obliged nor equipped to expose. Anonymous callers get the full catalogue and 774 resource payloads; the other 7,913 are redacted behind a free, self-serve, email-verified account.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/national-grid-electricity-distribution/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/national-grid-electricity-distribution/refs/heads/main/apis.yml)

## Tags

- Energy
- United Kingdom
- Utilities
- Electricity
- Grid
- Distribution Network
- Open Data
- Smart Metering
- DER
- Flexibility
- Renewables

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### NGED Connected Data Portal API

The public CKAN 2.9.8 Action API behind National Grid Electricity Distribution's Connected Data Portal, documented by NGED on its own API Guidance page. Exposes the DNO's open data catalogue — 91 datasets, 8,687 resources, 155 tags and 6 data groups (connection, demand, flexibility, innovation, system-and-network, system-planning) — covering live power cuts, live primary and secondary substation measurements, LV load monitoring, the Embedded Capacity Register, the generation capacity register, distribution substation data and the Ofgem-mandated aggregated smart meter consumption data. Catalogue-level calls (`package_list`, `package_search`, `package_show`, `group_list`, `group_show`, `tag_list`, `status_show`) return 200 anonymously. Resource-level calls (`resource_show`, `datastore_search`) and the majority of resource download URLs are gated behind a free API token, returning `Access denied: Resource access restricted to registered users`.

- **Human URL:** [https://connecteddata.nationalgrid.co.uk/api-guidance](https://connecteddata.nationalgrid.co.uk/api-guidance)
- **Base URL:** `https://connecteddata.nationalgrid.co.uk/api/3/action/`

#### Tags

- Open Data
- Electricity
- Distribution Network
- Grid
- Smart Metering
- Flexibility
- CKAN

#### Properties

- [Documentation](https://connecteddata.nationalgrid.co.uk/api-guidance)
- [API Reference](https://docs.ckan.org/en/latest/api/index.html)
- [Portal](https://connecteddata.nationalgrid.co.uk/)
- [Datasets](https://connecteddata.nationalgrid.co.uk/dataset/)
- [Authentication](https://connecteddata.nationalgrid.co.uk/api-guidance)
- [Sign Up](https://connecteddata.nationalgrid.co.uk/user/register)
- [Documentation](https://connecteddata.nationalgrid.co.uk/registration-and-subscription)
- [License](https://www.nationalgrid.co.uk/open-data-licence)
- [Support](https://connecteddata.nationalgrid.co.uk/contact)

### NGED Connected Data DCAT Catalogue

Machine-readable DCAT catalogue exports of the entire NGED Connected Data Portal, linked from the footer of every portal page and served anonymously in four serialisations — JSON-LD (205 KB), Turtle (112 KB), N3 and RDF/XML. Not a REST API but a genuine, versionless, contract-shaped harvesting surface for the DNO's full 91-dataset catalogue.

- **Human URL:** [https://connecteddata.nationalgrid.co.uk/](https://connecteddata.nationalgrid.co.uk/)
- **Base URL:** `https://connecteddata.nationalgrid.co.uk/`

#### Tags

- Open Data
- DCAT
- JSON-LD
- Catalog

#### Properties

- [JSON-LD](https://connecteddata.nationalgrid.co.uk/catalog.jsonld)
- [Data](https://connecteddata.nationalgrid.co.uk/catalog.ttl)
- [Data](https://connecteddata.nationalgrid.co.uk/catalog.xml)
- [Data](https://connecteddata.nationalgrid.co.uk/catalog.n3)
- [Portal](https://connecteddata.nationalgrid.co.uk/)
- [License](https://www.nationalgrid.co.uk/open-data-licence)

## Common Properties

- [Website](https://www.nationalgrid.co.uk/)
- [About](https://connecteddata.nationalgrid.co.uk/about)
- [Portal](https://connecteddata.nationalgrid.co.uk/)
- [Documentation](https://connecteddata.nationalgrid.co.uk/api-guidance)
- [Sign Up](https://connecteddata.nationalgrid.co.uk/user/register)
- [License](https://www.nationalgrid.co.uk/open-data-licence)
- [Privacy Policy](https://www.nationalgrid.co.uk/privacy-policy)
- [Terms of Service](https://www.nationalgrid.co.uk/terms-and-conditions)
- [Support](https://connecteddata.nationalgrid.co.uk/contact)
- [Case Studies](https://connecteddata.nationalgrid.co.uk/case-studies)
- [Data](https://connecteddata.nationalgrid.co.uk/dataset/)
- [Documentation](https://commercial.nationalgrid.co.uk/digitalisation-and-data)
- [Portal — DSO](https://dso.nationalgrid.co.uk/)
- [Portal — Power Cuts](https://powercuts.nationalgrid.co.uk/)
- [Portal — Planned Outages](https://planned.nationalgrid.co.uk/)
- [Portal — Connections](https://connections.nationalgrid.co.uk/)
- [Portal — Network Opportunity Map](https://commercial.nationalgrid.co.uk/network-opportunity-map)
- [Documentation](https://www.nationalgrid.co.uk/electricity-distribution)

## Mandate and Access Posture

| Dimension | Finding |
| --- | --- |
| Mandate regime | `other` — Ofgem Data Best Practice Guidance, imposed as an electricity distribution licence condition. Not a consumer data right. |
| Mandate status | `live-implemented` — NGED quotes the licence condition verbatim in its own dataset metadata and ships the mandated aggregated smart-meter data alongside it. |
| Secondary regime | `smart-meter-infrastructure` — the Smart DCC under the Smart Energy Code. NGED is a permitted network user, not a publisher. No NGED-operated DCC developer surface exists. |
| Data standard | CKAN Action API 3 (2.9.8) + DCAT + an Open Government Licence v3.0–derived open licence. No energy-domain standard found — no Green Button, ESPI, CDR, OCPP/OCPI, OpenADR, IEEE 2030.5 or IEC CIM. |
| Consumer data API | No. A GB distributor holds no billing relationship; household smart-meter data flows via the DCC and suppliers. Smart-meter data published by NGED is aggregated by design. |
| Market data open | Yes. 91 datasets / 8,687 resources, queryable anonymously, 774 payloads downloadable with no account, under a commercially reusable open licence. |
| Access gate | `self-serve` — register, verify email, self-issue an API token from your profile. No approval, no accreditation, no licence signature. |
| Auth model | CKAN API Token (opaque JWT-shaped bearer string) sent in the `Authorization` header. No OAuth 2.0, no OIDC, no mTLS. |
| Machine-readable contracts | None. NGED publishes no OpenAPI, AsyncAPI, GraphQL SDL, JSON Schema, Postman collection or MCP descriptor; its API Guidance delegates the reference to docs.ckan.org. |

See [`review.yml`](review.yml) for the full evidence trail — every URL probed, with the HTTP status observed on 2026-07-27.
