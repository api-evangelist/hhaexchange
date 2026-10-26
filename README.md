# HHAeXchange

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

HHAeXchange is a homecare management platform providing scheduling, Electronic Visit Verification (EVV), Medicaid billing, and caregiver management for home health agencies and payers. The platform exposes RESTful HTTPS APIs enabling third-party EVV systems to integrate with state Medicaid programs.

## API Overview

The HHAeXchange EVV API allows third-party EVV vendors and aggregators to submit caregiver records and visit data for state Medicaid compliance. The API uses OAuth 2.0 (client credentials flow) for authentication and returns JSON responses.

### Key Endpoints

- `POST /identity/connect/token` — Obtain OAuth 2.0 access token (30-minute expiration)
- `POST /api/v{version}/caregivers` — Create or update caregiver records
- `POST /api/v{version}/visits` — Submit one or more EVV visit records
- `PUT /api/v{version}/visits/{evvmsid}` — Update an existing visit record
- `DELETE /api/v{version}/visits/{evvmsid}` — Remove a visit record
- `GET /api/v{version}/visits/transactions/{transactionId}` — Check transaction processing status

### Authentication

OAuth 2.0 client credentials (client ID, client secret, scope). Tokens expire in 30 minutes and should be reused until expiration.

### Rate Limits

- 200 calls per method per provider per minute
- Maximum 5 transaction status checks per second
- Maximum 2 active credential sets per provider

## Documentation

- [API Overview](https://knowledge.hhaexchange.com/edi/Content/Documentation/EDI/API.htm)
- [API Workflow and Endpoints](https://knowledge.hhaexchange.com/edi/Content/Documentation/EDI/API-Workflow-Endpoints-P.htm)
- [Onboarding and Integration](https://knowledge.hhaexchange.com/edi/Content/Documentation/EDI/API-Onboarding-Integration-P.htm)
- [HTTP Response Status Codes](https://knowledge.hhaexchange.com/edi/Content/Documentation/EDI/API-HTTP-Response-Status-Codes-P.htm)
- [System Status](https://hhaexchange.statuspage.io/)

## Support

For API integration inquiries: EINTSupport@hhaexchange.com

## APIs.json

This repository is indexed by [apis.json](apis.yml) following the [APIs.json 0.19 specification](https://apisjson.org).
