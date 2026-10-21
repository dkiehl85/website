---
title: "Scoping CMMC Level 2 with an enclave: what actually shrinks"
date: 2026-10-08
draft: true
description: "An enclave can cut your assessment scope dramatically, but not everything leaves scope. Here's what stays in."
topics: ["CMMC & CUI"]
---

> **SAMPLE ARTICLE: review, edit, and verify before publishing.** Set `draft: false` when it's ready.

When a mid-sized firm looks at CMMC Level 2, the first instinct is often "we'll put CUI in an enclave and only assess that." It's a good instinct. But the enclave shrinks scope less than people expect.

## What the enclave does shrink

- **CUI Assets:** the systems that process, store, or transmit CUI. If CUI only lives in the enclave, these are only the enclave's endpoints, file stores, and applications.
- **The user population** that needs CUI-level controls applied to their day-to-day work.

## What stays in scope anyway

- **Security Protection Assets:** your identity provider, logging/SIEM, endpoint protection, and admin tooling that protect the enclave. If corporate IT runs them, they're in.
- **People and process.** Training, incident response, personnel security, and media protection apply to everyone who touches CUI, inside the enclave or not.
- **The leaks.** CUI that arrives by email to a corporate inbox, gets printed, or is saved to a laptop "just this once." Every leak path makes the enclave boundary weaker.

## The practical test

Draw every way CUI enters and leaves your organization. If any arrow ends outside the enclave, you either have a technical control blocking it or a scope problem. Most of the real work goes into closing those arrows, not into building the enclave.
