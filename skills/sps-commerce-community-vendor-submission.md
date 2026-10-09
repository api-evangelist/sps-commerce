---
name: sps-commerce-community-vendor-submission
description: Discover a Community submission form and submit a new trading partner (vendor) to an SPS Commerce Community program.
api: openapi/sps-commerce-submission-api-openapi.yml
operations:
  - get_forms_v1_forms_get
  - get_form_v1_forms__id__get
  - create_lead_v1_trading_partners_post
generated: '2026-10-09'
method: generated
---
# Community vendor submission

Server: `https://api.spscommerce.com/submissions`. Auth: HTTP bearer token. For Community Buying Organizations automating new-vendor submissions.

1. `get_forms_v1_forms_get` (`GET /v1/forms`) — list available submission forms; page with `offset` / `limit`.
2. `get_form_v1_forms__id__get` (`GET /v1/forms/{id}`) — read the chosen form to learn the fields it requires.
3. `create_lead_v1_trading_partners_post` (`POST /v1/trading-partners`) — submit the trading partner as JSON; 201 on success.
4. Errors: 400 invalid body, 403 not permitted, 404 form not found, 500 server error. No idempotency key is documented, so do not blindly retry the POST.
