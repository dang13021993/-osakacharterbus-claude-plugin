# Osaka Charter Bus for Claude

This is the separate public-safe Claude plugin source bundle, containing no private website code or credentials.

Install this in a dedicated public GitHub repository with .claude-plugin/plugin.json at the repository root for Claude directory publication. The existing dang13021993/osakacharterbus source repository is private; do not change its visibility merely to publish this plugin.

The MCP is read-only and must be tested on the current production website before submitting to Claude Directory. Reviewers should check tool list and the privacy-preserving quotation flow.

MCP: https://osakacharterbus.com/api/mcp/
Website: https://osakacharterbus.com/en/
Operator: MIA Co., Ltd.

No payments, confirmed bookings, or anonymous lead submission are performed through the MCP.

## Directory submission

Upload the *contents* of this ZIP at the root of a separate public GitHub repository. Verify that .claude-plugin/plugin.json and .mcp.json appear at repository root; do not nest the whole extracted folder. The full website source repo can remain private.
