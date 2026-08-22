# Omnitracs (omnitracs)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
