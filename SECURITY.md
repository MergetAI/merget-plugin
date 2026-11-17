# Security policy

This repository, MergetAI/merget-plugin (Merget's plugin for coding agents), is part of Merget, the semantic merge queue for GitHub made by Merget, Inc. Security reports for it, and for every part of the Merget service, go to **security@merget.ai**. The full policy is published at https://merget.ai/legal/vulnerability-disclosure, and the contact is also in https://merget.ai/.well-known/security.txt.

## Reporting a vulnerability

Email security@merget.ai, in English, with:

- what you found and where (the file in this repository, or the host, route, tool or page in the service), and the account or organization you used, if any;
- the steps to reproduce it, with requests and responses where they help;
- the impact as you understand it: what an attacker could read, change or do;
- whether anyone else knows, and whether the details are published anywhere;
- how we can reach you, and the name to credit if you want credit.

Do not open a public issue for a security problem. Where this repository has GitHub private security advisories turned on, you may open one instead of emailing; it reaches the same people. Do not send another customer's data; if you reached it by accident, stop, tell us what you saw, and delete your copy.

## What we do

- We acknowledge every report within 3 business days, with a reference to quote.
- We confirm the issue, rate its severity, and tell you what we plan to do.
- We fix confirmed issues in priority order and tell you when the fix ships. In this repository a fix lands as a release; its changelog names the issue once the fix is out.
- With your agreement, we credit you in the release note.

## Scope

In scope: this repository's code, the Merget service it connects to (merget.ai, sema.merget.ai with the HTTP API and MCP server, auth.merget.ai, demo.merget.ai), the Merget GitHub App, the Claude Code plugin and its skills, the CLI, Merget's build and validation environment, and the emails and text messages Merget sends.

Out of scope: denial of service; social engineering or physical attacks; vulnerabilities in third-party services (GitHub, Google Cloud, Stripe, PostHog, Cloudflare, Slack), which go to the vendor; findings in a customer's own repositories; best-practice reports with no demonstrated impact; automated scanner output with no proof of exploitability.

## Safe harbor

Research that follows the published policy is authorized: test only accounts and repositories you own or may use, stop as soon as you can show the issue, do not degrade the service, do not use social engineering, and keep the details private until a fix ships or 90 days have passed since our acknowledgment, whichever comes first. For such research Merget will not pursue civil action, will not refer you for prosecution, and will not bring a claim under the Computer Fraud and Abuse Act, the Digital Millennium Copyright Act or similar laws. If you break a rule by accident, tell us at once.

## No bounty

Merget does not run a bug bounty and does not pay for reports. We thank researchers and credit them when they want credit.

## Supported versions

Only the latest released version of this repository receives security fixes. Keep your installation current; where the Claude Code plugin's auto-update is on, it brings the fix on its own.
