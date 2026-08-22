# Agentbox (agentbox)

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
