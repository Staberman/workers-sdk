---
"miniflare": patch
---

Accept raw MIME email replies that omit the `In-Reply-To` header

`message.reply()` with a raw `EmailMessage` no longer fails locally with "no In-Reply-To header found in reply message" when the reply leaves out `In-Reply-To`. Matching Email Routing, Miniflare now sets `In-Reply-To` from the incoming email's `Message-ID` (and `References` as before). A reply that sets a mismatched `In-Reply-To` is still rejected.
