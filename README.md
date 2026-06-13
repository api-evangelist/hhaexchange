# HHAeXchange

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
