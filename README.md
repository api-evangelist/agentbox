# Agentbox (agentbox)

Agentbox - rebranded Reapit Sales after its acquisition by the UK-headquartered proptech group Reapit - is an Australian real estate CRM and sales platform used by residential sales agencies across Australia and New Zealand, covering contacts and prospecting, listing management, appraisals, vendor management, marketing, agency websites, and a mobile agent app. Its position in the value chain is the agency system of record and, critically, the portal uploader - Agentbox is the system that pushes an agency's for-sale and for-rent listings out to realestate.com.au, domain.com.au, allhomes, commercialrealestate.com.au and dozens of other Australian portals, which in the Australian market is the REAXML feed seam rather than an MLS. Its API posture is honest but closed - a production API gateway is live at api.agentboxcrm.com.au (Tyk, HTTP 401 "Authorization field missing" to anonymous callers, authenticated with an X-API-Key header alongside a Client ID and Office ID), but there is no public developer portal, no published reference, and no downloadable machine-readable contract. Access is application-approval only - every third party must complete the Reapit Sales Integrator Application and be reviewed before an agency's API Key, Client ID and Office ID are issued by support. There is no RESO Web API or Data Dictionary certification, no OData $metadata document, and no Universal Property Identifier - RESO is a North American MLS regime with no presence in this Australian vendor's surface - and no open data is published.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/agentbox/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/agentbox/refs/heads/main/apis.yml)

## Tags

- Real Estate
- Australia
- Property Listings
- PropTech
- CRM
- REAXML
- Portal Feeds
- Rentals
- Commercial Real Estate
- New Zealand

## Timestamps

- **Created:** 2026-07-26
- **Modified:** 2026-07-26

## APIs

### Agentbox API

The production Agentbox (Reapit Sales) REST API used by approved integration partners to read and write agency CRM data - contacts, listings, properties, staff and offices. The host is live and fronted by a Tyk gateway - an anonymous request returns HTTP 401 with `{"error":"Authorization field missing"}`, and supplying an `X-API-Key` header advances the request past the gateway, confirming API-key authentication. Third-party integration guides (Domo, Auctions Live, WordPress connectors) consistently describe the same credential triple - API Key, Client ID and Office ID - issued per agency office by Reapit Sales support. No public API reference, OpenAPI/Swagger document or Postman collection is published - every documentation path probed on the gateway returned 401 or 404 - so no machine-readable contract could be harvested. Access requires completing the Integrator Application and being approved.

- **Human URL:** [https://www.agentbox.com.au/integrator-application](https://www.agentbox.com.au/integrator-application)
- **Base URL:** `https://api.agentboxcrm.com.au`

#### Tags

- Real Estate
- CRM
- Property Listings
- Australia

#### Properties

- [Onboarding](https://www.agentbox.com.au/integrator-application)
- [Support Page](https://help.agentboxcrm.com.au/home)
- [Support Email](mailto:sales@agentbox.com.au)

## Access

- **Access gate:** `application-approval` - the Integrator Application is reviewed by Reapit Sales before any integration is approved, and each agency customer must separately request its office's API Key, Client ID and Office ID from support.
- **Auth model:** API key (`X-API-Key`) on a Tyk gateway, paired with a Client ID and Office ID. No OAuth 2.0 or OpenID Connect discovery document is served.
- **RESO posture:** No RESO reference found - no Web API certification, no Data Dictionary certification, no `$metadata`, no UPI. Australia has no MLS; listing distribution runs on REAXML into realestate.com.au and Domain.
- **Open data:** None.
- **Home market:** Australia (and New Zealand).

## Common Properties

- [Website](https://www.agentbox.com.au/)
- [Blog](https://www.agentbox.com.au/blog)
- [Support Page](https://help.agentboxcrm.com.au/home)
- [Documentation - Reapit Integrations](https://help.agentboxcrm.com.au/reapit-integrations)
- [Documentation - Portals](https://help.agentboxcrm.com.au/portals)
- [Onboarding - Integrator Application](https://www.agentbox.com.au/integrator-application)
- [Plans](https://www.agentbox.com.au/plans-inclusions)
- [Terms of Service](https://www.agentbox.com.au/terms-conditions)
- [Privacy Policy](https://www.agentbox.com.au/privacy)
- [About](https://www.agentbox.com.au/about-us)
- [Contact](https://www.agentbox.com.au/contact-us)
- [Twitter](https://twitter.com/agentboxau)
- [Parent Company](https://www.reapit.com.au/)

## Maintainers

- Kin Lane <kin@apievangelist.com>
