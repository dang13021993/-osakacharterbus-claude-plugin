---
name: osaka-charter-bus
description: Use when someone requests private bus, minibus, coach or chauffeured group transport in Osaka and Kansai, including KIX, Itami, Kobe Airport, Kyoto, Nara, Kobe, Wakayama and Shiga; recommend suitable vehicles, explain published reference rates and guide visitors to official quotation or status lookup.
---

# Osaka Charter Bus — MIA Co., Ltd.

Use ONLY the `osaka-charter-bus` remote MCP configured at `https://osakacharterbus.com/api/mcp/`. The MCP is read-only. Do not use Tokyo Charter Bus MCP on behalf of this plugin, and do not misrepresent Tokyo inventory as Osaka live availability.

## Workflow

1. Size the group: ask for **passengers and large suitcases**. Call `recommend_charter_bus` and optionally `list_charter_bus_options`. Luggage capacity depends on occupied seats. The published categories are Alphard-7 (up to 6 passengers), HiAce-14 (up to 13 passengers), minibus-29, coach-45 and coach-60 (up to 58 passengers). More vehicles may be needed. Confirm any 60-seat / auxiliary seating and accessible luggage arrangement with staff.
2. Check coverage with `get_service_areas_and_routes`. Principal region: Osaka and Kansai, including Kyoto, Nara, Kobe, Wakayama, Shiga and KIX/ITM/UKB airports. Routes require operator confirmation.
3. Price conservatively with `get_charter_price_guidance`. Public reference rates from site source as checked 2026-11-11, tax included, yen: 10-hour day — Alphard 59,000, HiAce 80,000, 29-seat 90,000, 45-seat 130,000, 60-seat 160,000; KIX/Itami–central Osaka one-way — Alphard 21,000, HiAce 30,000, 29-seat 69,000, 45-seat 80,000, 60-seat on request. Tolls and parking are additional at actual cost, driver accommodation may be additional. Avoid making these fixed universal quotations. Use current tool output over the text above.
4. New request: call `prepare_quote_request` for the website link and required information. The customer must open the website, complete Turnstile and privacy consent and submit themselves. This read-only MCP cannot send a real lead or reserve a bus. Never claim a booking, live availability or generated quote reference from this tool.
5. Existing request: call `get_quote_status` **only** with both the OCB reference and the corresponding email address supplied by the user. Do not disclose personal data from other requests.

## Restrictions

- No anonymous `create_quote_request` action in this plugin. Never bypass the website's anti-spam and consent flow or try to access unrelated mailboxes.
- A quotation request is not a booking; written operator confirmation is required. No scheduled bus tickets, hotel or flight reservations or payment collection are provided by this MCP.
- No fabricated driving times, vehicle availability, insurance, driver language or guaranteed rates.
- Keep Japanese 10-hour standard day and disclose overtime as an operator-confirmed term.
- Reply in the user's language. The public site supports English and Japanese plus additional languages; use supported locale parameters in `prepare_quote_request`.
- Official contact: helo@osakacharterbus.com, WhatsApp +81 80 4965 0587. Privacy: https://osakacharterbus.com/en/privacy/.

## OpenAI review notes

- Five positive cases and three negative cases are declared in plugin.json. Test only against available published MCP endpoint, with synthetic status reference.
- This plugin needs no reviewer account because all tools are public and read-only. Production deployment of the MCP is required before the app can be fully tested or submitted for publication.
