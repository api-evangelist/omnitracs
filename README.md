# Omnitracs (omnitracs)

Omnitracs is a commercial fleet-management, telematics, and transportation-management provider, now part of **Solera Inc.** (Solera acquired Omnitracs in 2021, and it operates today under Solera Fleet Solutions). The Omnitracs One platform and the Omnitracs Roadnet routing platform serve roughly 15,000 fleet customers with ELD / Hours-of-Service compliance, telematics and GPS positioning, driver workflow and messaging, routing and dispatch, and video safety.

> **Access model — partner/customer gated (honest stub).** Omnitracs exposes *real* integration APIs and web services, but there is **no open, self-service public developer portal**. API credentials (a username/password with API access) and the full integration developer wiki are provisioned to contracted customers and integration partners. The APIs described below are honestly **modeled** from public integration release notes and the Services Portal integration document — they are marked `endpointsModeled: true` in `apis.yml` rather than mirrored from an open reference, and no concrete endpoint list is fabricated.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/omnitracs/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/omnitracs/refs/heads/main/apis.yml)

## Tags

- Fleet Management
- Telematics
- ELD
- Hours of Service
- Transportation
- Routing
- Trucking
- GPS
- Solera

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

### Omnitracs Web Services (Roadnet Platform)

Integration web services for the Omnitracs Roadnet routing and dispatch platform (route planning and optimization, orders/stops, and schedules). A live Swagger UI is published at the integration host, but the underlying operations require a provisioned integration account; the surface is not openly self-service. Endpoints are modeled, not mirrored from an open reference.

- **Human URL:** [https://apex-prod-integration.aws.roadnet.com/integration/api-docs/index.html](https://apex-prod-integration.aws.roadnet.com/integration/api-docs/index.html)
- **Base URL:** `https://apex-prod-integration.aws.roadnet.com/integration`
- **Endpoints modeled:** yes

### Omnitracs Entity Management Web Services

Services Portal entity-management web services for maintaining fleet master data — vehicle maintenance (add/edit), driver maintenance (add/edit), and trailer management, with HOS Group membership and a bulk importer. Also exposed as Entity Management Web Service Extensions for the Omnitracs One platform. Partner/customer gated; a username/password with API access is required. Endpoints are modeled from public integration notes.

- **Human URL:** [https://services.omnitracs.com/portalWeb/](https://services.omnitracs.com/portalWeb/)
- **Endpoints modeled:** yes

### Omnitracs Event Subscription Service (ESS)

A publish-subscribe integration service in which Omnitracs applications continually publish transactions (vehicle positions/GPS, driver messages, Hours-of-Service logs, and critical-event / driver-coaching notifications) to the Integration Web Server, and back-office applications subscribe to and periodically request the transaction types they want. The Event Subscription Service delivers each transaction as a SOAP/XML package and expects a SOAP/XML acknowledgement. Transport is request/response polling over HTTPS, **not a WebSocket**. Partner/customer gated; endpoints are modeled.

- **Human URL:** [https://services.omnitracs.com/portalWeb/](https://services.omnitracs.com/portalWeb/)
- **Endpoints modeled:** yes

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/omnitracs)
- [Website](https://www.omnitracs.com)
- [Documentation](https://apex-prod-integration.aws.roadnet.com/integration/api-docs/index.html)
- [Signup URL](https://services.omnitracs.com/portalWeb/)
- [Plans](plans/omnitracs-plans-pricing.yml)
- [Parent (Solera Fleet Solutions)](https://www.solera.com/solutions/fleet-solutions/omnitracs/)

## Pricing

Omnitracs does not publish a public, self-service price list; pricing is custom-quoted by fleet size, modules, hardware, and volume. Third-party 2025–2026 reviews cite indicative figures (e.g. BYOD ELD from ~$22.95/vehicle/month, standard plans from ~$35/vehicle/month with a minimum fleet size, IVG hardware ~$799/unit). See [`plans/omnitracs-plans-pricing.yml`](plans/omnitracs-plans-pricing.yml). API/web-service access is bundled with the underlying subscription rather than sold as a standalone metered API product.

## WebSocket Review

Omnitracs does **not** expose a documented public WebSocket API. Its event-oriented surface (the Event Subscription Service) is SOAP/XML publish-subscribe consumed by polling, not a server-push `wss://` endpoint. See [`review.yml`](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
